# 坚实的数学(第二部分:溢出)

> 原文：<https://medium.com/coinmonks/math-in-solidity-part-2-overflow-3cd7283714b4?source=collection_archive---------0----------------------->

## 这篇文章是关于在 Solidity 中做数学的系列文章的第二篇。这次的题目是:**溢出**。

![](img/33814660e11413af0dd5cd97152bf7be.png)

# 介绍

每次看到`+`、`*`或者`**`在做另一个 Solidity smart 合约的审计，我就开始写下面的评论:“这里有溢出的可能”。我需要几秒钟来写这四个字，在这几秒钟里，我观察附近的行，试图找到一个原因，为什么溢出是不可能的，或者为什么在这种特殊情况下应该允许溢出。如果找到了原因，我会删除注释，但大多数情况下，注释会保留在最终的审计报告中。

事情不应该是这样的。算术运算符应该允许编写简洁易读的公式，如`a**2 + 2*a*b + b**2`。然而，这个表达式几乎肯定会引发一系列安全问题，实际代码更可能是这样的:

```
add (add (pow (a, 2), mul (mul (2, a), b)), pow (b, 2))
```

这里的`add`、`mul`和`pow`分别是实现`+`、`*`和`**`的“安全”版本的函数。

不鼓励使用简洁方便的语法，很少使用简单的算术运算符(一次不超过一个)，到处都是繁琐和不可读的函数式语法。在这篇文章中，我们分析了使事情变得如此怪异的问题，其臭名昭著的名字是:**溢出**。

# 我们在某个地方拐错了弯

有人会说，溢出总是存在的，所有的编程语言都会受到它的影响。但这真的是真的吗？你见过像为 C++、Python 或 JavaScript 实现的安全数学库这样的东西吗？你真的认为，每一个`+`或`*`都是安全漏洞，直到相反的情况被证明吗？很可能，你对这两个问题的回答都是“不”。所以，

## 为什么在坚固中溢出是如此痛苦？

> 剧透:无处可逃，无处可藏。

纯数学中数字不会溢出。人们可以把两个任意大的数相加，得到精确的结果。JavaScript、Python 等高级编程语言中数字不会溢出。在某些情况下，结果可能会变成无穷大，但至少将两个正数相加不会产生负数。在 C++和 Java 中，整数确实会溢出，但浮点数不会。

在这些语言中，整数类型确实会溢出，普通整数主要用于索引、计数器和缓冲区大小，即受所处理数据大小限制的值。对于可能超出普通整数范围的值，有浮点、大整数和大十进制数据类型，或者是内置的，或者是通过库实现的。

基本上，当算术运算的结果不符合参数的类型时，编译器可以做一些选择:I)使用更宽的结果类型；ii)返回截断的结果，并使用侧通道通知程序溢出；iii)抛出异常；以及 iv)只是安静地返回截断结果。

第一个选项是在 Python 2 中处理`int`类型溢出时实现的。第二个选项是 CPU 中进位/溢出标志的用途。第三个选项是由 SafeMath 库实现的。第四个选项是 Solidity 自己实现的东西。

第四个选项可能是最差的一个，因为它使算术运算容易出错，同时使溢出检测非常昂贵，尤其是对于乘法运算。为了安全起见，每次乘法之后都需要进行额外的除法运算。

所以，坚固既没有安全的类型，你可以跑过去，也没有安全的操作，你可以躲在后面。由于无处可逃，也无处可藏，开发人员不得不直面溢出，并在整个代码中与它们战斗。

那么，下一个问题是:

## 为什么 Solidity 没有安全类型，也没有操作？

> 剧透:因为 EVM 没有。

智能合同必须是安全的。其中的错误和漏洞会造成数百万美元的损失，我们已经从惨痛的教训中吸取了教训。作为智能合约开发的主要语言，Solidity 非常重视安全性。它有许多功能，可以防止开发者搬起石头砸自己的脚。我们指的是像`payable`关键字、类型转换限制等特性。每一个主要版本都添加了这样的特性，通常会破坏向后兼容性，但是为了更好的安全性，社区对此是容忍的。

然而，基本的算术运算是如此不安全，以至于现在几乎没有人直接使用它们，这种情况也没有改善。唯一变得稍微安全一点的操作是除法:被零除过去返回零，但现在它抛出一个异常，但即使除法也没有变得完全安全，因为它仍然可能溢出。是的，在 Solidity `int`类型中，当-2 ⁷除以-1 时，除法溢出，因为正确答案(2 ⁷)不适合`int`。所有其他操作，即`+`、`-`、`*`和`**`仍然容易上溢或下溢，因此本质上是不安全的。

Solidity 中的算术运算复制了相应的 EVM 操作码的行为，并且使这些运算在编译器级别上安全会增加数倍的气体消耗。普通`ADD`操作码花费 3 气。本文作者找到的实现安全添加的最便宜的操作码序列是:

```
DUP2(3) DUP2(3) NOT(3) LT(3) <overflow>(3) JUMPI(10) ADD(3)
```

这里`<overflow>`是溢出跳转的地址。括号中的数字是运营的天然气成本，这些数字总共为我们提供了 28 种天然气。几乎是普通`ADD`的 10 倍。太多了，对吧？看你跟什么比了。比方说，从 SafeMath 库中调用`add`函数将花费大约 88 gas。

因此，库或编译器级别的安全算法成本很高，但是

## 为什么 EVM 没有安全的算术操作码？

> 剧透:没什么好理由。

有人会说，出于性能原因，EVM 的算术语义复制了 CPU 的算术语义。是的，一些现代 CPU 有[操作码](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions)用于 256 位算术，然而主流 EVM 实现似乎不使用这些操作码。Geth 使用 Go 编程语言标准库中的`big.Int`类型。这种类型实现了由本机字数组支持的任意宽的大整数。奇偶校验使用[自己的库](https://github.com/paritytech/parity-common/blob/master/uint/src/uint.rs)在本机 64 位字的基础上实现固定宽度的大整数。

对于这两种实现，算术溢出检测的额外成本几乎为零。因此，一旦 EVM 有了算术操作码版本，溢出时恢复，他们的天然气成本可以与现有的不安全版本相同，或略高。

更有用的是根本不会溢出，而是返回整个结果的操作码。这种操作码将允许在编译器或库级别有效地实现任意宽的大整数。

我们不知道为什么 EVM 没有上述操作码。可能只是因为其他主流虚拟机没有吧？

到目前为止，我们一直在谈论真正的溢出:计算结果太大而不适合结果数据类型的情况。现在是时候发现问题的另一面了:

# 幻象溢出

如何计算 3%的 *x* 的实度？在主流语言中，人们只写`0.03*x`，但是实性不支持分数。那`x*3/100`呢？嗯，这在大多数情况下都行得通，但是如果 *x* 太大，以至于`x*3`会溢出怎么办？从上一节我们知道该怎么做，对吗？使用 SafeMath 的`mul`就可以了，保险起见:`mul (x, 3) / 100` …不要那么快。

后一个版本更安全，因为它返回前一个版本返回的错误结果。这很好，但是…为什么计算 3%的东西会溢出呢？无论是名义价值还是绝对价值，某样东西的 3%肯定会低于其原始价值。所以，只要 *x* 适合 256 位字，那么 *x* 的 3%应该也适合，不是吗？

嗯，我称之为“幻影溢出”:最终计算结果适合 result 数据类型，但一些中间操作溢出的情况。

幻像溢出比真实溢出更难检测和解决。一种解决方案是对中间值使用更宽的整数类型甚至浮点类型。另一种方法是重构表达式，使幻像溢出成为可能。让我们试着用我们的表情去做后者。

算术法则告诉我们，下面的公式应该产生相同的结果:

```
(x * 3) / 100
(3 * x) / 100
(x / 100) * 3
(3 / 100) * x
```

然而，实度中的整数除法与纯数学中的除法不同，因为在实度中，它将结果四舍五入为零。前两种变体基本等价，都有幻影溢出的问题。第三种变体没有幻像溢出问题，但是有点不太精确，特别是对于小的 *x* 。第四种变体更有趣，因为它意外地导致了编译错误:

```
browser/Junk.sol:5:18: TypeError: Operator * not compatible with types rational_const 3 / 10 and uint256browser/Junk.sol:5:18: TypeError: Operator * not compatible with types rational_const 3 / 10 and uint256
```

我们已经在上一篇文章中描述了这种行为。为了编译第四个表达式，我们需要像这样修改它:

```
(uint (3) / 100) * x
```

然而，这没有多大帮助，因为校正后的表达式的结果总是零，因为`3 / 100`向零舍入是零。

通过第三个变体，我们设法以精度为代价来解决幻影溢出问题。实际上，精度损失只对小的 *x* 显著，而对大的 *x* 可以忽略不计。请记住，对于原始表达式，幻影溢出问题仅在大的 *x* 时出现，因此看起来我们可以像这样组合两种变体:

```
x > SOME_LARGE_NUMBER ? x / 100 * 3 : x * 3 / 100
```

这里`SOME_LARGE_NUMBER`可以计算为(2 ⁵⁶-1)/3，并将该值向下舍入。现在，对于小的 *x* 我们使用原始公式，而对于大的 *x* 我们使用不允许幻影溢出的修改公式。看起来我们现在解决了幻影溢出问题而没有显著的精度损失。干得好，对吧？

在这种特殊情况下，可能是的。但是如果我们需要计算的不是 3%，而是 3.1415926535%呢？公式是:

```
x > SOME_LARGE_NUMBER ?
x / 1000000000000 * 31415926535 :
x * 31415926535 / 1000000000000
```

我们的`SOME_LARGE_NUMBER`将变成(2 ⁵⁶-1)/31415926535.没有那么大。而 3.1452653589793238462643383279%呢？这种方法适用于简单的情况，但似乎不能很好地扩展。

# 结论

EVM 不提供溢出保护的操作码。Solidity 在编译器级别不提供任何溢出保护。因此，智能合约开发人员必须在代码级别解决溢出问题，这使得代码很麻烦，效率也很低。

幻像溢出更难检测和解决。直截了当会导致折衷，且通常无法扩展。

在我们的下一篇文章中，我们将提出解决幻影溢出问题的更好的方法，我们下一篇文章的主题将是: [**百分比和比例**](/coinmonks/math-in-solidity-part-3-percents-and-proportions-4db014e080b1) 。

本系列的其他文章:

*   [第 1 部分:数字](/coinmonks/math-in-solidity-part-1-numbers-384c8377f26d)
*   [第 3 部分:百分比和比例](/coinmonks/math-in-solidity-part-3-percents-and-proportions-4db014e080b1)
*   第四部分:复利
*   [第五部分:指数和对数](/coinmonks/math-in-solidity-part-5-exponent-and-logarithm-9aef8515136e)

> [直接在您的收件箱中获得最佳软件交易](https://coincodecap.com/?utm_source=coinmonks)

[![](img/7c0b3dfdcbfea594cc0ae7d4f9bf6fcb.png)](https://coincodecap.com/?utm_source=coinmonks)[![](img/e9dbce386c4f90837b5db529a4c87766.png)](https://coincodecap.com)