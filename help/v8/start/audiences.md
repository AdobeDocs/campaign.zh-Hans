---
title: 在Campaign中使用受众
description: 在Campaign中使用受众
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 99cb937a475997aae714a67b1f9f91c6bae932f4
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 17%

---

# 在Campaign中使用受众{#gs-ac-audiences}

用户档案是存储在Campaign数据库中的联系人。

在Adobe Campaign中，**收件人**&#x200B;是发送投放内容（电子邮件、短信等）所定位的默认用户档案。 通过存储在数据库中的收件人数据，您可以筛选将接收任何给定投放的目标，并在投放内容中添加个性化数据。 数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

在本节](../audiences/gs-audiences.md)中了解如何导入、更新和管理用户档案和受众[。

## 创建列表{#create-lists}

列表是一组静态的联系人，在投放操作中可以定位这些联系人，或在导入或其他工作流操作期间对其进行更新。 例如，通过查询从数据库中提取的群体可以存储为列表。

在[此页面](../audiences/create-audiences.md)中了解如何创建和管理列表。

## 筛选数据库{#filter-the-database}

筛选器配置允许您从列表&#x200B;**[!UICONTROL dynamically]**&#x200B;中选择数据：修改数据时，将更新过滤的数据。 您可以创建自己的过滤器，也可以使用内置的过滤器来定义目标受众。

了解如何在[此页面](../audiences/create-filters.md)中创建和管理筛选器。

## 在工作流中创建受众

定位可以通过工作流中以图形顺序显示的查询组合来创建。 您可以创建根据要求定向的受众。 要显示工作流编辑器，请单击营销活动仪表板中的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;选项卡。

在[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"}中了解如何在营销活动工作流中构建受众。


## 使用中的用户档案 {#active-profiles}


活动用户档案是客户在过去12个月内尝试通过任何渠道与之通信的用户档案。

根据您的合同，您的每个 Campaign 实例都会配置特定数量的活动用户档案，并对这些活动用户档案进行计数以计费。请参阅您的最新合同，了解已购买的活动用户档案的数量。 在[Adobe Campaign产品描述](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}中了解详情。

您可以直接从Campaign控制面板监控实例上的活动用户档案数。 有关详细信息，请参阅[控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}。


以下护栏和限制适用：

* 被多次投放定向的用户档案只会被计数一次。
* 在X(Twitter)的社交营销上下文中定位的用户档案不会计为活动用户档案。
* 计数基于收件人主键。 因此，如果某个用户档案存在于两个不同的收件人表中，则它可能会被计算为活动用户档案两次。


## 隐私和同意{#privacy-and-consent}

Adobe Campaign是一款用于收集和处理大量数据（包括个人信息和敏感数据）的强大工具。 通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并监控收件人的同意至关重要。

请参阅[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hans){target="_blank"}以了解如何管理隐私和同意。

**相关主题**

* [设计和执行特定于营销活动的工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html){target="_blank"}

* [了解如何选择营销活动的受众](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"}

* [开始使用工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}
