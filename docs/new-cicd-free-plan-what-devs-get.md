# 开发者从最慷慨的免费计划中获得的开箱即用的东西

> 原文：<https://circleci.com/blog/new-cicd-free-plan-what-devs-get/>

免费增值计划是公司向开发者介绍他们的产品的好方法，并提供了他们所提供的价值的实际演示。但是，当一个自由层限制了对关键特性的访问，或者没有提供足够的能力来评估产品在现实世界开发场景中的表现时，这对开发人员来说是非常令人沮丧的。这不仅令人沮丧，而且还降低了开发人员的整体体验，导致对产品的负面的、有时是不准确的理解。

许多公司努力在免费层中包含哪些功能以及在何种使用水平下需要付费账户之间取得平衡。CircleCI 也不例外。直到最近，我们的免费计划还不足以提供最好的开发人员体验，并展示 CircleCI 可以为您的持续交付和发布流程带来的价值和力量。这就是为什么我们决定彻底改革我们的服务，提供市场上最全面的免费计划。

在这篇文章中，我将讨论新发布的 CircleCI 免费计划，强调一些最具影响力的变化以及它们将如何改善开发者体验。

## 免费计划详情

开发人员不断采用创新的策略和概念，比如持续交付和发布管理过程，目标是更快更有效地构建和发布软件。CircleCI 通过自动化软件构建和发布实践，使您的团队能够最大化开发速度。借助我们新推出的免费层产品，您可以获得充分利用构建时间所需的所有特性和功能。以下是新的免费计划给您带来的好处:

*   无限用户
*   每月 30，000 积分，足以支持多达 6，000 分钟的构建时间，具体取决于您的计算类型
*   访问多种执行环境，包括 Docker、Linux、Arm 和 Windows，以及更大的资源类
*   30 个并发作业在任何可用的计算选项上运行
*   5 个自托管运行程序在您自己的机器上运行作业
*   1 GB 的网络数据传输到自托管的运行者，2 GB 的数据存储用于保存缓存和工作区，上传测试结果，以及构建工件
*   Docker 层缓存加速您的 Docker 构建
*   在我们的 Insights 仪表盘上检测多达 5 项测试
*   能够创建私有 orb，以便与团队的其他成员共享配置代码

既然我已经简要描述了新的免费计划中包含的令人敬畏的产品和特性，那么让我们仔细看看对开发者和他们的团队最重要的一些特性。

## 更大的资源类别

发布周期变得越来越短，这样团队就可以尽快向用户发布变更和新特性。对于开发人员来说，要满足他们的发布周期需求，关键是他们要对要发布的变更执行高效的 CI/CD 管道。有许多方法可以优化您的 CI/CD 管道，最简单和最有效的方法之一是通过一个称为[资源类](https://circleci.com/docs/configuration-reference/#resourceclass)的特性来控制管道的底层计算节点容量。

资源类功能使团队能够配置和管理计算节点资源(如 CPU 和 RAM)的容量，确保管道有适当的马力来成功和方便地完成管道作业。通常，管道作业资源类配置的资源容量不足，导致运行速度大大降低。这些较慢的运行逐渐延长了管道完井的持续时间，这可能导致释放过程的延迟。新的免费计划提供了对更广泛的资源类的访问，使团队能够拨入正确的资源来优化他们的管道作业性能。

## 30 倍并发

除了为管道作业提供适当的计算能力，团队可以用来加速管道的另一个功能是并发性，即跨多个执行环境同时运行多个作业的能力。在新的免费计划下，您现在可以同时运行多达 30 个作业，这可以通过允许您在给定的执行环境中避免由资源限制引起的排队来节省大量时间。

管道内并发的一个很好的用例是[并行测试执行](/blog/how-bolt-optimized-their-ci-pipeline-to-reduce-their-test-run-time-by-over-3x/)。项目中的测试越多，在单台机器上完成测试所需的时间就越长。为了减少这个时间，您可以通过在您的作业配置中指定一个`parallelism`级别来并行运行测试。然后，您的测试将在多个独立的执行器上同时运行，从而允许您缩短验证和向您的用户发布更改所需的时间。有关并行性和并发性的更多信息，请查看[文档](https://circleci.com/docs/parallelism-faster-jobs/)。

## Docker 层缓存

Docker 是 CircleCI 平台中可用的[容器化](/blog/benefits-of-containerization/)技术。Docker 映像允许团队构建容器环境来运行作业，许多团队构建自己的 Docker 映像来定制测试和部署应用程序的环境。Docker 映像是从 docker 文件构建的，docker 文件中的每个命令都会在映像中产生一个层。构建 Docker 映像可能是 CI/CD 工作流程中最耗时的任务之一。

CircleCI Free 计划现在提供 Docker 层缓存，您可以通过在每次作业运行时保存 Docker 映像的各个层来减少重复构建 Docker 所花费的时间。下次运行工作流时，CircleCI 将从缓存中检索任何未更改的图层，而不是从头开始重建整个图像。这使得团队能够高效地打包他们的应用程序并构建相关的 Docker 映像，而不会降低管道执行速度。有关 Docker 层缓存的更多信息，请查看文档。

## 私人球体

orb 是 YAML 的可重用包，使开发者更容易自动化流程，将第三方工具整合到他们的管道中，以及跨项目共享配置。虽然在我们的[公共 orb 注册表](https://circleci.com/developer/orbs)中有许多有用的 orb，但在医疗保健、金融或公共部门等高监管行业工作的团队通常需要更高级别的安全性和合规性。

有了[私有 orb](https://circleci.com/docs/orb-intro/#private-orbs)，您的团队将获得 orb 的所有协作和效率优势，以及通过限制组织内经过身份验证的用户的访问而增加的隐私和安全性。您的团队可以使用 CLI 工具创建和发布新的私有 orb，经过身份验证的用户可以通过访问 CircleCI web 应用程序的组织设置选项卡中的 orb 页面来查看和管理您组织的私有 orb。

## 通过不稳定的测试检测获得测试洞察力

自动测试代码变更是[持续集成](https://circleci.com/continuous-integration/)的基础，也是最小化软件发布风险的重要一步。但现实是大多数测试并不完美。它们并不总是像预期的那样执行，有时还会不稳定，这意味着它们会不确定地失败。使用 [CircleCI Insights 仪表板](/blog/monitor-and-optimize-your-ci-cd-pipeline-with-insights-from-circleci/)，您可以监控多个工作流和开发分支的测试性能，以自动识别速度慢、不可靠或最常失败的测试。

Insights 为开发人员提供了对测试执行和性能数据的有价值的可见性。提高对测试套件的健康和性能的认识可以通过消除花费在追踪未识别的 bug 上的时间和增加您对代码质量的信心来节省您的团队的时间和金钱。此外，借助 Insights，您还可以监控其他关键指标，包括信用额度使用情况、成功率和管道持续时间，这样您就可以一目了然地全面了解您的工作流程绩效。要了解更多信息，请访问[洞察文档](https://circleci.com/docs/insights/)。

## 结论

在这篇文章中，我讨论了新发布的 CircleCI 免费计划，并强调了一些将为开发者体验提供最大改进的变化。通过访问 CircleCI 强大的持续集成和交付平台上的完整功能集，您的团队可以实施快速、灵活和高效的 CI/CD 管道，从而大大缩短从提交到部署的时间。

对于希望响应用户需求并在竞争中保持领先的软件生产商来说，通过持续交付来自动化开发过程不再是可选的。要了解更多关于 CircleCI 的定价以及它与市场上其他计划的比较，请访问我们的[定价页面](https://circleci.com/pricing/)。如果你的团队还没有从一个强大的 CI/CD 解决方案所带来的时间节省和信心提升中获益，那么注册一个[免费 CircleCI 账户](https://circleci.com/signup/)，今天就开始吧。

* * *