# 什么是比特币挖矿？[2020 版]

> 原文：<https://medium.com/coinmonks/what-is-bitcoin-mining-84dca020c801?source=collection_archive---------2----------------------->

## *比特币挖掘和共识算法是比特币技术的核心原理。正是它们让比特币变得独一无二，具有革命性。让我们看看这是怎么回事。*

# **比特币挖矿**

我们已经知道，比特币是一个 P2P 去中心化的网络，在这个网络中，我们通过一系列持有去中心化数据库的节点来转移价值，我们没有任何中央权威机构可以依赖。这一切都很好，但在比特币出现之前，我们已经有了这种技术，这项技术的真正好处是与*共识算法*。

挖掘的过程不仅仅是发现新比特币的一种方式，事实上，它还是保护网络安全的主要功能，即在没有任何权威中心的情况下，找到对真实真相的共识——这就是共识算法。

> 另读:[比特币挖矿如何运作？【技术】](https://blog.coincodecap.com/how-bitcoin-mining-work/)

## **奖励制度**

奖励制度是对矿工保护网络的激励。向区块链[添加新的有效区块的矿工](https://blog.coincodecap.com/tag/blockchain/)会收到新创建的硬币，并收取该区块的交易费。如今，他们的主要激励因素是新创造的硬币，交易费仅占他们收入的 0.5%，但随着有限的硬币供应随着时间的推移而减少，交易费也在慢慢增加。

当矿工成功地将新区块添加到区块链时，他们通过在区块内创建特殊交易来支付自己，该交易被称为' ***【比特币基地】'*** 交易，其包括交易的总费用加上随时间减少的硬币数。

## **货币创造**

每次新的区块被添加到区块链，一个新的[比特币](https://blog.coincodecap.com/tag/bitcoin/)就会凭空产生。**2100 万比特币的供应量有限。**为了维持有限且不断减少的货币发行，每四年或每 210，000 个区块创造的新比特币的最大数量会减少。它始于 2009 年，每块 50 个比特币，2012 年减半至 25 个比特币。2016 年 7 月再次减半至 12.5 比特币。据估计，在 2020 年左右(块 630.000)，它将再次减半至 6.25 比特币。与货币创造相关的最后一个区块是第 6 . 720 . 000 个区块，大约在 2137 年开采。从这一点来看，矿商将得到的唯一回报将是交易费。我们必须考虑到，这种固定的货币供应是一种抵御通货膨胀和随着时间的推移而升值的方法。

> ***快速提问*** *:是什么阻止矿工奖励自己比当前设定的奖励多很多？答案是，不正确的奖励会导致该块被网络的其他节点拒绝，浪费大量的电力和资源。*

# **块头创建和挖掘**

挖掘器的主要任务是创建一个具有块头和事务的块，并比其他挖掘器更快地找到*工作证明*算法的解，以便将新块传播到网络并赢得奖励和费用的竞争。要创建块标题，矿工必须遵循以下步骤:

*   选取前一个块哈希头
*   从内存池中挑选事务
*   从挑选的交易中创建 [Merkle 树](/@sheinix/the-bitcoin-blockchain-a3eb996f7140)
*   向块头添加时间戳
*   添加**工作证明**算法的目标(稍后解释)
*   添加初始化为零的 ***随机数*** (稍后解释)

> 通过选择前一个块哈希头，矿工正在提交他的挖掘能力以扩展在该特定块中结束的链，换句话说，对于该链来说是****【buring】***更深的最后一个块，因此增加了该块上的事务的确定性。*

*挖掘是一个*‘友好’*的词，用来描述机器为了解决**工作证明**(又名 **PoW** )算法而产生的计算工作。*

**要理解****PoW****算法我们得先看看什么是哈希算法。**

## ***哈希算法***

*哈希算法是一种函数，它接受任意长度的数据输入，并产生固定长度的确定性输出。它每次都会为相同的输入产生相同的输出。这些算法的主要特点是它们是“*无冲突的*，这意味着在计算上不可能找到产生相同输出的两个不同的输入。在[比特币](https://blog.coincodecap.com/tag/bitcoin/)中，PoW 使用 SHA256 作为其核心哈希函数，它总是返回 256 位长度的输出。还有一个特殊性，那就是无法知道也无法计算哪个输入会产生特定的输出，唯一的方法是根据需要尝试多次，直到达到期望的输出。*

**我们来看一个例子:**

***SHA256('此贴牛逼')=***0 CEA 0123 da 2 b 2638 c9f 5743947 D6 caf 313 c 674 e 651377 C3 c 373115 B3 b 555 aaeb**

*在这种情况下“*0 CEA 0123 da 2b 2638 c9f 5743947 D6 caf 313 c 674 e 651377 C3 c 373115 B3 b 555 aaeb”*是用 SHA256 哈希的结果输出‘这个帖子太牛了’。每次我们将 SHA256 应用到“这篇文章太棒了”时，它都会产生相同的输出。*

*现在，如果我们只添加一个字符:*

***SHA256('此贴很牛逼 1 ')=***f 68930 a 4 da 1c 474 e 0073919 df 822464909180 f 45370 DC 2d 95 e 97 b 7 e 3c 2 e 3f 31d**

*您现在可以看到，稍有不同的输入会产生长度相同但完全不同的输出。同样，如果我们增加变量数，每次都会得到一个新的不同的散列:*

***SHA256('这个帖子很牛逼 2 ')=**e 04 a4 EAF 043434447d 8 fadf 423 c 5776 BD 218461 bb 4c ce 6775129 df 868 E4 C5 ca*

***SHA256('本帖很牛逼 3 ')=***C1 a5 F3 F9 d 98 c 0758 db 3a 81 f 74 a 7 e 1383 b 26 c 44123 c 13 f 40 BF 9 C2 fa f1 c 14660 BD**

***SHA256('这个帖子很牛逼 4 ')=***414d 63 aa 2178 b 594947 C3 C4 EC 4 f 922940 EAD 9 c 18864846632626931 e 9924823**

***SHA256('本帖很牛逼 5 ')=***5a 6530944 bb 1 ba 20972 f 593925 ef 8 b 2 f 4c 64 e 40 a 65 b5 EC 129 a 61886 C5 c 7 cfeb 6**

***SHA256('本帖牛逼 6 ')=***061 c33 a 89 bafc 0 fad 304 befa 219d 508 CDF 134 b 93 BF 44 DBC 0 df 516178 b 26764 fc**

*在比特币中，输入的可变组件编号(上面示例中的编号)称为***【nonce】***，它用于改变输出，也是矿工需要找到的，以便产生小于特定目标的输出。哇！我们在谈论什么目标？？继续读我亲爱的朋友！*

## ***目标和难度***

***目标数**是一个十六进制数，用作随机数和块头的散列输出的阈值。nonce 和块头之间的哈希结果必须小于目标数。有时，我们听说 nonce 和 block header 的结果哈希必须在开头有一定数量的零，这是对同一事情的另一种解释，一个数字在开头的零越多，它就越小，因此目标也就越小。*

> *目标越小意味着难度越大，目标越大意味着难度越小。*

*因此，为了让挖掘器找到 PoW 的具体解决方案，它计算块头的散列和随机数，如果散列不小于目标值，挖掘器将修改随机数(通常只是将它递增 1)并再次尝试，直到它可以找到小于目标值的数。这个过程需要大量的计算能力——*功*。一旦 nonce 被找到，我们可以说这个块的 PoW 被解决了，这是*证明*矿工花费了计算能力试图找到特定的输出，因此得名**工作证明。***

*正如我们所看到的，目标决定了挖掘的难度，因此影响了求解 PoW 算法的时间。平均每 10 分钟就有一批比特币产生，这意味着比特币有固定的货币发行频率，并且在几十年的时间里必须保持不变。在这段时间内，预计计算能力将增长到更快的速度，因此[比特币](https://blog.coincodecap.com/tag/bitcoin/)难度将不得不进行调整，以便将块生成时间保持在 10 分钟。这个过程被称为“*重定目标*”，在每个节点自动发生。每 2016 个块，所有节点通过遵循预设公式重新定位难度:*

****新目标=旧目标*(最后 2016 块的实际时间/ 20160 分钟)****

*这个等式用找到最后 2016 个块所用的时间除以所需的时间量(20160 分钟，每个块 10 分钟)，然后用旧目标乘以该比率。换句话说，如果网络查找数据块的速度快于每 10 分钟一次，难度就会增加，反之，难度就会降低。*

## ***赢得采矿回合***

*那么当一个矿工找到了 PoW 的解并创造了获胜的方块会发生什么呢？在用 PoW 解决方案创建块之后，它做的第一件事就是把它传输给所有的对等体。当网络中的每个其他节点收到新数据块时，它们会对其进行验证，如果它是正确的，它们会将其添加到区块链的本地副本中，从而扩展选定的链。添加积木后，他们放弃该轮的工作，并开始竞争下一轮。*

*当节点接收到新数据块时，它必须通过检查一组特定的规则来验证它:*

*   *数据结构在语法上是有效的*
*   *块头哈希必须小于目标值*
*   *标题块的时间戳必须在未来两小时之内*
*   *块大小介于平均值之间。*
*   *这个街区只有一笔比特币基地交易，而且是第一笔*
*   *该块中的所有交易都有效。*

***如果该块不符合该规则中的至少一条，则该块无效，并且不会被添加到** [**【区块链】**](https://blog.coincodecap.com/tag/blockchain/) 。采矿过程消耗大量电力和资源，因此，如果矿工创建了不符合该规则的恶意或无效区块，它将被拒绝，并将白白浪费大量资源，**这就是为什么独立验证是分散共识的关键组成部分。***

*接收节点的最后一步是将新块添加到区块链的本地副本中。在此之前，我们必须了解节点维护三种不同类型的块:*

1.  *主区块链的街区*
2.  *符合主链分支(次级链)的嵌段*
3.  *还没有父块的块(孤立块)*

****【主链】*** 是拥有最多区块的区块链，或者在两个区块数量相同的链的情况下，它是拥有更多工作证明的链。通过总是选择最长的链，节点可以*为达成共识的 ***【真理】*** (每个人都有相同版本的什么是有效的)。然而，存在这样的情况，节点将维护主链的分支，这些分支的**符合块**是有效的，但是它们不是主链的一部分，并且被保留以备将来参考，以防其中一个分支在工作中被扩展超过主链(解决节点之间的临时差异)。**孤立块**是具有未知“先前块头散列”的块。它们被保存在孤立块池中，直到接收到父块。一旦接收到父项，它们将被链接到父项，并从孤立池中删除。**

***既然我们知道了这个过程的主要组成部分，那么描述起来就很容易了:***

**在节点验证了新块之后，它将查看其**先前的散列块**，并查看它是否在区块链的本地副本上。如果不是，它将把它放在**孤儿池**中以备后用。如果是，它会将新块链接到其父块。如果程序块的父程序块是主链的最后一个程序块，新的程序块现在被认为是**主链**的一部分，如果父程序块的高度小于最大高度(不是最后一个程序块)，它将链接它到它的父程序块，创建一个临时分支，这个分支将在以后解决，因为更多的程序块被添加到每个链的顶部。**

**这就是[比特币](https://blog.coincodecap.com/tag/bitcoin/)在挖掘过程中保护网络的方式——通过独立节点寻找共识。我希望你今天能学到一些新东西，我很感激你能学到这一点。如果你想阅读和了解更多关于区块链技术的知识，可以在 Medium 或 [twitter](https://twitter.com/sheinix) 上关注我。**

**下次见！**

> **[直接在您的收件箱中获得最佳软件交易](https://coincodecap.com/?utm_source=coinmonks)**

**[![](img/7c0b3dfdcbfea594cc0ae7d4f9bf6fcb.png)](https://coincodecap.com/?utm_source=coinmonks)**

# **行动呼吁**

**[如果您想了解更多关于区块链的信息，请加入我们的每周简讯，了解来自加密领域的所有新闻。](https://mailchi.mp/fe27d17793e9/cryptolitics)**

**[![](img/e9dbce386c4f90837b5db529a4c87766.png)](https://coincodecap.com)**