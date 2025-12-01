---
title: Campaign API入门
description: Campaign API入门
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 26fededf0ee83299477e45e891df30a46c6d40fe
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 11%

---

# 开始使用[!DNL Campaign] API {#gs-ac-api}

[!DNL Adobe Campaign]附带了一组Javascript函数，您可以使用这些函数：

* 在脚本中 — 在[!DNL Adobe Campaign]工作流中
* 通过API — 来自外部系统

>[!NOTE]
>
>根据您的部署模型，您还可以将REST API与Campaign v8结合使用。 [了解详情](../dev/api/get-started-apis.md)。

您可以使用[Campaign JavaScript API](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}在Campaign云数据库中写入或从数据库中读取：

* 特定于业务的API，允许您对每个对象执行操作：投放、工作流、订阅等。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}以了解详情。
* 用于使用queryDef和NLWS方法查询数据模型数据的通用数据访问API。 在[使用queryDef](query-api.md)查询数据库中了解更多信息。

请注意，在其[企业(FFDA)部署](../architecture/enterprise-deployment.md)中，Campaign可与两个数据库配合使用：用于用户界面实时消息传递和统一查询、通过API写入的本地数据库，以及用于活动执行、报告、数据摄取、批量查询和工作流执行的云数据库。

>[!CAUTION]
>
>* 从Campaign v8.5.1开始，更改了Campaign v8的身份验证过程。 技术操作员必须使用Adobe Identity Management System (IMS)连接到Campaign。 请阅读[此技术说明](../../technotes/upgrades/ims-migration.md)，了解如何迁移现有技术帐户。
>
>* [!DNL Adobe Campaign] v8对API层的吞吐量(TPS)存在限制。 超出此限制会导致标准HTTP错误(429)。 作为托管云服务用户，您可以联系Adobe以调整每个API的限制。
> 

## 先决条件 {#ac-api-prerequisites}

在使用[!DNL Adobe Campaign] API之前，您需要熟悉以下主题：

* JavaScript
* SOAP协议
* [!DNL Adobe Campaign]数据模型

要使用API并与[!DNL Adobe Campaign]交互，您还必须熟悉您的数据模型。

>[!NOTE]
>您可以生成数据模型的完整说明。 请参阅[此页面](datamodel.md)以了解详情。


**相关主题**

* [使用queryDef查询数据库](query-api.md)
* [数据模型最佳实践](datamodel-best-practices.md)
* [Campaign JSAPI文档](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
