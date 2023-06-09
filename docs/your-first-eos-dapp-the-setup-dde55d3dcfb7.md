# 您的第一个 EOS dApp —设置

> 原文：<https://medium.com/coinmonks/your-first-eos-dapp-the-setup-dde55d3dcfb7?source=collection_archive---------1----------------------->

![](img/602f820e91e4d2c23c41c320bef7db55.png)

## EOS 简介

EOS 有望成为下一个*以太坊杀手*，虽然这仍有待观察，但这款产品有一些非常棒的下一代功能。我相信您已经阅读了数千篇吹捧 DPOS 扩展能力的文章(授权的利益相关证明)，但是在 EOS 的引擎盖下还有许多其他伟大的东西。我对保管方案特别感兴趣，如果我丢失了我的私钥，我可以选择一个可信任的方来帮助恢复对我的帐户的访问。还有一个概念是一个帐户的所有者密钥和活动密钥，它允许您最小化每天交易的负债。人类可读的帐户名也是一个长期以来一直需要的特性。不过，我在东拉西扯——让我们继续吧。

# 我们的项目

对于我们的示例契约和 dApp，我们将创建一些实际上有用的东西——学校招生彩票。任何有学龄儿童的父母都知道，让你的孩子进入一所好学校可能是一件困难的事情，这取决于你住在哪里。有时候，进入一所好学校的唯一方法就是参加他们的抽奖，祈祷学校的工作人员遵守规则。希望工作人员不会偏袒和操纵系统，但除非我们有一个开放的智能合同来消除人为错误，否则谁会真正知道呢？我们将尝试创建这个智能契约和一个简单的 dApp 来与之交互。

# 设置

## 构建 EOS

我们将使用当地的 EOS 链，因为这是目前唯一可靠的。你需要按照这里[的说明](https://github.com/EOSIO/eos/wiki/Local-Environment#1-getting-the-code)来安装黎明 4 版本。

一旦您安装并编译了 EOS，您应该能够从您的根 EOS 目录运行以下内容。

```
./build/programs/nodeos/nodeos -e -p eosio --plugin eosio::wallet_api_plugin --plugin eosio::chain_api_plugin --plugin eosio::account_history_api_plugin
```

假设您安装成功，您也可以访问下面包含的实用程序

*   **cleos** —一个 CLI 工具，用于管理账户、部署合同/与合同互动等等
*   eosiocpp —一个 eos 编译器，它将生成。wast(合同 web 程序集)和。部署需要 abi(合同接口)
*   **nodeos** —负责启动/停止和一般链管理命令的工具
*   **keosd** —虽然我们使用 **cleos** 来创建我们的钱包，但是在这里完成工作的底层钱包管理工具是 **keos**

## 创建钱包

让我们继续创建一个用于发送和接收资金的钱包。我们可以使用 **cleos** 创建名为*彩票*的钱包，如下所示

```
cleos wallet create -n lottery
```

您应该会看到这个方法输出的密码散列。保存此密码，因为这是您解锁*彩票*钱包的唯一方式。这不是你的*私人钥匙*但是应该小心处理。

## 创建密钥

现在我们已经创建了*彩票*钱包，让我们创建一个帐户来与我们的智能合同交互。我们将再次使用 **cleos** 命令如下

**生成所有者密钥(私有/公共)**

```
cleos create key
```

您将在上述命令的输出中获得一个公钥和一个私钥。根据您的需要，将这些值保存在安全的地方。

**将所有者私钥导入钱包**

您现在可以使用下面的命令将上一步生成的私钥导入新的*彩票*钱包

```
cleos wallet import <private key hash> -n lottery
```

**生成活动密钥(私有/公共)**

我们现在将做和以前一样的事情，除了这将是我们的活动钥匙。这是一个二级账户，应用于日常小额或可忽略价值的交易。

```
cleos create key
```

您将在上述命令的输出中获得一个公钥和一个私钥。根据您的需要，将这些值保存在安全的地方。

**将活动私钥导入钱包**

您现在可以使用下面的命令将上一步生成的私钥导入新的*彩票*钱包

```
cleos wallet import <private key hash> -n lottery
```

**创建账户**

在这里，我们将其绑定在一起，并创建一个名为*彩票的账户。代码*我们指定哪些关键帧属于所有者/活动子账户。在典型的区块链钱包中，你有一个公钥和一个私钥或一个助记符，但在 EOS 中，我们有一个人可读的账户名，有两个子账户(活动账户和所有者账户)。指定的*所有者*公钥被指定来处理所有者级别的账户访问，而*活动的*公钥被归入简单交易，无权进行账户级别的更改。这是一个非常有用的权力分离。运行以下命令创建您的帐户。在我们的案例中，*彩票. code* 账户将拥有并管理我们的智能合同，我们将在下一篇文章中设置该账户。

```
cleos create account eosio lottery.code <owner public key> <active public key>
```

*请注意，eosio 是一个系统级帐户，默认情况下会出现在我们的测试链中。我不确定它是否会在随后的版本中发布，或者替代版本会是什么。*

另一个需要注意的有用的事情是，帐户只通过它们作为所有者和活动密钥链接的公钥链接到钱包。您可以使用相同的所有者/活动密钥创建多个帐户。此[链接](https://github.com/EOSIO/eos/wiki/Tutorial-Comprehensive-Accounts-and-Wallets)非常有用，详细介绍了 EOS 中的钱包/账户管理。

## 摘要

我们在这篇文章中做了很多。我们设置我们独立的 EOS 链和我们需要的钱包和帐户。我们还为我们的项目做好了准备，并更深入地研究了 EOS 的客户管理。在我们的下一篇文章中，我们将探索实际创建和部署我们的教育彩票智能合同。