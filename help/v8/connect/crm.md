---
solution: Campaign
product: Adobe Campaign
title: 使用活动和您的CRM
description: '了解如何使用活动和您的CRM '
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 21%

---

# 使用活动 {#gs-crm}连接CRM

Adobe Campaign 提供各种 CRM 连接器，可将您的 Adobe Campaign 平台链接到第三方系统。通过这些 CRM 连接器，您可以同步处理联系人、帐户、购买等。您可以使用这些 CRM 连接器轻松地将您的应用程序与各第三方和商务应用程序相集成。

这些连接器支持快速、轻松的数据集成：Adobe Campaign为从CRM中提供的表中收集和选择内容提供专用助理。 并且可确保双向同步处理，让整个系统中的数据随时保持最新。

>[!NOTE]
>
>此功能可通过&#x200B;**CRM connectors**&#x200B;专用包以Adobe Campaign形式提供。

## 兼容系统{#compatible-crm-systems-and-limitations}

支持的CRM和版本详见活动 [兼容性矩阵](../start/compatibility-matrix.md)。

**注意** - CRM连接器仅使用安全URL(https)。

## 实施步骤 {#crm-implementation-steps}

:arrow_upper_right:了解在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)中连接活动和Microsoft Dynamics的分步过程

:arrow_upper_right:了解在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)中连接活动和Salesforce的分步过程


Adobe Campaign与CRM之间的数据同步是通过专用工作流活动执行的。 构建工作流，以在活动和CRM之间实现自动同步。 您可以创建一个工作流，该工作流通过Microsoft Dynamics导入联系人，将其与现有Adobe Campaign数据同步，删除重复联系人，然后更新Adobe Campaign数据库。

:arrow_upper_right:了解有关[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)的更多信息

