---
solution: Campaign
product: Adobe Campaign
title: 活动 v8入门
description: 发现关键功能、用户界面和全局指南
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 55%

---

# 开始使用Adobe Campaign{#gs-ac-v8}

Adobe Campaign 提供了跨渠道客户体验设计平台，并为可视化的活动编排、实时互动管理和跨渠道执行提供了环境。

使用活动可以：

* 通过客户的单一可访问视图推动个性化和参与
* 将电子邮件、移动、线上和线下渠道集成到客户旅程中
* 自动投放有意义、及时的消息和优惠

![](assets/ac-capabilities.png)

## 整合的客户档案 {#integrated-customer-profile}

用户档案集中在powerfull cloud数据库中。 有许多可能的机制可获取用户档案并创建此数据库：通过 Web 窗体在线收集、手动或自动导入文本文件、复制公司数据库或其他信息系统的内容。借助 Adobe Campaign，您可以整合营销历史、购买信息、偏好、CRM 数据，以及整合视图中任何相关的 PII 数据，从而进行分析并采取行动。

在 Adobe　Campaign 中，收件人是发送投放内容（电子邮件、SMS 等）所定位的默认用户档案。凭借数据库中存储的收件人数据，您可以过滤将接收任何给定投放的目标并在投放内容中添加个性化数据。数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

：灯泡：用户档案管理基础知识在[本节](audiences.md)中有说明。

：灯泡：了解如何在[本节](import.md)中向活动添加用户档案。

## 目标市场细分 {#targeted-segmentation}

Adobe Campaign 具有功能强大且易于使用的市场细分和定位功能，让您可以打造极具针对性的差异化优惠方案。您可以使用描述性分析功能分析营销活动的上游和下游信息，而过滤器管理及图形查询编辑器功能可用于过滤订阅者群体及样本，或根据无数量限制标准设定目标组。

高级数据管理功能可进一步扩充数据处理能力。通过包含未在数据集市中建模的数据，该功能可简化并优化定位流程。

：灯泡：了解有关[本节](audiences.md)中的分段、受众创建和个性化的更多信息。

## 跨渠道活动编排 {#cross-channel-campaign-orchestration}

您可以利用 Adobe Campaign 在多个渠道上设计和编排有针对性的个性化活动：电子邮件、直邮、SMS、推送通知等。通过单个界面为您提供计划、编排、配置、个性化、自动化、执行和衡量所有活动和通信所需的全部功能。

：灯泡：了解如何在[本节](campaigns.md)中设计、计划和执行活动。

## 工作流

Adobe Campaign优惠一个全面的图形环境，它允许您设计包括细分、活动执行、文件处理等在内的复杂流程。 例如，您可以使用工作流从服务器下载文件，解压缩文件，然后将其记录导入Adobe Campaign数据库。

工作流还可能会涉及用户，方法是为他们分配任务或让他们批准执行的任务。 这意味着，您可以向一个或多个用户分配任务，以处理内容或指定目标，并在发送消息之前批准验证。

工作流可以用于不同的上下文，例如：

* 定位以管理受众或发送消息。
* 数据管理(ETL)来操作数据。
* 将数据导入活动数据库。
* 诸如数据库清理、恢复跟踪信息等技术过程。

：灯泡：了解如何在[本节](../config/workflows.md)中设计和执行工作流。

## 报告和分析{#analysis-and-reporting}

Adobe Campaign 可逐步丰富客户数据和用户档案，从而让您监控和解读客户的行为。利用报告和分析工具，您可以充分利用每一个新活动、更有效地确定营销方案的目标，且最大限度提高活动的影响力及投资回报。

：灯泡： 了解有关[本节](reporting.md)中报告和跟踪功能的更多信息。

## Adobe Experience Cloud 集成 {#adobe-experience-cloud-integrations}

您可以将 Adobe Campaign 的投放功能以及高级活动管理功能与帮助您个性化用户体验的解决方案（例如　Adobe Experience Manager、Adobe Analytics、Adobe Target 或 Adobe Experience Cloud 触发程序）结合起来。此外，您也可以使用 Adobe ID 集成到 Adobe IMS 并登录 Campaign。

：灯泡：了解如何与[本节](../connect/integration.md)中的Adobe服务和解决方案集成。

## 关于活动功能{#core-capabilities-and-add-ons}的更多信息

根据您的需求和架构，Adobe Campaign 提供了一系列功能，帮助您实施和优化各种对话式营销功能。其中有些是核心功能，有些功能取决于软件包的安装和您的配置。产品说明详细信息请访问：[Adobe Campaignv8产品说明](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-classic---product-description.html)。

：灯泡：已经熟悉Campaign Classic? 了解[本页](capability-matrix.md)中Campaign Classic和活动 v8之间的主要差异。

## 工作区和自定义

活动工作区可通过客户端控制台使用。

：灯泡： 了解如何在[本节](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)中使用活动工作区

：灯泡： 了解如何在[此部分](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)中自定义列表

您还可以通过Web访问某些功能。

