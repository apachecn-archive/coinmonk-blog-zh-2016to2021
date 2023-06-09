# 第五部分——区块链 101:21 世纪最具突破性创新的简单介绍

> 原文：<https://medium.com/coinmonks/part-v-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-fe37f825f999?source=collection_archive---------9----------------------->

欢迎来到我们系列的最后一部分。在这一部分，我们将介绍区块链技术的最后一个重要元素:共识机制、工作证明和挖掘。在我们继续我们的沙盒类比之前，请确保您已经阅读并理解了本系列的最后一部分( [*第四部分，此处*](https://kiranbanakar.medium.com/part-iv-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-8e6faeb0c80d) *)。*

![](img/3a62f1be7eade0d2ac86212aac7a0e52.png)

Photo by [Greg Rakozy](https://unsplash.com/@grakozy?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

“莎拉，你有没有注意到，在我们的货币系统中，任何人都不能拥有超过 100 沙盒欧元？”劳拉问你。“最初，当我们创造我们的货币时，我们给了每个人 25 沙盒欧元([见第一部分](https://kiranbanakar.medium.com/part-i-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-c81d5fa16e8e))。因为我们是在我们的小世界做生意的四个孩子，沙盒欧元的总数只有 100 沙盒欧元。这意味着没有人会比这个数目更富有。我担心我们的货币上限会导致某种程度的经济受限。你看，我们正在发展我们的产品和服务。一开始，我们只卖沙饼干和蛋糕。然后，服务出现了，现在我们有大量不同的产品和服务互相销售。因此，我国经济从一开始就保持了高速增长。但是我们的货币没有任何增长——总量仍然和开始时一样。我担心，如果我们找不到解决方案，我们的经济将陷入停滞，尽管我们比以往任何时候都更有生产力。只是没有足够的手段来相互交换价值。你怎么看？”劳拉看着你。

劳拉是对的，你心里想。自从您注意到您系统中的价格一直在下降，您已经观察到同样的问题有一段时间了。一开始，一个沙盒饼干要 5 沙盒欧元，但现在只需要 1 沙盒欧元。看待这个问题的一种方式是，一种沙饼现在可能在生产中更便宜，导致价格更低。另一个观点是，沙盒欧元的购买力已经上升。换句话说:1 沙盒-欧元今天可以买到和过去 5 沙盒-欧元一样多的产品。这可能是一件好事，但如果我们把这种发展投射到未来，我们将看到一个沙箱的购买力——欧元永远上升。这会导致什么结果呢？我们无法预测未来，但我们可以有把握地假设，你和你的朋友将如何应对沙盒欧元的升值:因为你知道一个沙盒欧元明天比今天更有价值，你会停止买东西，因为如果你愿意等一段时间，你可以买更多的东西。结论是:今天每个人都将停止买东西，因为你们所有人都想在未来买更多的东西。因此，经济将会停滞不前。

担心之余，你和劳拉打电话给你的朋友和穆罕默德的母亲，告诉他们你的担忧。经过多次讨论，每个人都同意，你需要一种机制来提高你系统中的沙盒欧元总量，以跟上产品和服务的增长。

“嗯，”Mehmet 的母亲开始说，“一件好事是我们的货币系统是由我们所有人发展起来的。我们制定了规则，所以如果我们都同意这些改变，我们也可以改变这些规则，对吗？”

“对，没错。”丹尼尔说。

“好的，我们需要回答的第一件事是，谁将获得新创建的沙盒——欧元？”买买提的母亲问道。

“哦，那就清楚了。你应该得到他们，因为你是我们的组织实体，妈妈。”穆罕默德说。

“但我只是组织实体！我不消费东西，不吃沙饼干，不买你的服务。我只是记录每个人的余额。如果新创建的沙盒欧元和我在一起，它们怎么会在你们的经济中流通？”买买提的母亲清楚地表明了自己的观点，并向孩子们提问。

“我明白了，你是对的。那么……”丹尼尔自言自语道。"如果我们把它们平均分配给所有人会怎么样？"

“不，那会导致我们不再努力工作。我们只需等待下一批新创建的沙盒欧元存入我们的账户，我们将停止生产和销售东西。”劳拉说。

“你说得有道理。那么，如果我们创造一些活动，我们可以赚取新创建的沙箱-欧元？你在这项活动上投入的时间和精力越多，你挣得就越多。”买买提建议。

“坚持住！我有主意了！”劳拉大声喊道。

“不错！给我们讲讲！”买买提的母亲说。

“好吧。当 Mehmet 说我们应该通过在一项活动中投入时间和精力来找到赚取沙盒欧元的方法时，我不知何故不得不想到 Mehmet 的母亲一直在为我们做的工作。尽管她效率极高，速度极快，但她仍在投入时间和精力，以保持我们的货币体系健康和活力。现在，如果我们把这个活动变成一个竞赛呢？”劳拉兴奋地建议道。

“竞争？能解释一下吗？”丹尼尔一无所知。

“是的，当然。我所说的竞争指的是:不是只有一个人组织我们的货币体系，而是我们所有人都可以参与这个过程。我想到的是，更新我们的余额信息列表这一行为本身就可能成为一场竞赛。第一个成功更新列表的人将获得预先设定的沙盒奖励——欧元。这样，保持我们的货币体系健康就会增加我们世界的沙盒欧元总量。你怎么看？”劳拉自豪地微笑着。

“这听起来不错，但我有一些问题。”你还是不相信。“如果我们所有人都能以这种方式赚取更多沙盒欧元，那么我们将停止生产商品和服务，转而专注于更新名单。这导致没有经济活动，因此没有任何未完成的订单，需要处理这些订单来更新列表。你看到我害怕什么了吗？”

"莎拉，你说的话很有想法。"买买提的母亲赞赏地说。“我想我有这个问题的解决方案，但首先我需要告诉你我是如何得出这个解决方案的。当劳拉提议比赛时，我立即想到:“哦，不，我很高兴我们有一个预先定义的 10 分钟间隔([见第二部分](https://kiranbanakar.medium.com/part-ii-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-26e66bb3da17))，因为我喜欢更新名单之间的自由时间。但是劳拉的解决方案，顺便说一句，非常棒，”买买提的母亲向劳拉点点头，“不会有任何空闲时间了，因为比赛是关于谁将第一个更新列表。"

“啊，你说得对，我没有想到那一点。”劳拉若有所思地说道。

“别担心，我已经想出了一个解决方案，这也将解决保持经济活动活跃的问题。”买买提的母亲解释道。“我们必须减缓这一进程。我假设你们所有人都和我一样快地计算余额，因此如果比赛是关于谁将是最快的，我不能要求你们工作得更慢。相反，让我们介绍一个你必须解决的额外的谜语来成为赢家。”

“嗯？谜语？”买买提很惊讶。“什么意思？”

“让我解释一下。当你在自己的平板电脑上更新列表后，你将不得不解决一个谜语，但不是你个人，而是平板电脑本身。我会用一个插件更新你的平板电脑，这是一个哈希函数([见第四部分](https://kiranbanakar.medium.com/part-iv-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-8e6faeb0c80d))。更新列表后，哈希函数将处理新信息。这个哈希函数会将任何输入转换为预先确定的标准化输出，称为哈希。但是——谜题来了——我们将建立一个规则:只有那些前四位数字为零的散列才是有效的。”

![](img/d0fb69ad6ebf5a5de69cfaade30901ce.png)

We choose a rule to define valid hashes: the first four digits must be equal to zero (illustration by author).

“好吧，好吧，等等”，穆罕默德说。“幸运的是，我们以前都读过关于散列函数和散列的精彩介绍([见第四部分](https://kiranbanakar.medium.com/part-iv-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-8e6faeb0c80d))。否则，这对我来说是没有意义的。你基本上说的是，我们应该希望我们平板上的 hash 函数会巧合地生成一个前四位为零的 hash？这应该如何运作？”

“我还没告诉你最重要的事。”买买提的母亲对她的想法很兴奋。“首先，很高兴您知道哈希函数的基础知识。您可能还知道，只更改输入中的一个字符会生成一个完全不同的散列，是吗？”

“是的，我记得”，丹尼尔说，很好奇接下来会发生什么。

“太好了。现在，除了您自己计算的更新列表之外，我们将引入一个运行变量 x。这个变量有一个初始值，比如说，0。我们将包含运行变量的更新列表输入到哈希函数中，并查看输出的前四位数字(哈希)是否等于零。然而，如果没有，我们将运行变量增加 1，所以现在 X 等于 1。然后，我们将 X 的新值(为 1)再次输入到哈希函数中，并检查生成的哈希是否有效。我们重复这个过程，直到在某一点上，一个有效的散列将被生成。你们中第一个找到有效哈希的人将成为比赛的获胜者！”买买提的妈妈讲完了她的课，孩子们被深深打动了。“顺便说一句，递增运行变量的整个过程将由您的平板电脑自动完成，因此不需要您自己手动完成所有操作。”她补充道。

![](img/dff03452287dd9e7d877bb66352fd085.png)

Incrementally increasing the run variable will generate a fundamentally different hash every iteration (illustration by author).

“哇，这是高层次的。我想我已经理解了你的概念，它是辉煌的，我同意。”劳拉说。“但是还有一件事让我很困惑。我们计算更新列表的速度几乎一样快。这两款平板电脑完全相同，因此速度也一样快。我们如何确保有一个明确的赢家？无可争议的第一名？”

“敏锐的观察，劳拉。”买买提的母亲说。“我忘了告诉你:处理的速度是相等的，但是你可以单独设置初始值和运行变量自动增加的步数。在我上面的解释中，我将起始值设置为 0，将增量步长设置为 1。但是你可以单独选择这两个元素。例如，您可以将起始值设置为 1，597，578，将增量步长设置为 15，因此现在运行变量将从 1，597，578 开始，并且每次迭代增加 15。

![](img/0ba31dcd24b497ec41b14ab6f4caabcb.png)

The starting value and the increment of the run variable can be set individually, because the generation of a valid hash is random (illustration by author).

“哦…我明白了！”你兴奋地说。“因为哈希的生成是随机的，我们中的任何人都可能找到一个有效的哈希，不管起点和增量是多少。这意味着所有平板电脑的处理速度将是相同的，但每台平板电脑的“旅程”都将是高度个性化的，因为我们选择不同的起始值和增量步骤。是这样吗？”

![](img/e3a423fc4c27f95d29edd14f865a3834.png)

Based on the run variable, everyone in the system can land on a valid hash — it is just about who is going to be the first to find it (illustration by author).

“是的，莎拉，你得到了它。”买买提的母亲笑着说。

“呸，我们系统的另一项创新。如果我从一开始就没有参与其中，我想我什么都不会明白！”丹尼尔说。

“没错，现在这已经相当复杂了。但是我有另一个问题。当我们有一个明确的比赛获胜者时会发生什么？怎么才能知道有没有错误呢？更重要的是，奖励有多大？”买买提问道。

“说得好。我建议，在我们有了一个明确的获胜者之后，我们都来看看获胜者的更新列表和运行变量，看看是否一切都是正确和有效的。作为奖励，我想说每场比赛 5 沙盒欧元是个不错的数目，你们觉得呢？”劳拉求婚了。

“听起来有道理。5 沙盒——欧元是个不错的数目。”丹尼尔同意了，你们其他人都点头表示同意。

“好吧，那么，我们走吧！”你说，然后出发。

快进:在测试了新系统之后，它被证明是一个巨大的成功。没有人在多轮竞争后成为唯一的赢家，而是新创建的沙盒-欧元的平均分配得以实现。每个人都获得了公平的回报，此外，由于新的流动性，经济稳定下来。商业繁荣，每个人都过得更好。

为了防止这一部分变得不必要的长，我们将快速介绍所讨论概念的官方名称。

*   运行变量被称为 Nonce(“使用一次的数字”的缩写)。
*   找到有效 Nonce-Blockchain-match 的行为称为挖掘，因为最终的结果是获胜者(挖掘者)将获得一定数量的数字令牌。想想一个金矿工人，他挖金子，在投入时间和精力到采矿过程后找到了金子。
*   在找到一个 Nonce(它与更新的区块链一起生成一个有效的哈希)后，我们证明了我们已经投入了时间和精力(平板电脑的计算能力)来保持我们的货币系统健康。这样，我们就有了工作投入的证明——换句话说，我们有了工作证明。
*   最终的评估步骤被称为共识机制，因为其他利益相关者(矿工)将查看获胜者的结果，并检查是否一切都计算正确，以及最终散列是否有效。当所有人都同意且没有异议时，奖励将存入获胜者的账户。

恭喜你——你现在正式对区块链技术、各种子系统以及一切如何结合在一起有了深刻的理解。我希望现在对你来说事情更清楚了，并且你对这项简单而出色的技术有了新的认识。

如果你想重新开始这个系列，这里有以前部分的链接:

*   第一部分
*   [第二部分](https://kiranbanakar.medium.com/part-ii-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-26e66bb3da17)
*   [第三部](https://kiranbanakar.medium.com/part-iii-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-a6c303ddff12)
*   [第四部分](https://kiranbanakar.medium.com/part-iv-blockchain-101-a-simple-introduction-to-the-most-groundbreaking-innovation-of-the-21st-8e6faeb0c80d)

> 加入 Coinmonks [电报频道](https://t.me/coincodecap)和 [Youtube 频道](https://www.youtube.com/c/coinmonks/videos)了解加密交易和投资

## 另外，阅读

*   [MoonXBT vs Bybit vs 币安](https://blog.coincodecap.com/bybit-binance-moonxbt) | [硬件钱包](/coinmonks/hardware-wallets-dfa1211730c6)
*   [火币交易机器人](https://blog.coincodecap.com/huobi-trading-bot) | [如何购买 ADA](https://blog.coincodecap.com/buy-ada-cardano) | [Geco。一篇评论](https://blog.coincodecap.com/geco-one-review)
*   [币安 vs Bitstamp](https://blog.coincodecap.com/binance-vs-bitstamp) | [Bitpanda vs 比特币基地 vs Coinsbit](https://blog.coincodecap.com/bitpanda-coinbase-coinsbit)
*   [如何购买瑞波(XRP)](https://blog.coincodecap.com/buy-ripple-india) | [非洲最好的加密交易所](https://blog.coincodecap.com/crypto-exchange-africa)
*   [非洲最佳加密交易所](https://blog.coincodecap.com/crypto-exchange-africa) | [Hoo 交易所评论](https://blog.coincodecap.com/hoo-exchange-review)
*   [eToro vs robin hood](https://blog.coincodecap.com/etoro-robinhood)|[MoonXBT vs by bit vs Bityard](https://blog.coincodecap.com/bybit-bityard-moonxbt)
*   [有哪些交易信号？](https://blog.coincodecap.com/trading-signal) | [比特斯坦普 vs 比特币基地](https://blog.coincodecap.com/bitstamp-coinbase)
*   [ProfitFarmers 点评](https://blog.coincodecap.com/profitfarmers-review) | [如何使用 Cornix 交易机器人](https://blog.coincodecap.com/cornix-trading-bot)
*   [如何在势不可挡的域名上购买域名？](https://blog.coincodecap.com/buy-domain-on-unstoppable-domains)
*   [印度的秘密税](https://blog.coincodecap.com/crypto-tax-india) | [altFINS 审查](https://blog.coincodecap.com/altfins-review) | [Prokey 审查](/coinmonks/prokey-review-26611173c13c)
*   [Blockfi vs 比特币基地](https://blog.coincodecap.com/blockfi-vs-coinbase) | [BitKan 点评](https://blog.coincodecap.com/bitkan-review) | [Bexplus 点评](https://blog.coincodecap.com/bexplus-review)
*   [南非的加密交易所](https://blog.coincodecap.com/crypto-exchanges-in-south-africa) | [BitMEX 加密信号](https://blog.coincodecap.com/bitmex-crypto-signals)
*   [MoonXBT 副本交易](https://blog.coincodecap.com/moonxbt-copy-trading) | [阿联酋的加密钱包](https://blog.coincodecap.com/crypto-wallets-in-uae)
*   [Remitano 审查](https://blog.coincodecap.com/remitano-review)|[1 英寸协议指南](https://blog.coincodecap.com/1inch)
*   [iTop VPN 审查](https://blog.coincodecap.com/itop-vpn-review) | [曼陀罗交易所审查](https://blog.coincodecap.com/mandala-exchange-review)
*   [40 个最佳电报频道](https://blog.coincodecap.com/best-telegram-channels) | [喜美元评论](https://blog.coincodecap.com/hi-dollar-review)
*   [折 App 评论](https://blog.coincodecap.com/fold-app-review) | [StealthEX 评论](/coinmonks/stealthex-review-396c67309988) | [Stormgain 评论](https://blog.coincodecap.com/stormgain-review)
*   [购买 PancakeSwap(蛋糕)](https://blog.coincodecap.com/buy-pancakeswap) | [俱吠罗评论](/coinmonks/coinswitch-kuber-review-1a8dc5c7a739)