# 持续集成对交付周期的影响| CircleCI

> 原文：<https://circleci.com/blog/continuous-integrations-impact-on-lead-time/>

毫无疑问，速度对 DevOps 很重要。但是，如果没有可靠和一致的质量，速度就没有什么意义。高速度固然很好，但是高信心也同样重要。这两种品质结合在一起，就形成了所谓的高性能 DevOps。

挑战在于知道如何衡量开发团队的表现，因为速度只是故事的一部分。一个高绩效的团队实际上是什么样子的，你如何知道你的团队与其他 DevOps 团队相比做得好不好？“快”是什么样子的？

在我们最近的报告[数据驱动的 CI 案例:实践中 3000 万个工作流揭示了 DevOps 什么](https://circleci.com/resources/data-driven-ci/)中，我们深入研究了揭示 DevOps 性能的数据和指标。在这篇博客文章和接下来的三篇文章中，我们将聚焦于被认为是描述 DevOps 性能的行业标准的四个关键指标。

我们还分享我们的运行数据，这些数据支持 DevOps 专业人员已经熟悉的关键指标，这些专业人员跟踪来源，如 [2019 年 DevOPs 状态报告](http://cloud.google.com/devops/state-of-devops/)。感谢我们从 3000 万个 CircleCI 工作流中收集的信息，我们可以充满信心地说，这些数据支持将这些指标作为成功的基准——而[持续集成(CI)](https://circleci.com/continuous-integration/) 让团队能够自动化软件交付中耗时的手动步骤，从而发挥作用。

我们是 CI 的忠实粉丝，是采用 CI 方法的 DevOps 团队的啦啦队长，这不会让你感到惊讶。根据 Puppet 的 [2016 年开发运维状况报告](https://puppet.com/resources/report/2016-state-devops-report/)，高性能开发运维团队的部署频率比其他团队高 200 倍，故障恢复速度快 24 倍，交付周期短 2，555 倍。

## CI 对交付周期的影响

在本帖中，我们将讨论前置时间:工作流从第一次触发到完成所需要的时间长度。通过“交付时间”，我们不一定意味着“部署到生产”；我们的意思是让你的工作流程达到预期的最终状态。提前期是根据任何特定工作流运行所需的时间来衡量的。

提前期是指你能多快收到信号。如果你想要一个短的交付时间，你需要尽可能最大化自动化。这就是 CI 派上用场的地方:如果您尽可能多地自动化管道，您可以将部署时间表从传统的几周和几个月缩短到几小时甚至几分钟。

为了了解观察到的开发行为如何与行业标准进行比较，我们查看了 2019 年 6 月 1 日至 8 月 30 日期间运行的超过 3000 万个工作流的 CircleCI 数据。工作流代表:

*   每天运行 160 万个作业
*   超过 40，000 个组织
*   超过 150，000 个项目

以下是我们的发现:

*   记录的最短提前时间是 2.1 秒
*   最长准备时间为 3.3 天
*   3000 万个工作流中的 80%在 10 分钟内完成
*   交付周期的第 50 百分位是 3 分 27 秒
*   第 95 百分位是 28 分钟

## 从我们的数据中有什么收获？

没有放之四海而皆准的答案:这取决于您的工作流程。在 2.1 秒内完成的工作流不会做太多事情:很可能它们是关于发送通知，或者打印和返回一条消息并返回 exit 0。我们注意到的 3.3 天的最大交付周期可能显示了大量的测试，如回归套件、集成套件，可能还有针对多个平台的交叉编译。

正如我们所说的，交付周期取决于你想要完成的目标。对于一些团队和工作流来说，28 分钟(第 95 百分位)对于等待信号来说太长了；在其他情况下，在 28 分钟内完成一个工作流程可能是一个巨大的成功。你的测试的复杂性，你正在构建的软件的类型，以及测试集成的深度，所有这些因素都会影响到交付时间。

如果你能加入任何能减少工作流程时间的优化，你就走在了正确的方向上。

## 有没有运行*太*长的工作流？还是*太*慢了？

正如我们一开始就注意到的，当速度与质量相匹配时，速度是很重要的。但是我们并不是说工作流运行三天以上的 DevOps 组织很慢。该组织可能是一个有数百个相互依赖的项目的组织，这一点没有反映在我们的数据中。

但是尽管交付时间可能因为许多原因而变化，但是与不使用 CI 的团队相比，这是交付时间的巨大减少。这就是团队使用持续集成来自动化构建和测试的原因，也是使用 CI 的团队能够比他们的同行减少四个数量级的交付时间的原因。

## CI 采用的增量价值

我们不相信工作流交付时间的通用标准。团队不应该担心达到通用基准——他们应该专注于寻找减少工作流程长度的内部机会。

采用 CI 并不是一蹴而就的，但好消息是即使有一点点帮助(而且你不必做得完美)。这是一个很好的起点:简单地采用 CI 原则就能让您踏上提高绩效的道路。

在接下来关于我们的工作流数据的三篇博客文章中，我们将分享对更多关键 DevOps 指标的见解:[部署频率](https://circleci.com/blog/why-continuous-integration-is-key-to-stepping-up-deployment-frequency/)、[平均恢复时间](https://circleci.com/blog/feedback-loops-the-key-to-improving-mean-time-to-recovery/)和[变更失败率](https://circleci.com/blog/what-does-the-change-fail-rate-tell-us-about-high-performing-teams/)。