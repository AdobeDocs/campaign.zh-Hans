---
title: 受众入门
description: 受众入门
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 889400a238f32968464f1425bb7d6c2dc3ff3cd0
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 26%

---

# 受众快速入门{#gs-ac-audiences}

## 使用用户档案{#gs-ac-profiles}

用户档案是存储在Campaign数据库中的联系人，包括客户、订阅者和潜在客户。 有许多可能的机制可获取用户档案并创建此数据库：通过 Web 窗体在线收集、手动或自动导入文本文件、复制公司数据库或其他信息系统的内容。借助Adobe Campaign，您可以整合营销历史、购买信息、偏好、CRM数据以及整合视图中任何相关的PI数据，以便进行分析并采取行动。 用户档案包含定位、鉴别和跟踪个人所需的所有信息。

用户档案是 **nmsRecipient** 表或外部表，用于存储所有配置文件属性，如名字、姓氏、电子邮件地址、Cookie ID、客户ID、移动标识符或与特定渠道相关的其他信息。 链接到收件人表的其他表包含与用户档案相关的数据，例如投放日志表，其中包含发送给收件人的所有投放记录。 了解有关 [此部分](../dev/datamodel.md#ootb-profiles).

在Adobe Campaign, **收件人** 是发送投放（电子邮件、短信等）的默认定向用户档案。 通过数据库中存储的收件人数据，您可以筛选将接收任何给定投放的目标，并在投放内容中添加个性化数据。 数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

用户档案可以分组到列表中，也可以通过查询数据库来收集。

要使用用户档案数据填充Campaign，您可以：

* [导入数据文件](import.md) 从外部数据源（如CRM系统）
* [创建web窗体](../dev/webapps.md) 允许客户输入自己的信息并创建自己的用户档案
* [映射到外部数据库](../connect/fda.md) 存储用户档案的位置
* 使用Client Console手动输入用户档案，如下所示：

![](assets/create-profile.png)

![](../assets/do-not-localize/book.png) 了解如何在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html){target=&quot;_blank&quot;}。


## 隐私和同意

Adobe Campaign是用于收集和处理大量数据（包括个人信息和敏感数据）的强大工具。 通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并监控收件人的同意至关重要。

![](../assets/do-not-localize/book.png) 了解如何在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target=&quot;_blank&quot;}。

## 创建列表

列表是一组静态用户档案，用于在投放操作期间提供定位目标，或在导入操作或工作流执行期间进行更新。例如，通过查询从数据库中提取出的一组数据即可形成一个列表。

![](../assets/do-not-localize/book.png) 了解如何在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html){target=&quot;_blank&quot;}。

## 查询数据库

使用 **查询** 活动，用于查询数据库、细分数据和构建复杂受众。

![](../assets/do-not-localize/book.png) 详细了解 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html){target=&quot;_blank&quot;}。

![](../assets/do-not-localize/book.png) 所有定位活动均列在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target=&quot;_blank&quot;}。

## 在工作流中创建受众

定位可以通过工作流中图形序列中的查询组合来创建。 您可以创建受众，以便根据您的要求进行定位。 要显示工作流编辑器，请单击 **[!UICONTROL Targeting and workflows]** 选项卡。

![](../assets/do-not-localize/book.png) 了解如何在的营销活动工作流中构建受众 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}。


## 使用中的用户档案{#active-profiles}

根据您的合同，您的每个 Campaign 实例都会配置特定数量的活动用户档案，并对这些活动用户档案进行计数以计费。请参阅您的最新合同，了解已购买的活动用户档案数量。

**用户档案** 指信息记录(例如：记录 [收件人表](../dev/datamodel.md) 或包含Cookie ID、客户ID、移动标识符或与特定渠道相关的其他信息的外部表)，表示最终客户、潜在客户。 如果用户档案在过去12个月内通过任何渠道被定向或传达，则会将其视为活动用户档案。

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->


**Campaign Classic v7 文档**&#x200B;中的相关主题：

* [设计和执行特定于营销活动的工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target=&quot;_blank&quot;}

* [了解如何选择营销活动的受众](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target=&quot;_blank&quot;}

* [工作流入门](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target=&quot;_blank&quot;}
