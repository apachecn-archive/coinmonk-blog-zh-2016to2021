# 区块链螺母和螺栓:第 1 部分

> 原文：<https://medium.com/coinmonks/blockchain-nuts-and-bolts-part-1-e6afb4602f19?source=collection_archive---------0----------------------->

关于区块链，可能有成百上千种解释。有些真的很好，有些，嗯，你知道。既然我对区块链的定义倾向于得到积极的回应，我想为什么不把它们提供给更广泛的受众。如果你刚到区块链，或者只是想换个视角，这篇文章可能会派上用场。

让我们从你现在使用的东西开始:互联网。您有一个 web 浏览器，它连接到一个由 Medium Inc .运营的服务器。浏览器向该服务器请求数据，服务器返回浏览器以图像和文本的形式呈现和显示给您的字节。很简单。

幕后发生的事情对你来说是透明的:HTTP。当浏览器向服务器请求数据时，它必须使用服务器和浏览器都能理解的语言。这就是 HTTP:浏览器和服务器之间的一个标准化的通信*协议*。它允许我们一般性地构建 web 应用程序，而不必担心网络协议之类的底层细节。

我真的很感激在我们之前出现的巨人的贡献，因为如果我必须处理底层网络协议来构建一个应用程序，那么，我将花费大量的时间和精力来确定与哪个网络对话，在那个网络中与什么机器通信，以及使用什么协议。 ***啊哈！现在我正在准确地描述我们在区块链年轻历史中的位置。***

## HTTP 类比

在 HTTP 和浏览器出现之前,“互联网”并没有真正的互联。有几种网络和协议在发挥作用，直到社区最终确定了一套标准协议，如 TCP/IP 和 HTTP([https://en.wikipedia.org/wiki/History_of_the_Internet](https://en.wikipedia.org/wiki/History_of_the_Internet))。

如果你足够斜视，你可以说这种区块链进化实际上只是另一种互联网。除了，它没有交换 HTML 和图像数据(还没有)；它在交换交易数据。更具体地说，事务数据被组织成称为“块”的组。有许多网络使用不同的格式和协议发送这些数据块。这类似于互联网的早期——非常早期；就像 1960 年代早期。每当你听到关于区块链的消息时，请记住这一点——这很复杂，因为它仍然是一片混乱。但早期的互联网也是如此。

> 区块链有点像互联网；除了不是交换 HTML 和图像数据，而是交换事务数据

既然我们真的过度简化了概念，为什么不用我们已经理解的术语继续解释呢？假设我们使用互联网浏览器来查看互联网服务器提供的内容。区块链的情况相当于，我们用区块链的钱包观看区块链 T2 矿商生产的内容。和浏览器一样，钱包是区块链面向用户的元素。像服务器一样，挖掘器以块的形式生成数据。但是在互联网上，浏览器有办法找到服务器索要数据。钱包如何在区块链网络上找到矿工？

一个区块链钱包依靠一个*客户端*来执行与一个区块链矿工互动所必需的路由和联网。就像路由器位于浏览器和服务器之间一样，区块链客户端位于钱包和一个或多个矿工之间，以处理发现和网络协议。

> 区块链钱包与客户端交互，客户端与矿工通信以交换交易数据

如前所述，钱包是区块链面向用户的组件。它的主要目的是允许用户使用只有该用户才能访问的私钥授权并向网络提交交易。我们将在后面更详细地介绍钱包；现在，让我们解决这个关键问题…

## 公钥和私钥

当我们想到钥匙时，我们会想到我们随身携带的用来开门的小金属物。每把钥匙都有适合锁槽的小凹槽。插槽和凹槽必须对齐，钥匙才能工作。公钥和私钥是相似的，因为一个的槽必须适合另一个的槽。但是有一种数学拟合代替了机械拟合。

关于这些密钥，你唯一需要知道的是，公钥和私钥是成对的。如果您使用公钥对某些内容进行编码，那么它只能通过其私钥来读取。如果你用公钥对某些东西进行编码，那么只有用私钥才是可读的。

毫无疑问，你会在区块链听到“签约交易”的说法。这基本上意味着将一些事务位与来自私钥的位一起通过数学函数运行，以生成一组新的位，称为“签名”。然后，该签名可以与公钥一起进行数学分析，以确定实际上是否使用了公钥的私钥副本来生成该签名。这样，提交给网络的每一个交易签名都被认证为已经由私钥所有者签名，因此是交易的作者。这就是区块链安全的本质:没有通过这个签名测试的交易会被网络拒绝。而且，有人重构他人私钥的可能性是如此的不可思议，以至于你可能会说这是不可能的。

# 矿工

那么谁来验证这些签名呢？这是矿工的工作。在将交易包含在块中之前，它们使用交易发送者的公钥/地址来验证嵌入的签名。挖掘器是区块链网络中最关键的部分，因为它的工作是验证所有这些交易，并将它们分成块。因为它非常关键，所以很容易被欺骗。我们如何知道这些矿工是否不允许账户重复支出或忽略一些交易？

每个矿工都必须向电视网证明，如果他们作弊，他们会有所损失。实现这一点的方法越来越多，但最常用的是工作验证(PoW)算法。使用 PoW，矿工必须解决非常复杂的数学问题。这不是你可以在台式机或笔记本电脑上解决的那种数学，这需要大量的 CPU 能力，这转化为电能，这转化为金钱。当他们解决这个数学问题时，他们将解决方案与事务块一起作为他们花费资源创建这个新块的证据。如果他们作弊，他们只是白白花了一大笔钱做这道数学题！那么作弊是怎么被检测出来的呢？

## 散列法

当一个挖掘者构建一个事务块时，它必须为每个块生成一个“头”。这个报头由几个部分组成，但是其中一个关键部分是它的“散列”。正如约翰·奥利弗在他的《区块链》一集中强调的，哈希有点像把鸡肉变成鸡块。挖掘器在数学函数的帮助下将比特混合在一起，以产生更小的比特集合。这是一个单向函数…你不能逆转这个过程，就像你不能从一个鸡块再生出一只鸡一样。那么块的散列中包含什么呢？

要包含在新块中的每个事务都通过这个数学函数运行，以便为每个事务生成一个散列。来自这些散列的位以及前一个块的散列通过数学函数运行，以生成在新块头中使用的新散列。改变进入数学函数的这些位中的任何一位都会极大地改变输出位。因此，我可以通过运行相同的事务和以前的数据块，使用相同的数学函数来验证是否有任何更改，并比较哈希值。如果哈希值不同，我会立即知道发生了变化。因为每个数据块的标头都由该数据块内的数据和前一个数据块的标头组成，所以这些数据块通过这些哈希值“链接”在一起，因此称为“数据块链”。

## 竞赛

不是只有一个矿工在做这些工作；有成千上万个。他们每个人都在比赛解决数学难题，并声称有权创建这些新块之一。他们为什么要这么做？当然是钱！

每笔交易都包含一笔小额费用，激励采矿者实际验证交易并将其包含在区块中。此外，该网络通常会奖励矿工一定数量的货币，每产生一个区块。例如，在比特币中，每块价值 12.5 BTC(今天的价值约为 9.8 万美元)。在以太坊，每个价值 5 ETH(价值约 2400 美元)。根据市场价格，这可能非常有利可图；但是计算起来也非常昂贵。

在继续讨论第 2 部分中的客户机之前，我将在这里停下来，让大家理解一些内容。

一些人认为区块链目前使用的算法是可以破解的。时间旅行在理论上也是可能的，但没人做过。每天都有数百万黑客试图攻破区块链。这并不是说它永远不会发生，但由于密钥生成的复杂性，这种可能性很小。

> [在您的收件箱中直接获得最佳软件交易](https://coincodecap.com/?utm_source=coinmonks)

[![](img/7c0b3dfdcbfea594cc0ae7d4f9bf6fcb.png)](https://coincodecap.com/?utm_source=coinmonks)