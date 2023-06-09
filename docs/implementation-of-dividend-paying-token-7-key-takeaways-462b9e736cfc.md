# 我第一次实施派息令牌的 7 个要点

> 原文：<https://medium.com/coinmonks/implementation-of-dividend-paying-token-7-key-takeaways-462b9e736cfc?source=collection_archive---------1----------------------->

## 最近，我挑战自己，实施了一种所谓的派息代币。这是一个基于区块链以太坊的智能合约，允许人们分享一些资产，并在以后从中受益。

![](img/f9b32093cdebf6c10375bda422b42cb9.png)

什么是派息代币？一个很容易想象的例子是一个人买不起的公寓，但是如果一群人共同努力就会容易得多。在这种情况下，这些公寓的股东最终应该分担成本，分享收益——公寓每月赚取的租金。

让我们想象一下，在下面的场景中，三个朋友决定一起买一套公寓。

![](img/8f3987ff830b0010da7611e78f2f184f.png)

Initial shares situation that will be referenced later

Alice、Bob 和 Joe 贡献了不同的金额，因此他们现在可以期待不同的福利。如果公寓已经被租出去过周末并赚了 1000 美元，Alice、Bob 和 Joe 将分别得到 150 美元、600 美元和 250 美元。

在提到的例子中:
-公寓是有股息的象征，
-爱丽丝、鲍勃和乔是股东，
-公寓赚取的 1000 美元是股息

## 当心

这里的整个例子展示了**我对编码任务的个人想法**。它还没有公开部署，仍然是我的一个理论实验。它的目的不是任何形式的建议，尤其不是投资或会计方面的建议。**请记住，部署智能合约不可避免地会带来一些漏洞和风险，并且可能会被利用来攻击您和您的解决方案。**

# 不要从头开始

## 第一个陷阱——缺乏良好的基础

首先，我只关注股息分配，我忘记了公寓不仅是一个支付股息的代币，还是一个常规的可转让代币，与 ERC-20 标准有许多共同之处。它可以在网络地址之间自由传输，一个网络地址可以有一些余额，也可以有在网络地址之间传输的余量。这些特性无疑表明 ERC-20 标准是预期用例的完美基础。

## 优化内存利用率

作为一个整体，智能合约开发中棘手的部分是努力优化计算复杂性和内存使用。我最初在平面智能合约中存储了每个股东拥有多少股份的登记册。有一种更好的方法可以优化天然气的使用，从而降低交易成本。更省油的方法是尽量减少你多余储存的东西。公寓应该很少存储关于其共同拥有者的数据。在大多数简单的情况下，有一份公寓共有人的地址清单就足够了。
因此，我不应该单独存储用户的份额计数，因为它已经存储为令牌 ERC-20，可以使用`balanceOf`方法获取。

![](img/667a5842359313e6de7457ce15e57357.png)

# 用区块链的方式思考

## 不迭代

起初，我将股份登记簿存储在公寓合同端，并且每次都遍历所有股东的列表。这当然是气体低效的，因为操作的数量太高，而它可以被最小化。

![](img/f8ee3dc4f398c12e7c65c7d25e848bb7.png)

我提到的迭代是完全错误的，因为我坚持立即支付所有股息，而不是按照明确的共同所有者的要求。这种差异是显著的，尤其是当共有人的数量增加时。这导致每次获得红利时，都需要进行一系列的操作，而在惰性方法中，当没有人向你索要红利时，你可能什么都不需要做。

我猜这是这次编程实验最关键的收获。对于开发人员来说，从不同的角度思考简单的事情是一种令人耳目一新的体验。对此有价值的资源有:
[*https://WEKA . medium . com/dividend-bearing-token-on-ether eum-42d 01c 710657*](https://weka.medium.com/dividend-bearing-tokens-on-ethereum-42d01c710657)*[*https://programtheblockchain . com/posts/2018/02/07/writing-a-simple-dividend-token-contract/*](https://programtheblockchain.com/posts/2018/02/07/writing-a-simple-dividend-token-contract/)*

## ***有取款登记簿***

*如前所述，合同不会立即支付任何费用。它一直等到有人来，想把自己挣的房租份额拿走。*

*为了实现这一点，我们需要有一个登记册，以防这个人过一会儿再来。这样的登记簿可以以不同的方式实现，然而，它的主要目标是能够告诉特定的股东自从他们最近的退出请求以来，公寓已经为他们赚了多少。特别是因为每个股东都可以自由使用他们的余额，并可以自由提取。我想没有必要把它弄得太高级，我没有不间断地跟踪所有提款，只是最近提款的**时刻**。我指的是到目前为止从合同中获得的总金额。下面让我们来看看它的实际应用。*

*![](img/0ce2a9f572026d1ee073d730d191fc7c.png)*

*Storing the total income of the smart contract as a time instance in a register enables the lazy approach.*

## *保持清洁*

*只要平仓股的情况保持不变，最近的提款登记簿就能正常工作。如果一个用户决定将他们的部分股份转让给任何其他用户，撤销登记就变得没有用了，因为它没有记录股份的变化。为了减轻这种情况，该单位需要计算欠每个股份转让参与者的资金，或者保存在另一个登记簿中，或者让转让参与者提取该资金。*

*![](img/ce91a86eb89edf448abb1ec59403ebb7.png)*

## *对您的解决方案进行单元测试*

*毫无疑问，推迟红利支付和优化内存利用增加了解决方案的复杂性，这本身就是一个加入单元测试的足够好的理由。在这个例子中，我使用了 hardhat，单元测试一直是我与契约交互的唯一接口。这也证明了在安全帽上编写单元测试是很容易的，当然对于这种算法性质的问题来说，这种努力是值得的。*

## *明智地计算*

*你引入的数学不可避免地会带来一些陷阱。例如，将两个数字相除可能会让你陷入永远失去提醒的问题。意识到这一点，并据此进行规划。我分析得还不够深入，但我充分意识到问题的存在。你可能已经注意到，在所有的例子中，我都是基于没有引入除法余数的特定数字，因此要处理的数学是如此简单。*

# *包扎*

*下一次我处理支付股息的令牌场景时，我将:*

*   *如果通用部件及其接口支持，则使用 ERC-20*
*   *避免数组循环*
*   *寻找将计算推迟到需要时的可能性*
*   *当心数学相关的问题*
*   *毫不犹豫地用单元测试覆盖解决方案*