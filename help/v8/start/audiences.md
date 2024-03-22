---
title: 在Campaign中使用受众
description: 在Campaign中使用受众
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 15%

---

# 在Campaign中使用受众{#gs-ac-audiences}

用户档案是存储在Campaign数据库中的联系人。

在Adobe Campaign中， **收件人** 是发送投放（电子邮件、短信等）所定位的默认用户档案。 通过存储在数据库中的收件人数据，您可以筛选将接收任何给定投放的目标，并在投放内容中添加个性化数据。 数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

了解如何导入、更新和管理用户档案和受众 [在此部分中](../audiences/gs-audiences.md).

## 创建列表{#create-lists}

列表是一组静态的联系人，在投放操作中可以定位这些联系人，或在导入或其他工作流操作期间对其进行更新。 例如，通过查询从数据库中提取的群体可以存储为列表。

了解如何在中创建和管理列表 [此页面](../audiences/create-audiences.md).

## 筛选数据库{#filter-the-database}

筛选器配置允许您从列表中选择数据 **[!UICONTROL dynamically]**：修改数据时，将更新过滤的数据。 您可以创建自己的过滤器，也可以使用内置的过滤器来定义目标受众。

了解如何在中创建和管理过滤器 [此页面](../audiences/create-filters.md).

## 在工作流中创建受众

定位可以通过工作流中以图形顺序显示的查询组合来创建。 您可以创建根据要求定向的受众。 要显示工作流编辑器，请单击 **[!UICONTROL Targeting and workflows]** 选项卡。

了解如何在的营销活动工作流中构建受众 [此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"}.


## 使用中的用户档案 {#active-profiles}

活动用户档案是客户在过去12个月内尝试通过任何渠道与之通信的用户档案。 许可证量度基于活动用户档案。 了解详情，请参阅 [Adobe Campaign产品描述](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

您可以直接从Campaign控制面板监控实例上的活动用户档案数。 有关详细信息，请参见 [控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}.

>[!CAUTION]
>
>* 被多次投放定向的用户档案只会被计数一次。
>
>* 在X(Twitter)的社交营销上下文中定位的用户档案不会计为活动用户档案。

## 隐私和同意{#privacy-and-consent}

Adobe Campaign是一款用于收集和处理大量数据（包括个人信息和敏感数据）的强大工具。 通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并监控收件人的同意至关重要。

了解如何在中管理隐私和同意 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hans){target="_blank"}.

**相关主题**

* [设计和执行特定于营销活动的工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html){target="_blank"}

* [了解如何选择营销活动的受众](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"}

* [工作流入门](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}
