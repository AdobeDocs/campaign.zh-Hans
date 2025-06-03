---
title: 使用Campaign和您的CRM
description: 了解如何使用Campaign和您的CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 20%

---

# 将您的CRM连接到Campaign {#gs-crm}

Adobe Campaign 提供各种 CRM 连接器，可将您的 Adobe Campaign 平台链接到第三方系统。通过这些 CRM 连接器，您可以同步处理联系人、帐户、购买等。您可以使用这些 CRM 连接器轻松地将您的应用程序与各第三方和商务应用程序相集成。

通过这些连接器，可快速轻松地集成数据：Adobe Campaign提供了一个专用助手，用于从CRM中提供的表中收集和选择数据。 并且可确保双向同步处理，让整个系统中的数据随时保持最新。

主要优势包括：

* 销售与营销之间消息传送的一致性：Adobe Campaign与您的CRM集成，让两个系统均可访问客户insight和电子邮件营销历史记录，从而允许发送给客户的所有消息都共享同一条一致的消息传送。

* 所有潜在客户和客户数据的整体视图：通过将Adobe Campaign与您的CRM集成，可以从CRM系统中共享和访问每个联系人的电子邮件营销历史记录。

* 在任意渠道上激活您的CRM数据：如果联系人数据同步到Adobe Campaign，则可以通过Campaign在任意在线或离线渠道上发送通信，包括移动推送、应用程序内、电子邮件或直邮。


>[!NOTE]
>
>此功能通过&#x200B;**CRM连接器**&#x200B;专用包在Adobe Campaign中可用。

## 兼容系统 {#compatible-crm-systems-and-limitations}

Campaign [兼容性矩阵](../start/compatibility-matrix.md)中详细介绍了支持的CRM和版本。

>[!CAUTION]
>
> Campaign CRM连接器仅适用于安全URL (https)。

## 实施步骤 {#crm-implementation-steps}

在[此页面](ac-ms-dyn.md)中了解连接Campaign和Microsoft Dynamics的分步过程。

在[此页面](ac-sfdc.md)中了解连接Campaign和Salesforce.com的分步过程。

Adobe Campaign和CRM之间的数据同步通过专用工作流活动执行。 构建您的工作流以自动执行Campaign与CRM之间的同步。 您可以创建一个工作流，以通过Microsoft Dynamics导入联系人，将其与现有Adobe Campaign数据同步，删除重复的联系人，然后更新Adobe Campaign数据库。 请参阅[此页面](crm-data-sync.md)以了解详情。
