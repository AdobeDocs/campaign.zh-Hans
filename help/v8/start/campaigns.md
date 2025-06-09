---
title: 营销活动入门
description: 营销活动入门
feature: Cross Channel Orchestration
role: User
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66
source-git-commit: 8d6c3e03f9b7533f7f325b755e3b6d4f74b63a8d
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 93%

---

# 营销活动入门 {#gs-ac-campaigns}

Adobe Campaign 提供了一套解决方案，可帮助您在所有线上和线下渠道个性化和交付活动。 您可以创建、配置、执行和分析营销活动。 所有营销活动都可从统一的控制中心进行管理。在此部分了解如何浏览和创建营销活动。

活动包括操作（投放）和流程（导入或提取文件）以及资源（营销文档、投放概要）。 它们用于营销活动。活动是项目的一部分，项目包含在活动计划中。

## 跨渠道营销活动编排{#cross-channel-orchestration}

您可以利用 Adobe Campaign 在多个渠道上设计和编排有针对性的个性化活动：电子邮件、直邮、SMS、推送通知等。通过单个界面为您提供计划、编排、配置、个性化、自动化、执行和衡量所有活动和通信所需的全部功能。

![](assets/campaign-tab.png)

### 核心概念{#ac-core-concepts}

在开始实施营销活动之前，您需要熟悉以下概念：

* **营销活动**：活动集中了与营销活动相关的所有元素：投放、定位规则、成本、导出文件、相关文档等。每个活动都附属于项目。

* **项目**：项目允许您定义日历期间的营销行动：发布、调查意见、忠诚度等。每个项目都包含链接到日历的活动，日历提供了概览。

* **计划**：营销计划可包含多个项目。它链接到日历期间，有分配的预算，也可以链接到文档和目标。

* **活动工作流**：活动工作流包含用于构建活动逻辑的活动。使用活动工作流定义受众并为所有可用渠道创建投放。

* **周期性活动**：周期性活动是从定义要执行的工作流程模板和执行计划的特定模板创建的。

* **定期活动**：定期活动是根据模板的执行计划自动创建的活动。

## 营销活动工作区{#ac-workspace}

Adobe Campaign 允许您从一个统一的控制中心创建、配置、执行和分析所有营销活动。

![](assets/calendar.png)

在[此部分](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=zh-Hans){target="_blank"}中了解如何访问和实施营销活动。

## 开始的关键步骤{#gs-ac-start}

创建跨渠道营销活动的关键步骤有：

1. **规划和设计营销项目和活动**

   定义层次结构和计划、设置预算、添加资源、选择运算符。

   在[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-create.html?lang=zh-Hans){target="_blank"}中了解如何创建营销计划并配置营销活动。

   所有营销活动均基于存储主要设置和功能的模板。提供了内置模板以用于创建尚未定义特定配置的活动。您可以创建和配置活动模板，然后从这些模板创建活动。

   请参阅[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=zh-Hans){target="_blank"}以了解如何使用营销活动模板。

   请参阅[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=zh-Hans){target="_blank"}以了解周期性营销活动以及其配置方法。

1. **定义受众**

   您可以在工作流程中构建受众或选择现有群组，如收件人列表、新闻稿订阅者、以前投放的收件人或任何筛选条件。

   ![](assets/campaign-wf.png)

   请参阅[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"}以了解如何定义消息的受众。

1. **创建投放**

   选择渠道、定义消息内容并开始投放。

   ![](assets/campaign-dashboard.png)

   要了解如何创建和开始营销活动投放，请参阅[此页面](../../automation/campaigns/marketing-campaign-deliveries.md)。

   您可以将如报告、照片、网页、图表等各种文档与营销活动关联起来。要了解关联文档的更多信息，请参阅[此页面](../../automation/campaigns/marketing-campaign-assets.md)。

1. **设置审批流程**

   Adobe Campaign 允许您为营销活动的主要阶段设置协作审批流程。对于每个活动，您可以批准投放目标、内容和成本。负责审批工作的 Adobe Campaign 操作员收到电子邮件通知后，可通过控制台或 Web 连接批准或拒绝批准相关请求。

   请参阅[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=zh-Hans#campaign-orchestration){target="_blank"}以了解如何设置和管理审批。


## 分布式营销附加功能{#distributed-marketing-add-on}

Adobe Campaign 提供&#x200B;**分布式营销**&#x200B;附加功能，用于在中央实体（总部、营销部门等）和本地实体（商店、区域代理等）之间实施合作营销活动。此合作基于称为 **[!UICONTROL List of campaign packages]** 的共享工作区，在其中，中央实体可以将其设计的营销活动模板提供给本地实体。

>[!NOTE]
>
>从 Campaign v8.3 开始提供此功能。要检查您的版本，请参阅[此部分](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

了解如何在[此页面](https://experienceleague.adobe.com/docs/campaign/automation/distributed-marketing/about-distributed-marketing.html?lang=zh-Hans){target="_blank"}中配置和使用Campaign分布式营销功能。

## 响应管理附加功能{#response-manager-add-on}

Adobe Campaign 提供&#x200B;**响应管理**&#x200B;附加功能，可让您衡量营销活动的成功性和盈利能力，还可提供跨通信渠道（电子邮件、移动设备、直邮等）的产品建议提议。

>[!NOTE]
>
>从 Campaign v8.3 开始提供此功能。要检查您的版本，请参阅[此部分](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

[](../assets/do-not-localize/book.png)请参阅[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/response-manager/about-response-manager.html?lang=zh-Hans){target="_blank"}以了解如何配置并使用Campaign响应管理器。
