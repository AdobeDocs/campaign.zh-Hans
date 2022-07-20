---
title: 在Campaign中使用受众
description: 在Campaign中使用受众
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 18%

---

# 在Campaign中使用受众{#gs-ac-audiences}

用户档案是存储在Campaign数据库中的联系人。

在Adobe Campaign, **收件人** 是发送投放（电子邮件、短信等）的默认定向用户档案。 通过数据库中存储的收件人数据，您可以筛选将接收任何给定投放的目标，并在投放内容中添加个性化数据。 数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

了解如何导入、更新和管理用户档案和受众 [在此部分中](../audiences/gs-audiences.md).

## 创建列表{#create-lists}

列表是一组静态联系人，可在投放操作中定位，或在导入或其他工作流操作期间更新。 例如，通过查询从数据库中提取的群体可以存储为列表。

![](../assets/do-not-localize/glass.png) 了解如何在 [本页](../audiences/create-audiences.md).

## 过滤数据库{#filter-the-database}

过滤器配置允许您从列表中选择数据 **[!UICONTROL dynamically]**:修改数据时，会更新过滤的数据。 您可以创建自己的过滤器，也可以使用内置过滤器来定义目标受众。

![](../assets/do-not-localize/glass.png) 了解如何在 [本页](../audiences/create-filters.md).

## 在工作流中创建受众

定位可以通过工作流中图形序列中的查询组合来创建。 您可以创建受众，以便根据您的要求进行定位。 要显示工作流编辑器，请单击 **[!UICONTROL Targeting and workflows]** 选项卡。

了解如何在的营销活动工作流中构建受众 [本页](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)


## 使用中的用户档案{#active-profiles}

根据您的合同，您的每个Campaign实例都会配置特定数量的活动用户档案，这些活动用户档案会被计为计费用。 请参阅您的最新合同，了解已购买的活动用户档案数量。

**用户档案** 指信息记录(例如：记录 [收件人表](../dev/datamodel.md) 或包含Cookie ID、客户ID、移动标识符或与特定渠道相关的其他信息的外部表)，表示最终客户、潜在客户。 如果用户档案在过去12个月内通过任何渠道被定向或传达，则会将其视为活动用户档案。

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

## 隐私和同意{#privacy-and-consent}

Adobe Campaign是用于收集和处理大量数据（包括个人信息和敏感数据）的强大工具。 通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并监控收件人的同意至关重要。

![](../assets/do-not-localize/book.png) 了解如何在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hans){target=&quot;_blank&quot;}。

**相关主题**

* [设计和执行特定于营销活动的工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html)

* [了解如何选择营销活动的受众](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)

* [工作流入门](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)
