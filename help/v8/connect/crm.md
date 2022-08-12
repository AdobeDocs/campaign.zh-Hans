---
title: 使用Campaign和您的CRM
description: 了解如何使用Campaign和CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: ce2509e5755d83c5408265b490220ae2a662314e
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 20%

---

# 将CRM与Campaign连接 {#gs-crm}

Adobe Campaign 提供各种 CRM 连接器，可将您的 Adobe Campaign 平台链接到第三方系统。通过这些 CRM 连接器，您可以同步处理联系人、帐户、购买等。您可以使用这些 CRM 连接器轻松地将您的应用程序与各第三方和商务应用程序相集成。

这些连接器支持快速、轻松的数据集成：Adobe Campaign为从CRM中可用的表中进行收集和选择提供了专门的助手。 并且可确保双向同步处理，让整个系统中的数据随时保持最新。

主要优势包括：

* 销售和营销之间的一致报文传送：Adobe Campaign与您的CRM集成，使系统既可以访问客户洞察，又可以访问电子邮件营销历史，从而允许所有发送给客户的消息共享相同的一致消息。

* 所有潜在客户和客户数据的全面视图：通过将Adobe Campaign与您的CRM集成，可以从CRM系统内共享和访问每个联系人的电子邮件营销历史记录。

* 在任何渠道上激活CRM数据：联系人数据同步到Adobe Campaign后，可通过Campaign的任何在线或离线渠道（包括移动推送、应用程序内、电子邮件或直邮）发送通信。


>[!NOTE]
>
>此功能在Adobe Campaign中通过 **CRM连接器** 专用包。

## 兼容系统 {#compatible-crm-systems-and-limitations}

Campaign中详细介绍了支持的CRM和版本 [兼容性矩阵](../start/compatibility-matrix.md).

>[!CAUTION]
>
> Campaign CRM连接器只能与安全URL(https)一起使用。

## 实施步骤 {#crm-implementation-steps}

了解在中连接Campaign和Microsoft Dynamics的分步过程 [本页](ac-ms-dyn.md).

了解在 [本页](ac-sfdc.md).

Adobe Campaign与CRM之间的数据同步是通过专用的工作流活动执行的。 构建工作流以在Campaign和CRM之间自动同步。 您可以创建一个工作流，该工作流将通过Microsoft Dynamics导入联系人，将其与现有Adobe Campaign数据同步，删除重复的联系人，然后更新Adobe Campaign数据库。 请参阅[此页面](crm-data-sync.md)以了解详情。
