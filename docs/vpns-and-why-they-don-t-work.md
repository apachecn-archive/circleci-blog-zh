# VPN 和为什么他们不工作- CircleCI

> 原文：<https://circleci.com/blog/vpns-and-why-they-don-t-work/>

**来自出版商的说明:**您已经找到了我们的一些旧内容，这些内容可能已经过时和/或不正确。尝试在[我们的文档](https://circleci.com/docs/)或[博客](https://circleci.com/blog/)中搜索最新信息。

* * *

请注意:这篇文章专门介绍了我们在 SaaS 的服务。如果您的团队使用 VPN，我们的[企业产品](https://circleci.com/enterprise/)将更适合您。给我们[一行](mailto:%20enterprise@circleci.com)多聊聊。

用户经常向支持部门询问的一个问题是，如何在他们的构建中创建一个 VPN 隧道来安全地访问网络资源。这在我们的平台上不工作有几个原因。一个是由于 VPN 如何创建 TUN/TAP 设备，另一个与无特权的 LXC 容器有关。这篇文章将解决使用 CircleCI 和 VPN 的常见问题。

## 调谐器/TAP 设备

### 什么是调谐器/TAP 设备？

调谐器/TAP 设备是为 VPN 连接创建和使用的特定设备。它充当以太网设备，但不是直接从物理设备接收数据，而是从用户空间程序接收数据(可以是您正在使用的任何 VPN 类型，如 L2TP、PPP、Cisco 等)。).然后，它将数据发送回用户空间程序，用户空间程序再将数据发送到加密的“设备”，以便传输到目的地。

### 这和我的构建有什么关系？

VPN 连接软件使用特定设备节点(如/dev/net/tun)创建设备，并将其注册为 tunX 或 tapX。创建 VPN 连接的用户空间程序需要有创建设备的适当权限。使用该设备的驱动程序也需要编译到内核中才能正确使用。虽然用户确实可以访问他们的构建，但这并不适用于您的构建是有原因的，这就是 LXC 发挥作用的地方。

## 无特权的 LXC 集装箱

### 什么是 LXC 集装箱？

当用户运行一个构建时，我们创建一个 LXC 容器。linux 内核为不同的运行进程提供了不同的系统“视图”。这允许物理资源，如 I/O、CPU、RAM 等。在逻辑上被“划分”。内核还允许使用两个主要组件:控制组和 POSIX 文件功能。控制组允许内核将一个或多个进程组合在一起，然后指定要分配给该控制组的资源。POSIX 文件功能只是允许这些进程使用的文件比标准的“根”和“用户”权限分离具有更细粒度的安全性。

### 什么是无特权 LXC 容器？

无特权的 LXC 集装箱是 LXC 集装箱的一个更安全的版本，并且是我们在 CircleCI 使用的。在特权 LXC 容器中，主机和容器的根 UID 是相同的(0)。这意味着，如果用户能够通过/proc 或/sys 文件系统，或者通过某个 syscall 突破容器，他们将是主机上的 UID 0(或 root ),从而对主机以及该主机上的所有其他容器/资源拥有 root 访问权限。

非特权 LXC 容器使用用户名称空间为用户分配主机上未使用的用户和组 ID 范围(通常为 100，000 到 165，000)。这意味着如果用户能够突破容器，容器的 UID 0 将映射到主机上的 UID 100，000。这实际上授予了他们与 nobody 用户相同的权限，并且极大地限制了他们在主机上的权限。

### 为什么这意味着我不能创建 VPN？

当容器中的“root”用户试图制作一个 TUN/TAP 设备时，它在主机上需要比它所拥有的有限访问权限更多的权限。这限制了多项操作，包括但不限于:

*   挂载某些文件系统
*   创建设备节点(如创建 TUN/TAP 设备所需的节点)
*   或者任何需要分配给-- LXC 分配给容器的 UID/GID 范围(100，000 - 165，000 范围)之外的权限的操作。

如果不能在非特权容器上创建 TUN/TAP 设备，使用非特权 LXC 容器的任何平台上的任何用户都不能使用 VPN 服务。这意味着，只要我们使用无特权的 LXC 容器，就不会支持创建 TUN/TAP 设备，除非 LXC 对上游进行了更改，允许我们允许用户创建这些设备。

这是否意味着你无能为力？不，当然不是。还有一些其他的选择。我们将发布一篇后续文章，概述这些内容，并展示如何在未来实现它们。