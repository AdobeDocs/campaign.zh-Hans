---
solution: Campaign v8
product: Adobe Campaign
title: Campaign v8入门
description: 发现关键功能、用户界面和全局指南
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 42%

---

# 开始使用Adobe Campaign{#gs-ac-v8}

Adobe Campaign提供了跨渠道客户体验设计平台以及可视活动编排、实时交互管理和跨渠道执行的环境。

使用Campaign可以：

* **** 通过客户的单一可访问视图促进个性化和参与
* **** 将电子邮件、移动设备、在线和离线渠道集成到客户历程中
* **** 自动交付有意义且及时的消息和优惠

![](assets/ac-capabilities.png)

## 整合的客户档案 {#integrated-customer-profile}

用户档案将集中在功能强大的云数据库中。 有许多可能的机制可获取用户档案并创建此数据库：通过 Web 窗体在线收集、手动或自动导入文本文件、复制公司数据库或其他信息系统的内容。借助 Adobe Campaign，您可以整合营销历史、购买信息、偏好、CRM 数据，以及整合视图中任何相关的 PII 数据，从而进行分析并采取行动。

在 Adobe　Campaign 中，收件人是发送投放内容（电子邮件、SMS 等）所定位的默认用户档案。凭借数据库中存储的收件人数据，您可以过滤将接收任何给定投放的目标并在投放内容中添加个性化数据。数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

[!DNL :bulb:] 此部分 [中说明了用户档案管](audiences.md)理的基础知识。

[!DNL :bulb:] 在此部分中了解如何将用户档案添 [加到Campaign](import.md)。

## 目标市场细分 {#targeted-segmentation}

Adobe Campaign 具有功能强大且易于使用的市场细分和定位功能，让您可以打造极具针对性的差异化优惠方案。您可以使用描述性分析功能分析营销活动的上游和下游信息，而过滤器管理及图形查询编辑器功能可用于过滤订阅者群体及样本，或根据无数量限制标准设定目标组。

高级数据管理功能可进一步扩充数据处理能力。通过包含未在数据集市中建模的数据，该功能可简化并优化定位流程。

[!DNL :bulb:] 在此部分中了解有关分段、受众创建和个性化的 [更多信息](audiences.md)。

## 跨渠道活动编排 {#cross-channel-campaign-orchestration}

您可以利用 Adobe Campaign 在多个渠道上设计和编排有针对性的个性化活动：电子邮件、直邮、SMS、推送通知等。通过单个界面为您提供计划、编排、配置、个性化、自动化、执行和衡量所有活动和通信所需的全部功能。

[!DNL :bulb:] 在此部分中了解如何设计、计划和执行 [活动](campaigns.md)。

## 工作流

Adobe Campaign提供了一个全面的图形环境，使您能够设计复杂的流程，包括分段、促销活动执行、文件处理等。 例如，您可以使用工作流从服务器下载文件、解压缩，然后将其记录导入Adobe Campaign数据库。

工作流也可能涉及到用户，方法是为他们分配任务或让他们批准执行的任务。 这意味着您可以为一个或多个用户分配任务以处理内容或指定目标，并在发送消息之前批准校样。

工作流可以在不同的上下文中使用，例如：

* 定位以管理受众或发送消息。
* 数据管理(ETL)来处理数据。
* 将数据导入Campaign数据库。
* 技术过程，如数据库清理、恢复跟踪信息等。

[!DNL :bulb:] 在此部分中了解如何设计和执行 [工作流](../config/workflows.md)。

## 报告与分析{#analysis-and-reporting}

Adobe Campaign 可逐步丰富客户数据和用户档案，从而让您监控和解读客户的行为。利用报告和分析工具，您可以充分利用每一个新活动、更有效地确定营销方案的目标，且最大限度提高活动的影响力及投资回报。

[!DNL :bulb:] 在此部分中了解有关报告和跟踪功 [能的更多信息](reporting.md)。

## Adobe Experience Cloud 集成 {#adobe-experience-cloud-integrations}

您可以将 Adobe Campaign 的投放功能以及高级活动管理功能与帮助您个性化用户体验的解决方案（例如　Adobe Experience Manager、Adobe Analytics、Adobe Target 或 Adobe Experience Cloud 触发程序）结合起来。

[!DNL :bulb:] 在此部分中了解如何与Adobe服务和解决方 [案集成](../connect/integration.md)。

## 有关Campaign功能的更多信息{#core-capabilities-and-add-ons}

Adobe Campaign提供一系列功能，帮助您根据您的需求和架构实施和优化各种对话式营销功能。 其中有些是核心功能，有些功能取决于您在配置上安装软件包的情况。 此处提供了详细的产品描述：[Adobe Campaign v8产品说明](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-classic---product-description.html)。

[!DNL :bulb:] 已经熟悉Campaign Classic?了解[本页](capability-matrix.md)中Campaign Classic与Campaign v8之间的主要区别。

## 工作区和自定义

可通过[客户端控制台](../dev/general-architecture.md)使用Campaign工作区。

[!DNL :bulb:] [进一步了解Campaign客户端控制台](../start/connect.md)。

Campaign工作区可以根据您的需求进行调整。

[!DNL :arrow_upper_right:]  在Campaign v7文档中了解如 [何使用Campaign工作区](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)

[!DNL :arrow_upper_right:]  了解如何在 [Campaign Classicv7文档中自定义列表](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)

您还可以通过Web访问某些功能。

[!DNL :bulb:] [进一步了解Campaign Web Access](../start/connect.md#web-access)。


## 语言

Campaign v8用户界面提供以下语言版本：

* 英语（英国）
* 美式英语
* 法语
* 德语
* 日语

在安装过程中会选择语言。

>[!CAUTION]
>
>创建实例后，无法更改语言。

语言影响的日期和时间格式。 有关更多信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time)。

