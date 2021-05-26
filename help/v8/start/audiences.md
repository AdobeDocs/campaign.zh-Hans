---
solution: Campaign v8
product: Adobe Campaign
title: 受众快速入门
description: 受众快速入门
feature: 受众
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 0dae3431ac1ddc840244d7df4929b0c949f8011f
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 24%

---

# 受众入门{#gs-ac-audiences}

## 使用用户档案{#gs-ac-profiles}

用户档案是存储在Campaign数据库中的联系人，包括客户、订阅者和潜在客户。 有许多可能的机制可获取用户档案并创建此数据库：通过 Web 窗体在线收集、手动或自动导入文本文件、复制公司数据库或其他信息系统的内容。借助Adobe Campaign，您可以整合营销历史、购买信息、偏好、CRM数据以及整合视图中任何相关的PI数据，以便进行分析并采取行动。 用户档案包含定位、鉴别和跟踪个人所需的所有信息。

用户档案是&#x200B;**nmsRecipient**&#x200B;表或外部表中的记录，用于存储所有用户档案属性，如名字、姓氏、电子邮件地址、Cookie ID、客户ID、移动标识符或与特定渠道相关的其他信息。 链接到收件人表的其他表包含与用户档案相关的数据，例如投放日志表，其中包含发送给收件人的所有投放记录。 进一步了解[此部分](../dev/datamodel.md#ootb-profiles)中的内置配置文件和收件人表。

在Adobe Campaign中， **收件人**&#x200B;是用于发送投放（电子邮件、短信等）的默认用户档案。 通过数据库中存储的收件人数据，您可以筛选将接收任何给定投放的目标，并在投放内容中添加个性化数据。 数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

用户档案可以分组到列表中，也可以通过查询数据库来收集。


要使用用户档案数据填充Campaign，您可以：

* [从外部](import.md) 数据源（如CRM系统）导入数据文件
* [创建web](../dev/webapps.md) 窗体以允许客户输入自己的信息并创建自己的配置文件
* [映射到外部数据库，](../connect/fda.md) 其中存储了用户档案
* 使用Client Console手动输入用户档案，如下所示：

![](assets/create-profile.png)


[!DNL :[!DNL :arrow_upper_right:]:]了解如何在[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html)中管理配置文件。


## 隐私和同意

Adobe Campaign是用于收集和处理大量数据（包括个人信息和敏感数据）的强大工具。 通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并监控收件人的同意至关重要。

:[!DNL :arrow_upper_right:]:了解如何在[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html)中管理隐私和同意。

## 创建列表

列表是一组静态用户档案，用于在投放操作期间提供定位目标，或在导入操作或工作流执行期间进行更新。例如，通过查询从数据库中提取出的一组数据即可形成一个列表。

:[!DNL :arrow_upper_right:]:了解如何在[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html)中创建和管理列表。

## 查询数据库

使用工作流中的&#x200B;**查询**&#x200B;活动查询数据库、细分数据和构建复杂受众。

:[!DNL :arrow_upper_right:]:在[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html)中了解有关Campaign查询的更多信息。

:[!DNL :arrow_upper_right:]:[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)中列出了所有定位活动

## 在工作流中创建受众

定位可以通过工作流中以图形顺序排列的查询组合来创建。 您可以创建受众，以便根据您的要求进行定位。 要显示工作流编辑器，请单击营销活动仪表板中的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;选项卡。

:[!DNL :arrow_upper_right:]:了解如何在[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)的促销活动工作流中构建受众


## 使用中的用户档案{#active-profiles}

根据您的合同，您的每个 Campaign 实例都会配置特定数量的活动用户档案，并对这些活动用户档案进行计数以计费。请参阅您的最新合同，了解已购买的活动用户档案数量。

**** 用户档案是指信息记录(例如：收件人表或 [外](../dev/datamodel.md) 部表中的记录，其中包含代表最终客户、潜在客户或潜在客户的Cookie ID、客户ID、移动标识符或与特定渠道相关的其他信息。如果用户档案在过去12个月内通过任何渠道被定向或传达，则会将其视为活动用户档案。

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

:[!DNL :arrow_upper_right:]: For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**相关主题**

:[!DNL :arrow_upper_right:]:[设计和执行特定于促销活动的工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:[!DNL :arrow_upper_right:]:[了解如何选择营销活动的受众](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:[!DNL :arrow_upper_right:]: [工作流入门](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
