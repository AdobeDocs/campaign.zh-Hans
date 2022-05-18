---
title: Campaign API 快速入门
description: Campaign API 快速入门
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 15%

---

# 入门 [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] 附带一组Javascript函数，您可以使用：

* 在脚本中 — 在 [!DNL Adobe Campaign] 工作流
* 通过API — 从外部系统

您可以使用JavaScript API在Campaign云数据库中写入内容或从数据库读取内容：

* 允许您对每个对象执行操作的特定于业务的API:投放、工作流、订阅等。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html)以了解详情。
* 用于查询数据模型数据的通用数据访问API。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html)以了解详情。

Campaign v8可与两个数据库配合使用：用于用户界面实时消息传送和统一查询并通过API写入的本地数据库，以及用于促销活动执行、报告、数据获取、批量查询和工作流执行的云数据库。

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8对API层的吞吐量(TPS)存在限制。 超出限制会导致标准HTTP错误(429)。 作为受管Cloud Services用户，您可以联系Adobe以调整每个API的限制。

## 先决条件

使用之前 [!DNL Adobe Campaign] API，您需要熟悉以下主题：

* JavaScript
* SOAP协议
* [!DNL Adobe Campaign] 数据模型

以便使用API并与交互 [!DNL Adobe Campaign]，则还必须熟悉您的数据模型。

>[!NOTE]
>您可以生成数据模型的完整说明。 请参阅[此页面](datamodel.md)以了解详情。


**相关主题**

* [数据模型最佳实践](datamodel-best-practices.md)
