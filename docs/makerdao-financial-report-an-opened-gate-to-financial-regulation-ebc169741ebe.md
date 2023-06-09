# 马克道财务报告:打开金融监管的大门

> 原文：<https://medium.com/coinmonks/makerdao-financial-report-an-opened-gate-to-financial-regulation-ebc169741ebe?source=collection_archive---------2----------------------->

## 审慎监管离加密资产行业还有多远？

![](img/34dbd0f0d9e930290a737de25115578e.png)

马克尔道于 2021 年 8 月[***【1】***](#_ftn1)发布了关于其 8 月份协议财务报表的非约束性报告。虽然 MakerDAO 已经反复进行了这种练习，但本文的目的是加深对它所提供的数字的理解。

作为介绍，MakerDAO 协议是一个管理称为 DAI 的链上抵押稳定货币的生态系统，在该系统中，其发行受制于另一种加密货币的优先抵押(主要的一种是以太坊，作为 MakerDAO 操作的通常第 1 层)。根据 DeFi Llama 的评估，目前发行的 DAI 数量约为 100 亿，记录的 TVL 或锁定总价值为 10.22 亿英镑，突出表明稳定币作为 DeFi 市场标准的采用日益增加。

在分析 MakerDAO 提供的信息之前，重要的是要注意，stablecoin 公布其自己的指标或财务报表的事实允许推断 MakerDAO 不仅指基础的 DAI stablecoin，而且指协议的财务结构。MakerDAO 提出的价格稳定模型允许通过三种机制产生收入，这将在后面描述，这大大远离了电子货币或数字货币仅仅作为基础的概念，使其更接近于公司的概念。MakerDAO 的资产负债表结构和损益表的生成是市场可以用来制定实体财务估值的输入，即通过比率和业务估值模型计算其内在价值，其中稳定币只是其业务模型产生的基础资产。

**什么是创客刀，它是如何工作的？**

MakerDAO(去中心化自治组织)是以太坊上的一个去中心化借贷平台，通过一个去中心化的治理项目来支持和稳定其 DAI 令牌的价值。正如上一篇文章中所讨论的，作为总结，MakerDAO 寻求用一种模式来取代基于股东参与的传统治理模式，在这种模式中，MKR 治理令牌的持有者对算法预定义的一系列决策进行投票，以便消除或至少淡化 MakerDAO 法人实体背后的负责人的存在。

该协议基于一对在 20 标准下和谐工作的加密货币，其中作为治理令牌，戴作为针对抵押品生成的令牌，其价格以不同方式稳定。

戴(DAI)也是泰瑟(Tether)和的替代产品，它们是链外担保的稳定债券，通过开立法定账户使用集中的法律支持，并据此发行代币，这些代币由类似数量的法定货币支持，这些法定货币存储在特定的金库或保险柜中。集中化风险(CeFi)是指存在一个第三方可以针对其采取行动的中央机构，即存在一个中央故障点，严格来说，该故障点与交易的验证无关，但与支持发行的相反价值的系统有关。

DAI 通过动态超额抵押系统工作，在该系统中，用户开立 CDP(抵押债务头寸),参与者通过智能合约将一定量的以太币(尽管也使用 USDC 或基本注意力令牌)作为抵押品存入 CDP，并接收协议根据交付量生成的预设量的 DAI(比率 1 美元= 1DAI ),以及基于动态利率的利息。

风险在于可能无法偿还所收到的 DAI，在这种情况下，所存放的抵押品(类似于质押合同)将被强制执行，并被处以罚款。智能合约还设置了清算率(清算阈值，最初在 MakerDAO 中设置为债务的 150%)，通过该清算率确定在抵押品价格的什么水平执行头寸，在抵押品报价的价格平仓。

**马克尔道业务线:**

根据该报告，马克尔道生态系统有三条业务线:贷款业务、交易业务和抵押品管理业务。细目如下:

*   **贷款业务:**如上所述，DAI 是在特定资产(稳定资产(USDC)或非稳定资产(以太坊或 BAT))的抵押下以 CDP 形式发行的。由于法律人格、在跨境制度中的应用、数字身份问题以及总体上缺乏规范 P2P 环境中参与者之间关系的国际统一法律制度，协议在法律上不能对参与节点的不付款发起债务索赔诉讼，MakerDAO 协议通过抵押机制来覆盖其风险。换句话说，如前所述，一定数量的 DAI 的发行受发行的预先超额抵押的影响，以这种方式，抵押品的价值总是保证高于发行的 DAI 的价值。

此外，该协议收取动态利率，称为稳定费(SF ),作为贷款服务的费用。根据机构本身的定义，SF 是*“一个风险参数，旨在解决针对制造商金库中的抵押品生成 Dai 的固有风险。*[***【2】***](#_ftn1)*。*这意味着该协议与任何其他市场参与者一样，向贷款人收取利率，该利率仅根据所使用的抵押品而变化。与分析借款人一系列参数(金额、还款日历、收入来源、额外合同产品等)的银行评分模型不同，MakerDAO 利率仅根据上述参数作为连续利率固定，以 DAI 支付。这样的 SF 作为财务收入发送到 MakerDAO 的资产负债表，并包括在盈余缓冲中。

*   **交易业务:**马克道开发的第二条业务线，旨在保证以戴为抵押品的交换，而没有义务创设。为了做到这一点，设定了一个特定的利率，称为 PSM 或 Peg 稳定模块，这是一个由 MakerDAO 的参与节点校准的固定利率，它确保 DAI 与抵押品的交换以给定的价格设定，反之亦然。该系统类似于流动性池(由参与节点或协议本身提供的加密货币对，充当自动化流动性协议或 DEX)，尽管在整个减值损失期间，汇率不像传统流动性池(即:Uniswap)中那样是动态的。因此，按照协议中的定义，交易业务类似于借贷业务，只是没有稳定费，清算率等于 100%。此外，进入智能合同的参与节点并不保留将被交换用于 DAI 的抵押品的所有权，如 CDP 的生成所发生的那样，而是资产被交换，协议成为参与节点接收的资产的所有者。MakerDAO 的收入来源是执行智能掉期合同收取的费用，这些费用是由 MKR 治理令牌的持有人直接收取的。
*   **清算业务:**为中解释的拆借业务条线，创设超额抵押 CDP 造币厂戴。考虑到 MakerDAO 的保护方案，该协议建立了担保头寸的 150%的保证金要求，因此当担保物的价值低于发行的 DAI 的 150%时，头寸被清算，以确保该协议收回发行的 DAI 的全部金额，以及稳定费的利息。此外，保证金通知的执行需要对 CDP 持有者进行罚款，以这种方式，参与节点承担费用或罚款，这由 MKR 治理令牌的持有者来校准。因此，在具有易变工具(以太坊、BAT)的抵押 CDP 中，具有保证金追缴执行的 CDP 的交易量高于通过 USDC 的抵押 CDP，因为根据定义，价值变化为零(链上稳定货币)。

这三条业务线构成了马可道的营收基础。幻灯片 4 解释了 8 月份收入下降的原因，因为结算收入(来自本月以太坊的强烈波动)无法弥补贷款利息的下降。这是因为随着安普尔福思、USDC，特别是 Terra 的崛起，stablecoins 方面的竞争激烈，Terra 已融入索拉纳生态系统(反过来，也是最强的 DeFi 环境之一)。

**监管方面:对加密资产的偿付能力要求？**

此外，该报告提供了资本比率(CET1 的名称)和杠杆率方面的高级分析。这两个指标来自银行业，一直被用作定义信贷机构偿付能力水平的行业标准，可以是风险调整(偿付能力比率)或风险非调整(杠杆率)。为此，将机构的资产与其资本水平进行比较，根据资产是否被视为在纯会计基础上估值，或者是否需要额外调整来衡量与这些资产相关的意外损失，区分风险加权资产(RWA)或账面价值资产。关于这一点，CET1 或 CET1 比率衡量机构持有的自有资金(股权，主要根据 CRR 银行条例[【3】](#_ftn2))与其资产负债表上的资产(如上所述，这些资产被调整以定义违约概率)的数量。

在不对信贷机构评估和管理的风险分类进行深入辩论的情况下，应当指出，国际监管机构根据金融系统中其他参与者可能无法承担该机构造成的损失对金融稳定造成的风险，为这两个比率设定了最低水平。这种风险主要来自银行运营的部分准备金模式，在这种模式下，银行需要维持在机构本身收取的存款准备金率，以及通过发放贷款来调节到期日。

银行业偿付能力比率设定为 8%，而杠杆率为 3.5%。推而广之，尽管监管机构尚未对 MiCA 债务人制定具体的偿付能力要求[【4】](#_ftn3)，但 MakerDAO 对偿付能力比率的计算表明，协议的崩溃可能会给金融稳定带来风险。

因此，为了理解 MakerDAO 的偿付能力基本原理，我们要强调幻灯片 11，它分析了作为偿付能力比率分子的权益构成，校准了 MakerDAO 资产量的风险权重，最后，显示了前面提到的杠杆和偿付能力比率。

我们现在将讨论这些概念:

**股权**:定义为盈余缓冲+运营钱包。与传统的将权益概念化为净值(即没有偿还义务的股东的出资)相反，偿付能力比率的分子在盈余缓冲和运营钱包上发挥杠杆作用，这应符合通过 MKR 持有者从《议定书》获得资源或出资以资助其资产的概念。我们认为，马可道的股权由戴为继续通过拍卖收购而积累的、进而被处置以获得资源的量，以及钱包中已经积累的所有代币构成。虽然这种权益的概念是基于股东或协议管理者的出资概念构建的，但最终将决定偿付能力计算框架中被视为自有资源的任何金融工具的要求和特征的是法规。但是，出于说明的目的，它们定义如下:

*   剩余缓冲区是在 MKR 拍卖被激活之前，从稳定性费用收入中在协议中累积的 DAI 量。这是一个可变的量，因为盈余缓冲区的最大积累决定了协议为其随后的分期偿还获得 MKR(为协议从这种销售中产生收入)，稳定治理令牌的货币供应，并为其新的积累减少盈余缓冲区。
*   运营钱包包括持有 MKR 代币的所有活动钱包，因为它们是直接贡献给协议的资源，并且承担代币价值下降导致的损失的潜在吸收。

**风险权重:** MakerDAO 的资产来源于抵押系统，是基于 CDPs 的抵押贷款业务线发放的抵押贷款。此类贷款按账面价值的 100%加权，考虑到此类账面价值已经包含了意外损失，只有以太坊-B 和以太坊-C 的加权不同。特别是，以太坊-B 的权重为 200%(最大 1500 万 DAI 的 CDP，SF = 4%，清算率= 130%)，以太坊-C 的权重为 50%(最大 2M DAI 的 CDP，SF = 3.5%，清算率= 175%)。

但是，考虑到银行偿付能力框架采用的方法，权重没有考虑每笔贷款中包含的抵押品，这些抵押品是根据信用风险缓释技术或 CRMT 定义的。根据 CRMT 框架，任何有相关抵押品的资产，都必须从资产的风险敞口或违约风险敞口(EAD)中减去该抵押品的价值，并根据波动性、汇率和到期日进行调整。在 MakerDAO 协议的情况下，由于这些是超额抵押贷款，其中抵押品的价值总是高于贷款的价值，CRMT 框架的应用将意味着业务的风险为 0，因为抵押品涵盖了借款人拖欠贷款造成的潜在损失。

因此，在不评估担保贷款之外构成 MakerDAO 资产负债表一部分的其他资产价值的情况下，MakerDAO 的风险加权资产应等于 0，因此保持非常高的偿付能力或 CET1 比率。相比之下，杠杆比率的应用，这是一个不是基于风险的比率，以资产的账面价值作为分母。因此，应将其作为 MakerDAO 标准指标进行分析，因为贷款的账面价值不受抵押品存在的影响，抵押品记录在实体财务报表的备忘录账户中。

**结论:**

总之，受监管的银行业也符合金融协议(不一定包含在信贷机构的法律形式中)，因为全行业的偿付能力标准都是适用的。虽然信贷机构的系统性是由该机构的本质(部分准备金模型和作为收入循环流动驱动力的信贷中介)以及规模、相互联系、复杂性等参数(目前不影响这些协议)所验证的(MakerDAO 有 10B TLV)，但有必要强调其潜在采用对金融稳定构成的风险，以及通过比率和风险管理系统进行的必要监管。

[1][https://forum . maker Dao . com/t/real-world-finance-core-unit-report-2021-08/10123](https://forum.makerdao.com/t/real-world-finance-core-unit-report-2021-08/10123)

【https://makerdao.world/en/learn/vaults/stability-fees/】

[【3】](#_ftnref2)资本要求条例:欧洲关于计算信贷机构资本要求的条例。

[【4】](#_ftnref3)加密资产市场:欧洲加密资产监管条例提案。

> 加入 Coinmonks [电报频道](https://t.me/coincodecap)和 [Youtube 频道](https://www.youtube.com/channel/UCbyDhTbOiKh2iUMKBi4-4Zg)了解加密交易和投资

## 另外，阅读

*   [尤霍德勒 vs 科恩洛 vs 霍德诺特](/coinmonks/youhodler-vs-coinloan-vs-hodlnaut-b1050acde55a) | [Cryptohopper vs 哈斯博特](https://blog.coincodecap.com/cryptohopper-vs-haasbot)
*   [币安 vs 北海巨妖](https://blog.coincodecap.com/binance-vs-kraken) | [美元成本平均交易机器人](https://blog.coincodecap.com/pionex-dca-bot)
*   [如何在印度购买比特币？](/coinmonks/buy-bitcoin-in-india-feb50ddfef94) | [WazirX 评论](/coinmonks/wazirx-review-5c811b074f5b) | [BitMEX 评论](https://blog.coincodecap.com/bitmex-review)
*   [比特币主根](https://blog.coincodecap.com/bitcoin-taproot) | [Bitso 回顾](https://blog.coincodecap.com/bitso-review) | [排名前 6 的比特币信用卡](/coinmonks/bitcoin-credit-card-bc8ab6f377c6)
*   [双子座 vs 比特币基地](https://blog.coincodecap.com/gemini-vs-coinbase) | [比特币基地 vs 北海巨妖](https://blog.coincodecap.com/kraken-vs-coinbase) | [CoinJar vs CoinSpot](https://blog.coincodecap.com/coinspot-vs-coinjar)
*   [Bybit vs 币安](https://blog.coincodecap.com/bybit-binance-moonxbt)|[stealth x 回顾](/coinmonks/stealthex-review-396c67309988) | [Probit 回顾](https://blog.coincodecap.com/probit-review)
*   [顶级付费加密货币和区块链课程](https://blog.coincodecap.com/blockchain-courses)
*   [在美国如何使用 BitMEX？](https://blog.coincodecap.com/use-bitmex-in-usa) | [BitMEX 评论](https://blog.coincodecap.com/bitmex-review)
*   [最佳期货交易信号](https://blog.coincodecap.com/futures-trading-signals) | [流动性交易所评论](https://blog.coincodecap.com/liquid-exchange-review)