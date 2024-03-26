---
title: Campaign版本和升级
description: 了解关于Campaign版本和升级的更多信息
feature: Release Notes
role: User
level: Beginner
exl-id: 04bda36f-051f-41a3-84b3-6af3c5e34ab2
source-git-commit: a779f243b0ba13dc3fcb7839377ca8766e5f7841
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 18%

---

# 版本和升级 {#upgrades}

## Campaign版本 {#versions}

Adobe Campaign会定期发布产品版本，以提高Campaign基础架构的性能、安全性、逻辑和可用性。

这些升级可以是：

* **重大升级**，从主要版本到另一个版本，例如从v7到v8。 这些升级带来了新功能、改进、兼容性和安全更新以及修复。
* **次要升级**，从次要版本到另一个版本，例如从v8.5到v8.6。这些升级包括改进、兼容性、安全更新和修复。
* **修补程序升级**，从修补程序版本迁移到另一个修补程序版本，例如从v8.5.1到v8.5.2。这些升级带来了安全更新和修复。

有关每个新版本的详细信息，请参见 [发行说明](release-notes.md).

为确保配置稳定，Adobe建议您安装 **完全相同的版本** 在您的所有Campaign服务器上。 此外，除 [发行说明](release-notes.md)，客户端控制台必须打开 **完全相同的版本** 作为服务器实例。 [在此页面](../start/connect.md#upgrade-ac-console)中了解如何升级客户端控制台。

作为Campaign Managed Services客户，当有新的Campaign版本可用时，您的基础架构会通过Adobe进行升级，而无需执行任何进一步操作。

请注意，作为客户，您必须确保使用 [兼容性矩阵](compatibility-matrix.md).


## 常见问题解答 {#upgrades-faq}

### 如何检查我的Campaign版本？ {#version}

要检查您的Campaign版本，请访问 **帮助>关于……** 客户端控制台中的菜单。

![](assets/ac-version.png)

您可以访问以下信息：

* 此 **版本** 客户端控制台和应用程序服务器的数量。 在上面的示例中，客户端控制台和应用程序服务器的版本均为8.1.5。
* 用圆括号括起的 SHA 编号。
* 用于联系 Adobe 客户关怀团队的链接。
* 指向 Adobe 隐私政策、使用条款和 Cookie 政策的链接。

### 如何通知我已发布新版本？ {#upgrades-0}

新版本及其带来的更改将列在 [发行说明](release-notes.md). 新版本可用后，Adobe将与您联系并升级您的环境。

要获悉新的 Experience Cloud 解决方案版本，请订阅 [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target="_blank"}。

您也可以访问 [Campaign社区](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?style=all&amp;sort=date&amp;order=desc&amp;filters=adobe-campaign-classic-community&amp;topic=Campaign+v8){target="_blank"} 以获悉版本更新。


### 我的组织为什么需要此升级？ {#upgrades-1}

将您的基础架构升级到最新版本可确保您的帐户免受漏洞攻击，并使用更新后的性能技术。

通常，升级到最新版本会带来：

* 提高了安全性

  安全性需要持续关注和主动维护。 安全风险无处不在，不容忽视：Campaign的每次升级都会提高安全性。 这些升级必须应用于您的所有Campaign实例以及客户端控制台。 技术组合可支持Adobe Campaign共同创造价值。 所有这些技术都必须保持最新？

* 改进的支持

  大多数关键问题实际上都可以通过升级解决，并且可以避免。 定期升级有助于减少面临的挑战，并通过消除这些挑战来提高效率。 客户关怀工作量得以减少，从而可以加快解决速度并更多地关注与升级无关的问题。


* 更好的维护和稳定性

  随着时间的推移，Adobe Campaign团队会找出提高产品稳定性和性能的方法，并修复已知问题。 升级可使您的实例及时受益于这些改进，并消除在Campaign实例增长快速和/或复杂性增加的情况下组织所面对的常见挑战。您的营销和IT团队都能感受到为Campaign提供支持的整个技术栈栈中的改进。


### 此升级的流程和时间线是什么？ {#upgrades-2}

作为v8客户，如果已确定您的帐户需要升级到新版本，则Adobe会直接通知您。

Adobe团队将引导和指导您的组织完成这一过程。 一支由专职客户关怀代表、产品经理、工程师和技术运营专家以及产品顾问组成的团队将为您提供帮助并确保实现流畅的体验。
