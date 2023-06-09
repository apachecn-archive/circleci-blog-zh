# 如何建立工程师的自信| CircleCI

> 原文：<https://circleci.com/blog/how-to-build-confidence-as-an-engineer-an-interview-with-rob-zuber-circleci-cto/>

在这个系列中，我们把工程部门的人拉到一边来谈论信心。从技术高管到工程、管理和站点可靠性领域的团队成员，我们都想知道“信心”对他们意味着什么，以及在他们的职业生涯中，信心发生了怎样的变化。你可以阅读该系列的其他五篇帖子，分别是迈克尔·斯塔克、[斯蒂格·布劳塔塞特](https://circleci.com/blog/how-to-build-confidence-as-an-engineer-an-interview-with-stig-brautaset-circleci-staff-software-engineer/)、[格伦·梅勒](https://circleci.com/blog/how-to-build-confidence-as-an-engineer-an-interview-with-glen-mailer-circleci-staff-software-engineer/)、[雅克·加西亚](https://circleci.com/blog/how-to-build-confidence-as-an-engineer-an-interview-with-jacque-garcia-circleci-software-engineer/)和[迈克·马尔克斯](https://circleci.com/blog/how-to-build-confidence-as-an-engineer-an-interview-with-mike-marquez-circleci-senior-release-engineer/)。

在这次采访中，我们采访了 CircleCI 的首席技术官 Rob Zuber。我们希望你喜欢它。

* * *

### 作为一名工程师，自信对你意味着什么？

嗯，有对正确性的自信，也有对设计的自信。正确性是:我有足够的信心来交付这个吗？这就是 CI/CD 的用武之地。对我代码正确性的信心实际上在我之外:我已经把它外包出去了。通过请求测试系统来验证它，我可以确信它会工作。当然，我可以增加我的覆盖范围和所有这些事情，这将给我更多的信心。

然后我有信心，我在如何实现一些东西方面做出了正确的选择，在良好的抽象和设计等方面。这是我内心深处的想法。

随着时间的推移你会学到这一点。我认为学习不仅仅是有更多的想法，它是关于识别模式和观察事情如何发展，所以你可以有信心事情会足够好。如果我能接受我对自己正在做的事情足够自信，那么我就能继续下一件事。

> 学习不仅仅是有更多的想法，而是识别模式，观察事情如何发展

我认为这实际上是建立自信最具挑战性的部分之一。我喜欢谈论风险，知道一些事情是非常重要的，因此，我已经付出足够的努力去做足够的工作或做足够重要的事情。或者知道这是一个至关重要的系统，我会做更多的事情来变得更加自信。

在决策过程中，我们从决策模型的角度来讨论这个问题，我们试图在工程中建立决策模型。影响是什么，影响的范围是什么，扭转决策的代价是什么？在这一点上，你会有不同的观点，你会包括更多的顾问和更多的利益相关者来做出决定。

### 在你的职业生涯中，自信心发生了怎样的变化？

关于建立模式库，我想了很多。只是一个我可以反思的经验库。我喜欢超级怪异的类比，所以我为此道歉:

想想攀岩。当人们开始在顶绳上攀岩时，他们超级抓地力。比如，“如果我摔倒了会发生什么？”然后你倒下了，你倒下了三英寸。你会想，“哦，这没什么大不了的。”现在我真的可以去尝试一些事情了:我可以跳到另一个点，做一些更大的事情，因为我知道我会落下一英尺。然后你去攀岩，那完全是另一回事，但是你第一次攀岩就意识到，“哦，这其实没什么大不了的。”

所以我认为经历“灾难”[你害怕]实际上是一个巨大的信心建立者，因为你基本上对将要发生的事情感到舒适。在那之前，它是一个幽灵。是对未知的恐惧。但是一旦你经历过，你就会知道，“哦，我们知道如何解决这个问题。这很难，但我们都是聪明人，我们会解决的。”如果你总是试图不失败，那么你永远不会做大事。你永远不会去推动，因为推动往往看起来像失败。

> 我认为经历“灾难”[你害怕]实际上是一个巨大的信心建立者，因为你基本上对将要发生的事情感到舒适。

### 就信心而言，工具化或自动化如何改变了你与代码的关系？

它改变了一切。我可以构建一个包装器来测试我想要证明的东西，然后我就可以确定它是正确的。以前，我会将它构建到一个大型复杂系统中，然后尝试找到一个大型复杂的方法来手动完成这件事，并创建所有会导致这段代码得到验证的场景。

把它隔离到我正在做的事情上，这样一个键一个键地敲，我就能知道它是否正确。就对我所构建的东西的信心而言，自动化测试是巨大的。

快速部署让我有信心从某些事情中恢复过来。因此，如果我犯了一个错误，或者如果某些东西进入了生产环境，无论是因为我们发布了一些糟糕的代码，还是因为客户以一种以前没有使用过的方式使用它，我们发现了一个问题，这种快速从错误中恢复的能力——因为我知道我可以修复它，并推动修复，使其真正快速地进入生产环境——这是一个游戏规则改变者，对吗？

当我们开始丰富，吉姆[罗斯]说，“我们应该做连续部署。”我马上说，“这听起来像是有人在部署坏了的时候不需要修理它。不，这是个糟糕的主意。部署是可怕的，我们将整夜不眠，这是非常高的风险，我不想一直这样做，我想睡觉。”然后我读了些书。实际上，就在那一刻，我开始思考风险概况、风险缓解和理解我的行动的风险，通过将大量工作结合在一起，我正在创造更大的风险，这是所有部署挑战的驱动因素。通过将它分成小块，我实际上降低了我的风险，隔离了一个小错误，这将是一个小错误，我们会理解它。

> 第二天早上我回来说，“这就是我们正在做的。我们正在进行持续部署。”我们开始建立系统来做这件事，并且从不回头。

### 关于自信有什么最后的想法吗？

嗯，另一件事是建立一些东西，并在同一天把它放在你的客户面前…它创造了…我想说它创造了霸气？突然间，我成了一个做事的人。我对此感觉很好，我知道我有这个能力，因为我知道这是经过测试的。

进步的感觉很充实，给你一种“我擅长我所做的事情”的感觉。我在为顾客修理东西”或“我在制造顾客使用和喜爱的东西。”我认为这是一种非常不同的自信。但这是一种非常强大的自信。我只是对自己和我能实现的事情感觉良好，这让我想做得更多。这让我想变得有效率，这很令人兴奋。那篇论文掩盖了很多问题。当你觉得你可以把事情做完，你在传递价值，你和使命联系在一起。

因此，我认为这可能是我从未回顾持续部署的原因。就好像，我再也不想等着把东西送到顾客手中了，因为那太痛苦了。

### 你会给年轻时的自己什么建议？

我想说，学习是在失败中进行的。这个问题的有趣之处在于，我认为人们会希望回到过去，从错误中拯救自己，但如果我没有犯下我职业生涯中犯下的所有错误，我不知道我现在是否能够做好我的工作。失败是重要的，但关于失败的关键是反思它们，不是停留在它们上面，而是反思它们，因为在每一次失败中，你都会学到一些东西。

是啊，这是一个奇怪的。我想只是:享受旅程，因为它会很乱，会很粗糙，但这就是你学习的方式。

* * *

*注册[试试 CircleCI](https://circleci.com/signup/) 并开始对你的代码建立信心*