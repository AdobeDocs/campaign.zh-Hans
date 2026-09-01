---
title: Campaign版本和升级
description: 了解关于Campaign版本和升级的更多信息
feature: Release Notes
role: User
level: Beginner
exl-id: 04bda36f-051f-41a3-84b3-6af3c5e34ab2
TQID: https://experienceleague.adobe.com/EaoWEmt7vNplA6Cs6CdMvP-iwia6BkaDRjawsPoa6fs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 59a1ad4bbb194222f0c2b86117cc7dc6ecc3335d
workflow-type: tm+mt
source-wordcount: 1190
ht-degree: 10%

---

# 版本和升级 {#upgrades}

Adobe Campaign v8是作为&#x200B;**Managed Cloud Services**&#x200B;解决方案专门提供的。 Adobe会为您管理和执行每次服务器端升级 — 没有内部部署或混合部署v8，也没有服务器升级可自行安排或执行。

Adobe Campaign 会定期更新。 这种定期更新旨在让您掌握最新、最充分的信息，保持环境的安全，并改进您对我们产品的体验。

作为托管云服务用户：

* 您的Campaign服务器实例会由Adobe通过每个新版本自动升级，无需您执行任何操作。
* 在会对您的环境造成影响的升级之前，您的Adobe代表会联系您。
* **您的客户端控制台是您负责保持最新状态的组件。** 必须将其升级到与Campaign服务器相同的版本。 要了解如何升级客户端控制台，请参阅[此页面](../start/connect.md#upgrade-ac-console)。

此外，作为客户，请确保使用的是[兼容性矩阵](compatibility-matrix.md)中列出的最新受支持的系统版本。

>[!IMPORTANT]
>
>Adobe保留随时将关键安全补丁应用于托管环境的权利，恕不另行通知，以尽快修复漏洞。 部署这些修补程序时不会中断服务。 修复严重漏洞优先于高级通知。

## Campaign版本 {#versions}

Adobe Campaign会定期发布产品版本，以提高Campaign基础架构的性能、安全性、逻辑和可用性。

这些升级可以是：

* **主要升级**，从主要版本到另一个主要版本，例如从v7到v8。 这些升级带来了新功能、改进、兼容性和安全更新以及修复。
* **从次要版本到其他版本的次要升级**，例如从v8.5到v8.6。 这些升级包括改进、兼容性、安全更新和修复。
* **修补程序升级**，从修补程序版本升级到其他修补程序版本，例如从v8.5.1升级到v8.5.2。 这些升级带来了安全更新和修复。

有关每个新版本的详细信息，请参阅[发行说明](release-notes.md)。 每个版本的注释中均列出了安全相关的修复 — 请参阅[如何通知我新版本的发布？](#upgrades-0) 下。

为确保配置稳定，Adobe建议您在所有Campaign服务器上安装&#x200B;**完全相同的版本**。 此外，除[发行说明](release-notes.md)中另有提及外，客户端控制台必须使用&#x200B;**与服务器实例完全相同的版本**。 [在此页面](../start/connect.md#upgrade-ac-console)中了解如何升级客户端控制台。

## 使您的客户端控制台保持最新 {#ac-upgrades}

作为Campaign Managed Services客户，当有新的Campaign版本可用时，您的服务器基础架构会由Adobe升级，无需您执行任何进一步操作。

由于服务器升级是自动进行的，因此&#x200B;**客户端控制台**&#x200B;是一个未同时更新时可能会显示空隙的位置。 如果控制台版本与服务器版本不匹配，请执行以下操作：

* 在更新控制台之前，您可能会失去连接到Campaign实例的功能。
* 您的主机停止从服务器已移动到的版本中提供的修复和安全更新中获益 — 即使服务器本身是最新的。

要避免此情况，请在收到新版本通知后立即升级客户端控制台。 了解如何[升级您的客户端控制台](../start/connect.md#upgrade-ac-console)。

请注意，作为客户，您还必须确保使用[兼容性矩阵](compatibility-matrix.md)中列出的系统的最新支持版本。

## 常见问题解答 {#upgrades-faq}

### 如何检查我的Campaign版本？ {#version}

要检查您的Campaign版本，请从客户端控制台访问&#x200B;**帮助>关于……**&#x200B;菜单。

![](assets/ac-version.png)

您可以访问以下信息：

* 客户端控制台和应用程序服务器的&#x200B;**版本**&#x200B;编号。 在上面的示例中，客户端控制台和应用程序服务器的版本均为8.1.5。
* 用圆括号括起的 SHA 编号。
* 用于联系 Adobe 客户关怀团队的链接。
* 指向 Adobe 隐私政策、使用条款和 Cookie 政策的链接。

>[!NOTE]
>
>如果为客户端控制台显示的版本与为应用程序服务器显示的版本不匹配，请按照[使客户端控制台保持最新](#ac-upgrades)中的说明升级控制台。

### 如何通知我已发布新版本？ {#upgrades-0}

新版本及其带来的更改（包括安全修复）列在[发行说明](release-notes.md)中。 新版本可用后，您的Adobe代表会联系您并升级您的服务器环境；您将需要单独升级您的客户端控制台（请参阅[使您的客户端控制台保持最新](#ac-upgrades)）。

要获悉新的Experience Cloud解决方案版本及其内容，请订阅[Adobe优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target="_blank"}通信。

您还可以访问[Campaign社区](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?profile.language=zh-Hans&style=all&sort=date&order=desc&filters=adobe-campaign-classic-community&topic=Campaign+v8){target="_blank"}以获悉版本更新。

### 为什么我的组织需要升级？ {#upgrades-1}

升级可确保您的帐户免受漏洞攻击，并使用最新的性能技术。

通常，升级到最新版本会带来：

* **安全性提高**

  需要持续关注和主动维护安全性。 安全风险无处不在，不容忽视 — Campaign的每次升级都会提高安全性。 各种技术的组合共同为Adobe Campaign提供支持，并且所有这些技术都必须保持最新。 Adobe会自动将这些更新应用于您的服务器；在步骤中升级您的客户端控制台可以确保对其实施同样的保护。

* **改进的支持**

  大多数关键问题都可以通过升级解决，并且可以完全避免。 定期升级有助于减少您面临的挑战并提高效率。 客户关怀工作量得以减少，从而可以加快解决速度并更多地关注与升级无关的问题。

* **改进的维护和稳定性**

  随着时间的推移，Adobe Campaign 团队会找出提高产品稳定性和性能的方法，并修复已知问题。 升级可使您的实例及时受益于这些改进，消除在Campaign实例增长快速和/或复杂性增加的情况下组织所面对的常见挑战。 您的营销和IT团队都能感受到为Campaign提供支持的整个技术栈栈中的改进。

* **保持连接**

  您的客户端控制台只能与运行相同版本的服务器可靠通信。 保持主机最新（每次升级服务器时）是保持此连接，以及随之而来的安全和修复完整性的因素。

### 升级的流程和时间线是什么？ {#upgrades-2}

作为v8客户，Adobe端到端地管理您的服务器升级：

1. 当有新版本可用或您的帐户被确定需要迁移到某个版本时，您的Adobe代表会通知您。
1. Adobe升级您的服务器基础架构 — 执行此步骤无需您执行任何操作。
1. 在您这边，只需升级客户端控制台以匹配即可，并且仍支持[兼容性矩阵](compatibility-matrix.md)中的系统。 查看[使您的客户端控制台保持最新](#ac-upgrades)。

一支由专业的客户关怀代表、产品经理、工程师、技术运营专家和产品顾问组成的团队将为您提供帮助并确保实现流畅的体验。

>[!NOTE]
>
>关键安全修补程序可能会在此通知周期之外应用到您的托管环境 — 请参阅此页面顶部的说明。
