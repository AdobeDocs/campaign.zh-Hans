---
product: Adobe Campaign
title: 开始使用 Campaign v8
description: Campaign的新用户？ 了解如何快速入门
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 95%

---

# 开始使用 Adobe Campaign{#gs-ac-v8}

Adobe Campaign 提供了跨渠道客户体验设计平台，并为可视化的活动编排、实时互动管理和跨渠道执行提供了环境。

使用 Campaign 可以：

* 通过可访问的单一客户视图&#x200B;**推动**&#x200B;个性化和参与
* 将电子邮件、移动设备、线上和线下渠道&#x200B;**整合**&#x200B;到客户历程中
* **自动**&#x200B;投放有意义、及时的消息和优惠

![](assets/ac-capabilities.png)

## 整合的客户档案 {#integrated-customer-profile}

用户档案集中存储在一个功能强大的云数据库中。有许多可能的机制可获取用户档案并创建此数据库：通过 Web 窗体在线收集、手动或自动导入文本文件、复制公司数据库或其他信息系统的内容。借助 Adobe Campaign，您可以整合营销历史、购买信息、偏好、CRM 数据，以及整合视图中任何相关的 PII 数据，从而进行分析并采取行动。

在 Adobe　Campaign 中，收件人是发送投放内容（电子邮件、SMS 等）所定位的默认用户档案。凭借数据库中存储的收件人数据，您可以过滤将接收任何给定投放的目标并在投放内容中添加个性化数据。数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

[!DNL :bulb:] 用户档案管理基础知识在[本节](audiences.md)中有说明。

[!DNL :bulb:]请参阅[本节](import.md)以了解如何向 Campaign 添加用户档案。

## 目标市场细分 {#targeted-segmentation}

Adobe Campaign 具有功能强大且易于使用的市场细分和定位功能，让您可以打造极具针对性的差异化优惠方案。您可以使用描述性分析功能分析营销活动的上游和下游信息，而过滤器管理及图形查询编辑器功能可用于过滤订阅者群体及样本，或根据无数量限制标准设定目标组。

高级数据管理功能可进一步扩展数据处理能力。通过包含未在数据集市中建模的数据，该功能可简化并优化定位流程。

[!DNL :bulb:]请参阅[本节](audiences.md)以了解关于分段、受众创建和个性化的更多信息。

## 跨渠道活动编排 {#cross-channel-campaign-orchestration}

您可以利用 Adobe Campaign 在多个渠道上设计和编排有针对性的个性化活动：电子邮件、直邮、SMS、推送通知等。通过单个界面为您提供计划、编排、配置、个性化、自动化、执行和衡量所有活动和通信所需的全部功能。

[!DNL :bulb:]请参阅[本节](campaigns.md)以了解如何设计、计划和执行活动。

## 工作流

Adobe Campaign 提供了一个全面的图形环境，允许您设计包括分段、活动执行、文件处理等在内的复杂流程。例如，您可以使用某个工作流从服务器下载文件、解压缩，然后将其记录导入 Adobe Campaign 数据库。

工作流还可能会涉及用户，为他们分配任务或让他们批准已执行的任务。这意味着，您可以向一个或多个用户分配任务，以处理内容或指定目标，并在发送消息之前批准验证。

工作流可以在不同的上下文中使用，例如：

* 定位以管理受众或发送消息。
* 进行数据管理 (ETL) 以处理数据。
* 将数据导入 Campaign 数据库。
* 数据库清理、恢复跟踪信息等技术流程。

[!DNL :bulb:]请参阅[本节](../config/workflows.md)以了解如何设计和执行工作流。

## 报告和分析{#analysis-and-reporting}

Adobe Campaign 可逐步丰富客户数据和用户档案，从而让您监测和解读客户的行为。利用报告和分析工具，您可以充分利用每一个新活动、更有效地确定营销方案的目标，且最大限度提高活动的影响力及投资回报率。

[!DNL :bulb:]请参阅[本节](reporting.md)以了解有关报告和跟踪功能的更多信息。

## Adobe Experience Cloud 集成 {#adobe-experience-cloud-integrations}

您可以将 Adobe Campaign 的投放功能以及高级营销活动管理功能与帮助您个性化用户体验的解决方案（例如 Adobe Experience Manager、Adobe Analytics、Adobe Target 或 Adobe Experience Cloud 触发程序）结合起来。

[!DNL :bulb:]请参阅[本节](../connect/integration.md)以了解如何与 Adobe 服务和解决方案进行集成。

## 关于 Campaign 功能的更多信息 {#core-capabilities-and-add-ons}

根据您的需求和架构，Adobe Campaign 提供了一系列功能，帮助您实施和优化各种对话式营销功能。其中有些是核心功能，有些功能取决于软件包的安装和您的配置。此处提供了详细的产品说明：[Adobe Campaign v8 产品说明](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html)。

[!DNL :bulb:] 已经熟悉了 Campaign Classic？在[此页面](capability-matrix.md)中了解 Campaign Classic 和 Campaign v8 之间的主要差异。

## 工作区和自定义

Campaign 工作区可通过[客户端控制台](../dev/general-architecture.md)使用。

![](assets/home-page.png)

[!DNL :bulb:] [了解关于 Campaign 客户端控制台的更多信息](../start/connect.md)。

Campaign 工作区可以根据您的需求进行调整。

[!DNL :arrow_upper_right:] 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=zh-Hans)以了解如何使用 Campaign 工作区{target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:]  了解如何在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=zh-Hans)中自定义列表。{target=&quot;_blank&quot;}

您还可以通过 Web 访问某些功能。

[!DNL :bulb:] [了解关于 Campaign Web Access 的更多信息](../start/connect.md#web-access)。


## 语言

Campaign v8 用户界面提供以下语言版本：

* 英语（英国）
* 英语（美国）
* 法语
* 德语
* 日语

在安装过程中选择语言。

>[!CAUTION]
>
>创建实例后，无法更改语言。

受语言影响的日期和时间格式。有关更多信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=zh-Hans#date-and-time){target=&quot;_blank&quot;}。

**另请参阅**

* [Campaign v8兼容性矩阵](compatibility-matrix.md)
* [连接到 Campaign](connect.md)
* [常见问题解答](campaign-faq.md)