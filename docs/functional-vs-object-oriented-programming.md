# 函数式与面向对象编程| CircleCI

> 原文：<https://circleci.com/blog/functional-vs-object-oriented-programming/>

编程既是一门科学，也是一门艺术。个人偏好在决定你的编程风格方面起着很大的作用，所以当你发现自己在和一个同龄人争论时，你可能不会感到惊讶。一个正在进行的争论是在两个不同的编程范例之间的选择，这两个范例被称为**函数式编程**和**面向对象编程**。哪个更好？你应该使用哪一个？

双方的支持者都会告诉你，他们最喜欢的范式提供了一些几乎普遍适用的明显优势。你可以说这要视情况而定。在本文中，我们将着眼于这两种选择，并试图从事实中提炼出神话。目标是更好地理解这些编程方法，并准备在有意义的时候使用它们。

## 函数式编程

**函数式编程(FP)** 是最古老的编程种类之一，甚至可能是最古老的。它定义了一个构建完全依赖于函数的软件的过程。在 FP 中，开发人员编写函数来创建新函数，编写应用程序来避免共享状态或可变数据等问题。为了实现这一点，开发者经常声明性地使用 FP，而不是强制性地使用。

这意味着什么呢？

### 函数式编程中的关键概念

首先，理解函数在 FP 中是一等公民是很重要的，这意味着它们和其他任何值一样被对待。它们可以作为参数传递或从其他函数返回。返回函数的函数称为**高阶函数**。这些高阶函数使得直接从参数构造新函数成为可能。

第二个要点是不变性的概念。不可变的值是原始值，不能改变。像数字这样的值被认为是不可变的。您不能将 42 更改为 14。您只能创建一个值为 14 的新数字，并将其分配给之前使用的变量。但是新的 14 号不会影响你之前使用的 42 号。

虽然这种值处理对于诸如数字之类的原语是有意义的，但是对于诸如对象或数组之类的组合值来说可能感觉很奇怪。然而，FP 原则将所有的值都视为不可变的。更改值的唯一方法是创建一个新值，可能会使用旧值作为基值或副本。

不可变数据类型的使用允许 FP 使用**纯函数**。这些函数仅由其参数定义。因为参数不能改变，所以保证它们的行为是可预测的。同样的论点给出同样的结果。其他编程方法不能保证这种可预测的行为。

### 函数式编程的用例

尽管 FP 最初主要用于科学应用，但它在各种领域越来越受欢迎。例如，在 web 开发中，一个名为 [React](https://circleci.com/blog/continuously-testing-react-applications-with-jest-and-enzyme/) 的用户界面(UI)库利用 FP 原则变得声明性和易于处理。该库提倡使用不可变的状态对象(值)来反映应用程序的当前状态，而不进行更改。当开发者想要一个新的状态时，他们必须创建一个新的对象。这种方法的美妙之处在于，您可以追溯 UI 中的每次更改。所有先前的状态仍然未被触及并且可用。

虽然 FP 的根源当然是在计算机科学的学术方面，但是它的实际含义可以追溯到像 Lisp 或 Scheme 这样的语言。这些特性中的一些被融入了 JavaScript 语言，这是 FP 继续使用的一个关键因素。然而，有些语言是建立在 FP 原则之上的:F#、Clojure 和 Elixir 都是比较流行的语言。在学术界，Haskell 几十年来一直被认为是主流语言。

## 面向对象编程

函数式编程已经存在很长时间了，但是一些开发人员认为面向对象编程(OOP)更加传统。像 Smalltalk 或 Objective-C 这样的编程语言普及了 OOP，OOP 是在 20 世纪 70 年代末发明的。后来，C++、Java 和 C#继续将这种编程风格硬植入大多数开发人员的头脑中。

请继续阅读 OOP 中重要原则的描述和一些最常见的用例。

### 面向对象编程中的关键概念

在 OOP 中，开发人员将软件应用程序建模为可以相互通信的**对象**的集合。每个对象的接口都是一个**类**，一个指示函数和值可以被任何实例访问的模板。虽然这种通信能力最初被设想为允许网络通信或异步 IO 的消息传递，但后来它作为在相应对象上调用的简单函数而普及。这样的功能被称为**方法**。

与 FP 中的不可变对象不同，OOP 中的对象变异是游戏的一部分。因此，调用一个方法很可能也会改变对象的一些值。

许多开发人员仍然使用 OOP 的一个原因是，它是强制性编写的，尤其是在教授编程的时候。这意味着开发人员很清楚在哪里发生了什么。相反的观点是，即使使用这种命令式风格，也很难确定单个对象的当前状态。由于可变性，这可能会很快导致不可预见的后果。

### 面向对象编程的用例

传统上，开发人员用面向对象的方法制作了几乎所有的用户界面。这也相对简单，因为基于类的组件可以从另一个类似的组件继承它的基本结构(字段和方法)。例如，日期输入字段可以从文本输入字段继承，文本输入字段从输入框继承，输入框从控件继承。使用这种基于继承的方法，您只需要指定额外的方法，并在一些现有的方法上重新实现行为。例如，不需要再次编写键盘或鼠标处理的逻辑。

今天，OOP 是所有通用编程语言的必备特性。甚至基于 FP 的语言如 F#也直接支持 OOP 特性，如类或继承。一个很好的例子是 JavaScript，它没有马上加入标准特性，比如类或继承，而是在最近的版本中加入了它们。

正如我们已经发现的那样，这两种编程方法差异很大，足以证明在适当的时候使用这两种方法是正确的。那么如何在二者之间做出选择呢？以下是一些论据。

## 函数式编程与面向对象编程:争论

正如已经讨论过的，这两种方法各有利弊。计算机科学教授 Norman Ramsey 在著名的 T2 堆栈溢出答案 T3 中提供了一个有用的观点。他认为，当所有对象都是已知的，但行为可能会改变时，FP 会表现出色。相比之下，当行为已知时，OOP 是很棒的，但是实际的数据类型可能会改变。

双方的粉丝都不止这些。例如，FP 的追随者认为以纯 FP 风格编写的设计简洁的软件易于调试，并且永远不会崩溃。他们告诉你，FP 立刻给你带来了测试驱动开发的一些优势，严格应用了所有 T2 坚实原则的 OOP 本质上是 FP。虽然 SOLID 确实导致了类似于 FP 的大多数的个体函数，但是它不一定非得*是* FP。例如，没有坚实的原则禁止数据突变。

热爱 OOP 的开发人员可能会因为性能或简单性的权衡而忽略一些 FP 的好处。当您只想更改单个字段时，为什么要将一个对象的所有字段复制到一个新对象中？为什么有一百万个元素的数组需要一个副本来设置一个元素？当然，您可以使用一些模式来避免制作副本，但是您仍然需要专门的数据结构。与开发人员多年来独立于 OOP 使用的直接方法相比，这里的间接程度可能令人困惑。

虽然这些方法之间有一些非常鲜明的对比，但它们也可以是互补的。没有法律禁止在软件应用程序中使用类。也没有法律规定应用程序的一般状态是可变的。

## 展望未来

几乎所有流行的编程语言都是**多进制**。它们都支持 FP，允许传递函数，或者拥有处理数据对象不变性的助手。它们还附带了面向对象的特性，比如类或继承。无论哪种方式，这种多半径方法都将继续存在。从用户的角度来看，有更多的选择几乎总是更好。

总的来说，更倾向于 FP 友好的特性似乎是可能的。通过引入对克隆数据对象、函数引用和函数组合的额外支持，语言变成了一个很好的伴侣，甚至超越了 FP。在像 C#这样的语言中，FP 友好的特性为 OOP 特性提供了一个极好的补充。这种组合甚至在 OOP 开发的应用程序中也很方便，比如当您使用某些辅助函数时。

混合 FP 和 OOP 方法的缺点是学习曲线。有些人就是因为这个原因而避免使用 C#。最初作为 Java 的一个原始的、设计优雅的替代品，最终感觉更像是一个复杂的 C++怪物。

OOP 当然不会消失，但最有可能的结果是它会找到自己的位置，与 FP 共存。诚然，[副作用](https://en.wikipedia.org/wiki/Side_effect_(computer_science))自由开发的理想在实践中几乎不可能实现。将日志消息写入控制台已经有副作用了。开发者必须首先发现并打开 FP 的实用性。现在开发者已经开始认识到 FP 的实用性，几乎没有理由再把 FP 的特性锁在外面。

### 对面向对象编程的持续支持

在这种背景下，为什么 OOP 仍然是一个可行的选择？OOP 有价值，因为它本质上是理想的工具。几乎没有什么是开发人员不能通过 OOP 实践建模的。开发者甚至可以通过 OOP 对大多数 FP 特性进行建模。

例如，考虑像传递或组合函数这样的基本事情。简而言之，这就是[仿函数](https://en.wikipedia.org/wiki/Functor)或[委托](https://en.wikipedia.org/wiki/Delegation_(object-oriented_programming))所提供的。它只是一个对象，对应一个类，只有一个方法。

### 寻找共同点

很少有开发团队会仅仅为了从一种方法切换到另一种方法而改变他们的软件或编写应用程序的方式。对于一个团队来说，更有可能的是积极地重构他们的一些最基本的应用程序，以使用他们的编程语言的更新的特性。

不管怎样，未来看起来越来越混合。在未来的某个项目中，你可能会发现自己在 OOP 应用程序中使用了更多受 FP 启发的风格，或者在 FP 驱动的应用程序中使用了一些 OOP 特性。

## 结论

某些类型的应用程序偏爱 FP(比如编译器)，而其他的应用程序更适合使用 OOP 原则(比如经典的桌面应用程序)。选择正确的编程方法取决于几个因素，比如目标编程语言、框架和您正在构建的应用程序类型。使用你觉得最舒服的，但不要忘记继续学习增加你的工具。解决问题时有大量的选择总是有益的。