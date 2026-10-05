---
title: Campaign版本、升级和安全性
description: 了解关于Campaign版本和升级的更多信息
feature: Release Notes
role: User
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: bd8e8abb2d53dd9b7b3afcc82c283aa25111a0ff
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 7%
---
# 版本、升级和安全性 {#upgrades}

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

## Campaign版本和升级 {#versions}

Adobe Campaign会定期发布产品版本，以提高Campaign基础架构的性能、安全性、逻辑和可用性。

这些升级可以是：

* **主要升级**，从主要版本到另一个主要版本，例如从v7到v8。 这些升级带来了新功能、改进、兼容性和安全更新以及修复。
* **从次要版本到其他版本的次要升级**，例如从v8.5到v8.6。 这些升级包括改进、兼容性、安全更新和修复。
* **修补程序升级**，从修补程序版本升级到其他修补程序版本，例如从v8.5.1升级到v8.5.2。 这些升级带来了安全更新和修复。

有关每个新版本的详细信息，请参阅[发行说明](release-notes.md)。 每个发行说明中都介绍了与安全相关的修复。 有关安全通知的详细信息，请参阅[随时了解情况](#security-staying-informed)。

为确保配置稳定，Adobe建议您在所有Campaign服务器上安装&#x200B;**完全相同的版本**。 此外，除[发行说明](release-notes.md)中另有提及外，客户端控制台必须使用&#x200B;**与服务器实例完全相同的版本**。 [在此页面](../start/connect.md#upgrade-ac-console)中了解如何升级客户端控制台。

### 使您的客户端控制台保持最新 {#ac-upgrades}

作为Campaign Managed Services客户，当有新的Campaign版本可用时，您的服务器基础架构会由Adobe升级，无需您执行任何进一步操作。

由于服务器升级是自动进行的，因此&#x200B;**客户端控制台**&#x200B;是一个未同时更新时可能会显示空隙的位置。 如果控制台版本与服务器版本不匹配，请执行以下操作：

* 在更新控制台之前，您可能会失去连接到Campaign实例的功能。
* 您的主机停止从服务器已移动到的版本中提供的修复和安全更新中获益 — 即使服务器本身是最新的。

要避免此情况，请在收到新版本通知后立即升级客户端控制台。 了解如何[升级您的客户端控制台](../start/connect.md#upgrade-ac-console)。

请注意，作为客户，您还必须确保使用[兼容性矩阵](compatibility-matrix.md)中列出的系统的最新支持版本。

### 检查 Campaign 版本 {#version}

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

### 随时了解最新版本 {#upgrades-0}

新版本及其更改列在[发行说明](release-notes.md)中。

有关产品版本更新，请订阅[Adobe优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target="_blank"}或访问[Campaign社区](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?profile.language=zh-Hans&style=all&sort=date&order=desc&filters=adobe-campaign-classic-community&topic=Campaign+v8){target="_blank"}。

有关准备组织进行安全更新的安全通知和指导，请参阅[随时了解情况](#security-staying-informed)。

### 升级的优势 {#upgrades-1}

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

### 升级流程和时间表 {#upgrades-2}

作为v8客户，Adobe端到端地管理您的服务器升级：

1. 当有新版本可用或您的帐户被确定需要迁移到某个版本时，您的Adobe代表会通知您。
1. Adobe升级您的服务器基础架构 — 执行此步骤无需您执行任何操作。
1. 在您这边，只需升级客户端控制台以匹配即可，并且仍支持[兼容性矩阵](compatibility-matrix.md)中的系统。 查看[使您的客户端控制台保持最新](#ac-upgrades)。

一支由专业的客户关怀代表、产品经理、工程师、技术运营专家和产品顾问组成的团队将为您提供帮助并确保实现流畅的体验。

>[!NOTE]
>
>关键安全修补程序可能会在此通知周期之外应用到您的托管环境 — 请参阅此页面顶部的说明。

## 更快地保护Adobe Campaign客户：Adobe如何与安全性保持同步 {#campaign-security}

### 查找更多、更快的内容 {#finding-more-faster}

正如我们在[更快地保护客户：Adobe如何响应AI加速的漏洞发现](https://blog.adobe.com/security/protecting-customers-faster-how-adobe-is-responding-to-ai-accelerated-vulnerability-discovery)中分享的那样，Adobe安全团队使用AI辅助工具更快地识别和解决漏洞。 我们在我们的产品（包括Adobe Campaign）中均采用这种方法。

本节介绍我们如何评估和确定安全问题的优先级、如何部署修复程序以及这对于您意味着什么。

### 我们如何评估和确定安全问题的优先级 {#assess-security-issues}

并非每个安全问题都有相同的风险。 Adobe按严重性限定每个问题，该严重性设置优先级别。

零日漏洞是一个以前未知的漏洞，攻击者可在修复之前利用它，因此可能需要在常规发布计划之外采取紧急措施。 我们通过[Adobe安全公告](https://www.adobe.com/trust/security/bulletins-and-advisories.html)（通常在每个月的第二和第四个星期二发布）来解决大多数其他漏洞。

我们的响应目标将遵循此严重性评估。 对于一些比较严重的问题，我们首先关闭暴露窗口，然后尽可能快地共享相关细节。 这就是为什么一些修复措施很少或根本没有提前通知您。 该时间取决于漏洞的严重程度。 每次更新（包括紧急更新）在发货前都经过质量验证。

### 我们如何部署修补程序 {#deploy-security-fixes}

我们会在发布之前验证安全更新，并根据更改范围选择部署方法。 我们的目标是尽量减少干扰。

根据更新的范围，我们使用以下两种部署方法之一：

* **安全栈栈维护**：目标更新不会更改您的内部版本号或引入对产品功能的预期更改。 使用标准配置的客户通常不需要采取行动。
* **安全驱动的内部版本升级**：更改您的内部版本号并遵循Adobe的标准通知、发行说明和转出流程的更新。

对于开箱即用的标准配置，您的集成和正在运行的营销活动将保持与之前相同的运行状态。

我们设计安全更新以保持与标准Adobe Campaign配置的兼容性，并最大程度地减少对客户操作的中断。 如果您的环境包含自定义集成、脚本或其他修改，请在内部版本升级后执行贵组织的验证过程。 如果您遇到意外行为，请联系Adobe客户支持。

### 随时了解情况 {#security-staying-informed}

您无需立即采取行动，但这些步骤可以帮助您的组织随时了解情况并高效响应：

* 让您的帐户和技术联系人保持在Adobe Admin Console中的最新状态，以便通知可送达适当的人员。
* 订阅[Adobe安全通知](https://www.adobe.com/subscription/adobesecuritynotifications.html)以获取新公告和通知。
* 审查您组织的变更管理流程，以便您能够迅速评估并响应安全更新。

### 我们的承诺 {#security-commitment}

Adobe致力于帮助保护您的Adobe Campaign环境，并在出现安全问题时快速响应。 我们将继续加强安全流程，同时努力将运营中断降至最低。