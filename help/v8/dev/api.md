---
title: Campaign API 快速入门
description: Campaign API 快速入门
feature: API
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 4c2d3bba282f629a9f5cadcda9ab79a810ac9832
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 8%

---

# 开始使用 [!DNL Campaign] API {#gs-ac-api}

[!DNL Adobe Campaign] 随附了一组Javascript函数，您可以使用这些函数：

* 在脚本中 — 在 [!DNL Adobe Campaign] 工作流
* 通过API — 来自外部系统

您可以使用JavaScript API在Campaign云数据库中写入或读取数据库：

* 特定于业务的API，允许您对每个对象执行操作：投放、工作流、订阅等。 了解详情，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* 用于查询数据模型数据的通用数据访问API。 了解详情，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

请注意，在其 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，Campaign可与两个数据库配合使用：用于用户界面实时消息传递和统一查询、通过API写入的本地数据库，以及用于活动执行、报告、数据摄取、批量查询和工作流执行的云数据库。

>[!CAUTION]
>
>* 从Campaign v8.5.1开始，更改了Campaign v8的身份验证过程。 技术操作员必须使用AdobeIdentity Management System (IMS)连接到Campaign。 了解如何在中迁移现有技术帐户 [此技术说明](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8对API层的吞吐量(TPS)进行了限制。 超出此限制会导致标准HTTP错误(429)。 作为托管Cloud Service用户，您可以联系Adobe以调整每个API的限制。
> 

## 先决条件 {#ac-api-prerequisites}

使用前 [!DNL Adobe Campaign] API方面，您需要熟悉以下主题：

* JavaScript
* SOAP协议
* [!DNL Adobe Campaign] 数据模型

要使用API并与之交互 [!DNL Adobe Campaign]此外，您还必须熟悉您的数据模型。

>[!NOTE]
>您可以生成数据模型的完整说明。 请参阅[此页面](datamodel.md)以了解详情。


**相关主题**

* [数据模型最佳实践](datamodel-best-practices.md)
