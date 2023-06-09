# DeFi 初学者终极指南

> 原文：<https://medium.com/coinmonks/the-ultimate-beginners-guide-to-defi-how-to-make-money-with-crypto-by-yield-farming-266c67174dff?source=collection_archive---------6----------------------->

## **如何通过产量农业用密码赚钱**

![](img/fdc18d3c9dea14dd51a0bbdfdc6316c8.png)

DeFi 世界正在快速扩张，随着全球金融系统继续向数字化转型，DeFi 具有非常大的增长潜力，吸引了全球 300 多万投资者的关注。因此，有必要了解资产、市场、投资方法等。

![](img/e15f0fc6f76e4ddf6a192ae9ef9650ec.png)

[*Footprint Analytics*](https://www.footprint.network/) *-*[*TVL by protocols*](https://www.footprint.network/guest/chart/tvl-by-protocols-latest-day-fp-73a2d3c2-a9b1-4c6f-b598-fd63f10bf3f0?channel=u-DBc983)

我们在上一篇文章中已经介绍了 DeFi 的基础知识。这一次我们将深入探讨:

1.  3 个主要的 DeFi 投资类别；
2.  投资者如何通过参与 DeFi 投资获得被动收益；
3.  DeFi 项目的当前风险；和
4.  评估 DeFi 项目的 7 个视角

# 加密货币的两种投资方式

参照加密货币的投资类型，可以分为法定型和代币型。

**菲亚特投资**

*   加密货币(也称为代币)被视为股票，那么 CEX 或 DEX 就是股票交易所。
*   投资者 Alex 可以在 CEX 或 DEX 上买卖加密货币，高卖低买赚取差价，获得收益，称为“投机”。
*   在这种情况下，Alex 关心的只是加密货币的价格变化，使用 ROI(投资回报率)作为评估指标。

![](img/78e78925d94ee05e557f468931b2073d.png)

*Source: zoni@Footprint.network*

**代币制(或称产量农业)**

*   当投资者长期看好某些加密货币时，最简单的投资策略是“持有”它们；而更聪明的策略是通过创造更多的被动收入来更好地利用它们。
*   例如，投资者 Alex 可以将加密货币存入借贷平台 Compound 或收益率聚合器 Idle 以获得利息收入。
*   在这种情况下，投资者 Alex 关心的只是加密货币数量的增长和通过产量农业赚取的 APY。

![](img/9ecd2e4ce3790d4177a6dbf88501de0a.png)

*Source: zoni@Footprint.network*

我们将通过介绍 3 个主要的 DeFi 投资类别来进一步讨论高产农业，这 3 个类别是:AMM DEX、Ledning 和产量聚合器。

# DEX: Uniswap 为例

Uniswap 建立在以太坊之上，作为分散式交易所，支持该网络上的所有加密货币。与传统的订单交换不同，它使用 AMM(自动做市商)算法，允许用户以更高的效率交换各种 ERC-20 令牌。

在 Uniswap 的 AMM 模型中，流动性提供者(缩写为 LP)需要创建一个流动性池，供交易者交换所需的代币。

包括两种情况。

对于交易者来说，他们互换。

假设 1 ETH 等于 2220 DAI，交易者 Alex 想用他的 DAI 换 ETH。他需要支付 2220 DAI 加交易费(为便于理解，本文所有场景忽略气费)才能获得 1 ETH。

![](img/7d4ac2c25770ee2a16b4ca3a49467fa2.png)

*Source: zoni@Footprint.network*

**对于有限合伙人来说，他们提供流动性。**

Endy 作为 LP 需要向流动性池提供一对两个等值的令牌(如 DAI+ETH)。作为回报，他将从交易活动中获得一部分交易费用。他还将获得一个 LP 令牌，这是提供流动性的凭证，代表他在整个流动性池中的份额。

![](img/321f8b4bdfdb1090ce714fc7ed0bff0e.png)

*Source: zoni@Footprint.network*

它是如何实现自动定价的？这让我们想到 uni swap AMM 机制背后的“持续产品做市商”模式。这个模型的公式是:x*y=k，其中 x 和 y 代表各自的流动性，k 是常数。

![](img/bd131b0e1a9ec9db29ab96fd6a04b491.png)

*Source: zoni@Footprint.network*

值得注意的是，模型并不是线性变化的。事实上，订单的相对量越大，x 和 y 之间不平衡的幅度就越大。也就是说，大订单的价格相对于小订单呈指数增长，导致滑动价差越来越大。

![](img/49b84bae75358440c0a20b2c23829410.png)

*Figure: Uniswap price change curve*

在提供流动性的过程中，有限合伙人需要意识到非永久性损失。

**什么是非永久性损失？**下面是一个例子。

假设 Endy 持有 2000 DAI 和 1 ETH (1 ETH= 2000 DAI)，他有 2 个选择。

选项 1:作为有限合伙人

*   提供 2000DAI + 1 ETH 以形成流动性池的令牌对
*   当价格发生变化:ETH = 4000DAI(在 DEX 之外)时，套利者会以 Uniswap(更便宜)买入 ETH，并以更高的价格卖给其他 DEX
*   这将导致池中 ETH 的数量减少，ETH 的价格增加，直到等于 4000DAI。(套利机会消失)
*   此时恩迪的 LP 令牌价值 2828 DAI + 0.71 ETH，相当于持有 5657 DAI。

选项 2:拿着它们

*   当 ETH 价格变为 4000DAI 时，恩迪的资产相当于持有 6000DAI。

在相同条件下，“选项 1 提供流动性”比“选项 2 仅保持流动性”少 343 DAI，即减少 5.72%。这种损失叫做非永久性损失。当 ETH 恢复 2000 DAI，这种非永久性的损失就会消失。

# 贷款:以复利为例

在 DeFi 的借贷平台中，投资者在池中提供一个加密资产来赚取利息；如果这笔存款被抵押，投资者就可以借用另一笔加密资产。目前，DeFi 的贷款平台通常使用“超额抵押”，即借款人在违约时提供价值超过实际贷款的资产。

举例。

1.  投资者 Alex 与戴一起，他不想出售，所以他把它放入资金池，作为贷款人借给有需要的人，从而赚取利息
2.  Bob 知道在 DAI 有一个很好的投资机会，但他不想出售他拥有的 ETH，所以他用 ETH 作为抵押向 DAI 借款并支付利息。
3.  在这个过程中，Alex 和 Bob 都获得了 COMP 平台令牌，这就是我们所说的流动性挖掘。

![](img/25c0ac05cd532238e30cb6794faf1b6f.png)

*Source: zoni@Footprint.network*

# 收益聚合器:闲置和渴望

如今，DeFi 项目正在各地涌现。投资者可能面临以下问题:

1.  太多不同利率的平台:如何选择最好的？
2.  利率总是在变化，价格也是如此:
3.  借款人可能会意外清盘，怎么办？
4.  贷款人可能需要不断改变协议以获得更好的利率，从而导致高额的汽油费
5.  投资者不可能 24 小时盯着市场。

DeFi 的收益聚合器可以以某种方式解决上述问题，其中特定资产的价值提供了一个复杂的投资策略，该策略结合了贷款、抵押和交易，以实现利润最大化。

*   空闲:

这是一个基于以太坊的协议，允许用户通过投资单一资产获得最佳利益。目前支持 Maker、Compound、dYdX、Aave、Fulcrum 等协议的金融服务。使用 IDLE 存款时，您将收到一个复杂的 APY，由您存款的代币的 APR、平台代币 Idle 和 COMP 组成。

*   渴望:

它也是以太坊上的一个协议，主要目标是为存放的代币产生最高的回报。它以程序化资产管理为特色，以部署最佳策略。

以 ETH 金库为例。

1.  投资者将 ETH 存入 ETH 金库，ETH 金库将 ETH 存入 MakerDao，作为借入 stablecoin DAI 的抵押。
2.  借入的 DAI 被存入 Curve Finance 的流动性池，以基本 apy 的形式接收 LP 代币作为回报和交易费用。LP 令牌可以被押入曲线的 CRV 标尺，以赚取 CRV 奖励。
3.  挣得的 CRV 随后被转换成 ETH，并将再次存入 ETH 金库。如此循环，直到投资者退出。
4.  投资者最终获得 ETH 结算的利息，并支付一定数额的管理费。

![](img/4f85905d6f2570dfd9d8fdedddfbc622.png)

*Source：Finematics*

# DeFi 项目的风险

投资机会的多样性和持续增长使 DeFi 成为一项有吸引力和有利可图的投资。然而，与任何投资一样，DeFi 投资也有风险。

**协议风险**

*   智能合同:被黑(即使有审计)
*   单一智能合同
*   基于多智能契约的协议
*   协议风险
*   scamer:提供高 APY 的协议令牌+稳定币池
*   威尔士倾销代币导致价格为零
*   代币价格的可变性:
*   借款:很容易被清算
*   LP:非永久性损失
*   运营风险
*   钱包风险:种子短语、私钥被盗的风险
*   DeFi 授权:
*   取消未使用协议的授权
*   不要孤注一掷

# 如何评估 DeFi 项目

投资者一定要*做好自己的调研(* DYOR *)* 投资前，从以下 6 个方面入手:

1.  要问的基本问题:

*   哪种型号，在什么区块链上，审计过没有？
*   上线时，TVL、24H 用户的排名
*   是否在 coingecko、CMC 上？

2.著名发明家的筹款历史

1.  项目介绍(官网+公众文章+ github)

*   商业模式、竞争对手、差异化特征
*   有负面消息吗？考虑到媒体的中立性，关注太好的报道
*   经济模型(团队的代币分配:15%-20%以内是可接受的)
*   GitHub 的代码提交频率

3.关注价格趋势

*   短时间内暴涨？泵送的高概率
*   鲸鱼倾倒导致大量掉落的风险

4.关注极高的 APY

*   骗子吸引投资者的方法
*   小心翼翼地尝试，但要在崩溃前快跑

5.社区的活动

*   用户提问:投资者的素质
*   管理响应的态度和有效性

DeFi 为投资者提供了一个更方便的选择，作为传统投资的替代品。随着越来越多的投资者、机构、资本和开发商进入，一个更加开放、透明和节约的金融体系有望形成。

> 加入 Coinmonks [电报频道](https://t.me/coincodecap)和 [Youtube 频道](https://www.youtube.com/c/coinmonks/videos)了解加密交易和投资

## 也阅读

[](/coinmonks/leveraged-token-3f5257808b22) [## 杠杆代币[多头代币]终极指南

### 杠杆化令牌是具有杠杆化风险敞口的 ERC20 令牌，不考虑保证金、要求、管理…

medium.com](/coinmonks/leveraged-token-3f5257808b22) [](https://blog.coincodecap.com/crypto-exchange) [## 最佳加密交易所| 2021 年十大加密货币交易所

### 加密货币交易所的加密交易需要了解市场，这可以帮助你获得利润。之前…

blog.coincodecap.com](https://blog.coincodecap.com/crypto-exchange) [](/coinmonks/top-5-crypto-lending-platforms-in-2020-that-you-need-to-know-a1b675cec3fa) [## 2021 年最佳加密借贷平台| 6 大比特币借贷平台

### 获得比特币和其他加密货币的最佳贷款利率

medium.com](/coinmonks/top-5-crypto-lending-platforms-in-2020-that-you-need-to-know-a1b675cec3fa) [](/coinmonks/crypto-trading-bot-c2ffce8acb2a) [## 2021 年最佳免费加密交易机器人

### 2021 年币安、比特币基地、库币和其他密码交易所的最佳密码交易机器人。四进制，位间隙…

medium.com](/coinmonks/crypto-trading-bot-c2ffce8acb2a) [](/coinmonks/best-crypto-signals-telegram-5785cdbc4b2b) [## 最佳 4 个加密交易信号电报通道

### 这是乏味的找到正确的加密交易信号提供商。因此，在本文中，我们将讨论最好的…

medium.com](/coinmonks/best-crypto-signals-telegram-5785cdbc4b2b) [](https://blog.coincodecap.com/best-social-trading-platforms) [## 5 个最佳社交交易平台[2021] | CoinCodeCap

### 困惑于社交交易和副本交易哪个平台最好？本文将带您了解各种…

blog.coincodecap.com](https://blog.coincodecap.com/best-social-trading-platforms) [](https://blog.coincodecap.com/blockfi-review) [## BlockFi 评论 2021:利弊和利率| CoinCodeCap

### 今天，我们提出了一个全面的 BlockFi 评论，这是一个成立于 2017 年的加密贷款平台，拥有其…

blog.coincodecap.com](https://blog.coincodecap.com/blockfi-review) [](/coinmonks/buy-bitcoin-in-india-feb50ddfef94) [## 如何在印度购买比特币？2021 年购买比特币的 7 款最佳应用[手机版]

### 如何使用移动应用程序购买比特币印度

medium.com](/coinmonks/buy-bitcoin-in-india-feb50ddfef94) [](/coinmonks/best-crypto-tax-tool-for-my-money-72d4b430816b) [## 加密税务软件——五大最佳比特币税务计算器[2021]

### 不管你是刚接触加密还是已经在这个领域呆了一段时间，你都需要交税。

medium.com](/coinmonks/best-crypto-tax-tool-for-my-money-72d4b430816b) [](https://blog.coincodecap.com/best-hardware-wallet-bitcoin) [## 存储比特币的最佳加密硬件钱包[2021] | CoinCodeCap

### 保管您的数字资产很容易，但找到正确的存储方式却是一项繁琐的任务。在线钱包有一个风险…

blog.coincodecap.com](https://blog.coincodecap.com/best-hardware-wallet-bitcoin) [](/coinmonks/pionex-review-exchange-with-crypto-trading-bot-1e459d0191ea) [## Pionex 评论 2021 |免费加密交易机器人和交换

### Pionex 是为交易自动化提供工具的后起之秀。Pionex 上提供了 9 个加密交易机器人…

medium.com](/coinmonks/pionex-review-exchange-with-crypto-trading-bot-1e459d0191ea)