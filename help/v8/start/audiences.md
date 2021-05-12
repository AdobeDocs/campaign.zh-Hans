---
solution: Campaign
product: Adobe Campaign
title: 开始使用受众
description: 开始使用受众
feature: 受众
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
translation-type: tm+mt
source-git-commit: 3870395ec74dd51ed42944981a3851d1052ee255
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 30%

---

# 开始使用受众{#gs-ac-audiences}

用户档案可以按列表分组，或通过查询数据库来收集。

## 使用用户档案{#gs-ac-profiles}

用户档案集中在云数据库中。 有许多可能的机制可获取用户档案并创建此数据库：通过 Web 窗体在线收集、手动或自动导入文本文件、复制公司数据库或其他信息系统的内容。借助Adobe Campaign，您可以将营销历史、购买信息、偏好、CRM数据和任何相关PI数据合并到一个整合视图中，以便进行分析和采取行动。

“**用户档案**”指代表客户、潜在客户、新闻稿订阅者等的信息记录。
**nmsRecipient**&#x200B;表或外部表中的记录包含Cookie ID、客户ID、移动标识符或与特定渠道相关的其他信息。 了解有关[本节](../dev/datamodel.md#ootb-profiles)中内置用户档案和收件人表的更多信息。

在 Adobe　Campaign 中，收件人是发送投放内容（电子邮件、SMS 等）所定位的默认用户档案。收件人数据存储在目标库中，使您能够过滤将接收任何给定投放的投放，并在内容中添加个性化数据。 数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

:arrow_forward:[了解视频中的用户档案](https://video.tv.adobe.com/v/35611?quality=12)

:arrow_upper_right:了解如何在[本指南](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html)中管理用户档案。

## 隐私和同意

Adobe Campaign 是一款用于收集和处理超大量数据（包括个人信息和敏感数据）的强大工具。通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并监控收件人的同意至关重要。

:arrow_upper_right:请阅读本指南](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html)，了解如何管理隐私和同意。[


## 创建列表

列表是一组静态用户档案，用于在投放操作期间提供定位目标，或在导入操作或工作流执行期间进行更新。例如，通过查询从数据库中提取出的一组数据即可形成一个列表。

:arrow_upper_right:了解如何在[此部分](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html)中创建和管理列表。

## 查询数据库

在工作流中使用&#x200B;**查询**&#x200B;活动查询数据库、细分数据和构建复杂受众。

:arrow_upper_right:了解有关[本指南](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html)中的活动查询的更多信息。

:arrow_upper_right:所有定位活动列在[此页](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)中

## 在工作流中创建受众

可以通过工作流中图形序列中的查询组合创建定位。 您可以根据自己的需求创建目标受众。 要显示工作流编辑器，请单击“活动”仪表板中的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;选项卡。

:arrow_upper_right:了解如何在[此页面]https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow中的活动工作流中构建受众)


## 使用中的用户档案{#active-profiles}

根据您的合同，您的每个 Campaign 实例都会配置特定数量的活动用户档案，并对这些活动用户档案进行计数以计费。请参阅您的最新合同，了解已购买的活动用户档案数量。

“用户档案”指信息记录(例如：[收件人表](../dev/datamodel.md)中的记录，或包含表示最终客户、潜在客户或潜在客户的cookie ID、客户ID、移动标识符或与特定渠道相关的其他信息的外部表。 如用户档案在过去12个月内通过任何渠道被定向或传达，则视其为活跃。

您可以直接从活动用户档案监视实例上使用的活动控制面板数。

:arrow_upper_right:有关详细信息，请参阅[控制面板文档](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。


**相关主题**

:arrow_upper_right:[设计和执行活动特定的工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:arrow_upper_right:[了解如何选择活动的受众](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:arrow_upper_right:[开始使用工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
