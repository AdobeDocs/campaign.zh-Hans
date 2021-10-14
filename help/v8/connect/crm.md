---
title: 使用Campaign和您的CRM
description: 了解如何使用Campaign和CRM
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 25%

---

# 将CRM与Campaign连接 {#gs-crm}

Adobe Campaign 提供各种 CRM 连接器，可将您的 Adobe Campaign 平台链接到第三方系统。通过这些 CRM 连接器，您可以同步处理联系人、帐户、购买等。您可以使用这些 CRM 连接器轻松地将您的应用程序与各第三方和商务应用程序相集成。

这些连接器支持快速、轻松的数据集成：Adobe Campaign为从CRM中可用的表中进行收集和选择提供了专门的助手。 并且可确保双向同步处理，让整个系统中的数据随时保持最新。

>[!NOTE]
>
>此功能可通过&#x200B;**CRM连接器**&#x200B;专用包在Adobe Campaign中提供。

## 兼容系统 {#compatible-crm-systems-and-limitations}

Campaign [兼容性矩阵](../start/compatibility-matrix.md)中详细介绍了支持的CRM和版本。

![](../assets/do-not-localize/speech.png)  CRM连接器只能与安全URL(https)一起使用。

## 实施步骤 {#crm-implementation-steps}

![](../assets/do-not-localize/book.png) 了解在Microsoft v7文档中连接Campaign和Campaign Classic Dynamics的分 [步过程](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

![](../assets/do-not-localize/book.png) 了解Campaign Classicv7文档中连接Campaign和Salesforce的分 [步过程](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


Adobe Campaign与CRM之间的数据同步是通过专用的工作流活动执行的。 构建工作流以在Campaign和CRM之间自动同步。 您可以创建一个工作流，该工作流将通过Microsoft Dynamics导入联系人，将其与现有Adobe Campaign数据同步，删除重复的联系人，然后更新Adobe Campaign数据库。

![](../assets/do-not-localize/book.png) 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)以了解详情
