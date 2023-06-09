# 准备创建自己的加密货币！！！

> 原文：<https://medium.com/coinmonks/how-to-create-my-own-cryptocurrency-84eb1246e39f?source=collection_archive---------0----------------------->

## **第一部分:简介**

![](img/008c215c5236905aeb0488689b610cb4.png)

在创造你自己的加密货币之前，我有一个问题要问你。你给你的加密货币取名字了吗？很酷吗？。因为没人愿意在麦当劳对面的‘swar na bakery’(一家面包店的名字)吃汉堡。所以明智地选择你的。

有许多加密货币，有些你可能知道，如比特币、以太坊等，你也会听说区块链这个名字，它是区块链背后的技术，最有价值的加密货币是比特币，截至 2010 年 3 月价值约 0.003 美元，但现在(2020 年 10 月 3 日)价值 10542 美元，你能相信吗！！！！…

这个博客是一个介绍性的部分，不包括任何编码，所以只要把手从按键上拿开，享受滚动。

因此，如何开始有许多术语，如

*   区块链
*   密码术.密码术的类型.数字签名
*   散列法
*   节点
*   分类帐-超分类帐
*   Merkle 树
*   智能合约等。等。

阿哈:这太长了，别担心，我不会在这个博客中透露，我们会看到它会让我对我即将推出的博客感兴趣。正如我所说的，我们将会看到一些你听说过但并不深入了解的事情。

我给大家讲一个**只有少数人知道的故事，** **加密货币是作为另一项发明的副产品出现的，** [**比特币**](https://blockgeeks.com/guides/what-is-bitcoin-a-step-by-step-guide/) 的不知名发明者中本聪，从未打算发明一种货币。他的目标是建立一个分散的数字现金系统。在 90 年代，创造数字货币的尝试失败了很多。

> **宣布首次发行比特币，这是一种新的电子现金系统，使用点对点网络来防止重复消费。它是完全分散的，没有服务器或中央机构。——中本聪，2009 年 1 月 9 日，在 SourceForge 上发布比特币。**
> 
> ***…经过十多年基于可信第三方的系统(Digicash 等)的失败，他们认为这是一个失败的事业。我希望他们能做出区分，这是我第一次知道我们正在尝试一个基于非信任的系统。—中本聪在给达斯汀·特拉梅尔的一封电子邮件中***

当 Satoshi 试图建立一个没有中央实体的数字现金系统时，加密货币诞生了。

让我用一个简单的例子来解释现在存在的系统和 satoshi 发明的系统。让我们以金额交易为例，我在银行有一个账户，我从一个账户到另一个账户进行交易，这个交易历史记录保存在银行拥有的中央服务器中，对吗？如果有什么不好的事情发生。让我们猜测我们的坏，一些黑客改变交易金额为 10000，而不是 1000，并采取了所有 9k 的金额，然后我怎么能证明我被黑客攻击，这将清楚地记录为 10K 那里，但我只做了 1K 的交易。

现在想象一下这样一种情况，您的交易证明存储在许多分散的服务器中，如果黑客试图更改服务器中的数据，那么只有该服务器中的数据会被更改，但在其余的所有服务器中，原始数据会被保留，这样我们就可以发现该服务器中发生了错误，其操作将被回滚……这就是区块链大家好！！

# 什么是加密货币(也许是未来的货币)？

如果我们去除所有关于加密货币的宣传，看看这个词，它只是你账户中的一个数字，当你检查你账户中的余额时，它会被附加上货币的名称(美元、欧元、印度卢比等)，而加密货币会被附加上比特币、以太坊等。加密货币是数字现金，旨在比我们政府发行的货币更快、更便宜、更可靠。用户之间直接交易，自己存钱，而不是委托政府创造货币，委托银行存储、发送和接收货币，因为没有中间人，交易速度非常快，而且负担得起。加密货币的每个用户都可以同时记录和验证自己的交易和其他所有人的交易。数字交易记录被称为**分类账**，这个分类账对任何人都是公开的。有了这个公共分类账，交易变得高效、永久、安全和透明，从而防止欺诈和操纵。有了分类账，即公共记录，加密货币不需要你信任银行来保存你的钱。这个系统不需要信任。这种独特的积极品质被称为“不信任”。

# 比特币是什么？

比特币是 2009 年由一个名叫中本聪的未知个人或团体创造的第一种数字现金。比特币是独一无二的，因为它不依赖政府/银行创造的货币，这意味着没有银行或中间人。此外，交易直接发生在不知道真实姓名的人之间。每一笔交易都被记录在公开的数字记录中，由世界各地被称为**区块链**的许多人保存。因为有如此多的副本被同时维护，所以交易非常安全，几乎不可能被操纵。个人使用他们的数字钱包保护他们的比特币

# 什么是区块链？

区块链是一种用于创建永久、安全的去中心化数字记录的技术。区块链可以记录任何信息，如医疗信息、银行信息等。把区块链想象成一本记录的书。那本书的每一页都是一块积木，可以记录任何东西。块被一个接一个地创建，通过我们所知的区块链的散列方式彼此链接。多个区块链记录由许多不相关的个人和他们的电脑同时维护，这使得云存储变得异常活跃。可以立即看到更新，操作极其困难/不可能。许多人保留自己的区块链拷贝，这种积极的品质被称为“分发”。但是，如果一个区块链不是分布在许多个人之间，而是由一个政府、组织、团体或个人管理，那么它就根本不是一个区块链。像那样的中央系统只是一个数据库。

# 什么是智能合同？

智能合同将区块链技术与合同相结合，打造一个更高效、更实惠的商业体系。在智能合同中，两个做生意的人同意用钱交换其他东西。如果合同双方设定的要求在某个日期得到满足，它就会激活，交付所购买的东西。如果不满足要求，契约将停用并返回它存储的任何内容。

例如，爱丽丝想要鲍勃的 1 个比特币，鲍勃想要 11000 美元。鲍勃和爱丽丝都同意在 2020 年 10 月 7 日，比特币和现金都将被存入与智能合同相关的账户。10 月 7 日，合同看双方是否履行了义务。如果是这样的话，它会将支付款和比特币释放给它们的新主人。如果没有，比特币和钱将被归还给它们原来的主人。

因为合同是公开的且不可更改的，所以很容易让 Bob 和 Alice 对他们的交易负责。如果有人以某种方式违反协议，他们应该做什么的证据很容易获得。

# 什么是采矿？

挖掘是记录和验证被称为区块链的数字记录上的信息的计算机过程。因为采矿需要计算机能力，所以人们做这项工作来换取金钱。完成这一过程的每一台计算机都可以获得数字货币奖励，有时还可以获得全新的处女硬币。

为了保持区块链网络平稳运行，一次只能创建一个块。有几种不同的方法可以做到这一点:

1.  最常见的是工作证明，它要求计算机努力解决一个数学问题。解决这个问题的第一台计算机会发现一个新的区块，并记录区块链的信息。这为他们赢得了全新的数字货币奖励，外加每笔交易的费用。
2.  下一个采矿技术被称为证据。在这个系统中，软件会选择拥有大量硬币的人来制作新的积木。参赛的人是通过抽签系统随机选出的。有了赌注的证明，就没有新的硬币被创造出来。取而代之的是收取交易验证和记录费用。

随着每月超过 1000 种加密货币和更多的加密货币被创造出来，新的挖掘方式正在被探索和发现。

你可以找到下一部分创建块和[链接在一起，以创建一个区块链](/@ananthkrish1998/part-2-how-to-create-your-own-cryptocurrency-a4726d24c5ce)。

以上内容参考了网上的各种文章和资源，图片来源于[这里](https://worldview.stratfor.com/sites/default/files/styles/article_full/public/cryptocurrency-gulf-display-shutterstock-1028639176.png?itok=K36RQG5A)

请给我的博客打 0 到 50 分，并在下面评论给我改进的建议。感谢您宝贵的时间阅读我的博客。祝您愉快:)

## 另外，阅读

*   最好的[密码交易机器人](/coinmonks/crypto-trading-bot-c2ffce8acb2a)
*   [密码本交易平台](/coinmonks/top-10-crypto-copy-trading-platforms-for-beginners-d0c37c7d698c)
*   最好的[加密税务软件](/coinmonks/best-crypto-tax-tool-for-my-money-72d4b430816b)
*   [最佳加密交易平台](/coinmonks/the-best-crypto-trading-platforms-in-2020-the-definitive-guide-updated-c72f8b874555)
*   最佳[加密贷款平台](/coinmonks/top-5-crypto-lending-platforms-in-2020-that-you-need-to-know-a1b675cec3fa)
*   [最佳区块链分析工具](https://bitquery.io/blog/best-blockchain-analysis-tools-and-software)
*   [加密套利](/coinmonks/crypto-arbitrage-guide-how-to-make-money-as-a-beginner-62bfe5c868f6)指南:新手如何赚钱
*   最佳[加密制图工具](/coinmonks/what-are-the-best-charting-platforms-for-cryptocurrency-trading-85aade584d80)
*   [莱杰 vs 特雷佐](/coinmonks/ledger-vs-trezor-best-hardware-wallet-to-secure-cryptocurrency-22c7a3fd391e)
*   了解比特币的[最佳书籍有哪些？](/coinmonks/what-are-the-best-books-to-learn-bitcoin-409aeb9aff4b)
*   [3 商业评论](/coinmonks/3commas-review-an-excellent-crypto-trading-bot-2020-1313a58bec92)
*   [AAX 交易所评论](/coinmonks/aax-exchange-review-2021-67c5ea09330c) |推荐代码、交易费用、利弊
*   [Deribit 审查](/coinmonks/deribit-review-options-fees-apis-and-testnet-2ca16c4bbdb2) |选项、费用、API 和 Testnet
*   [FTX 密码交易所评论](/coinmonks/ftx-crypto-exchange-review-53664ac1198f)
*   [n 零审核](/coinmonks/ngrave-zero-review-c465cf8307fc)
*   [Bybit 交换审查](/coinmonks/bybit-exchange-review-dbd570019b71)
*   3Commas vs Cryptohopper
*   最好的比特币[硬件钱包](/coinmonks/the-best-cryptocurrency-hardware-wallets-of-2020-e28b1c124069?source=friends_link&sk=324dd9ff8556ab578d71e7ad7658ad7c)
*   最佳 [monero 钱包](https://blog.coincodecap.com/best-monero-wallets)
*   [莱杰纳米 s vs x](https://blog.coincodecap.com/ledger-nano-s-vs-x)
*   [bits gap vs 3 commas vs quad ency](https://blog.coincodecap.com/bitsgap-3commas-quadency)
*   [莱杰 Nano S vs 特雷佐 one vs 特雷佐 T vs 莱杰 Nano X](https://blog.coincodecap.com/ledger-nano-s-vs-trezor-one-ledger-nano-x-trezor-t)
*   [block fi vs Celsius](/coinmonks/blockfi-vs-celsius-vs-hodlnaut-8a1cc8c26630)vs Hodlnaut
*   Bitsgap 评论——一个轻松赚钱的加密交易机器人
*   为专业人士设计的加密交易机器人
*   [PrimeXBT 审查](/coinmonks/primexbt-review-88e0815be858) |杠杆交易、费用和交易
*   [埃利帕尔泰坦评论](/coinmonks/ellipal-titan-review-85e9071dd029)
*   [赛克斯石评论](https://blog.coincodecap.com/secux-stone-hardware-wallet-review)
*   [BlockFi 评论](/coinmonks/blockfi-review-53096053c097) |从您的密码中赚取高达 8.6%的利息