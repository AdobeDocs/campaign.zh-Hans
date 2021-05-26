---
solution: Campaign v8
product: Adobe Campaign
title: Campaign API 快速入门
description: Campaign API 快速入门
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 4%

---

# [!DNL Campaign] API{#gs-ac-api}快速入门

[!DNL Adobe Campaign] 附带一组Javascript函数，您可以使用：

* 在脚本中 — 在[!DNL Adobe Campaign]工作流中
* 通过API — 从外部系统

您可以使用Javascript API在Campaign云数据库中写入内容或从数据库读取内容：

* 允许您对每个对象执行操作的特定于业务的API:投放、工作流、订阅等。 在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html)中了解更多信息。
* 通用数据访问用于查询数据模型数据的API。 在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html)中了解更多信息。

Campaign v8可与两个数据库配合使用：用于用户界面实时消息传送和统一查询并通过API写入的本地数据库，以及用于促销活动执行、报告、数据获取、批量查询和工作流执行的云数据库。

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8对API层的吞吐量(TPS)存在限制。超出限制会导致标准HTTP错误(429)。 作为受管Cloud Services用户，您可以联系Adobe以调整每个API的限制。


## 先决条件

在使用[!DNL Adobe Campaign] API之前，您需要熟悉以下主题：

* Javascript
* SOAP协议
* [!DNL Adobe Campaign] 数据模型

要使用API并与[!DNL Adobe Campaign]进行交互，您还需要熟悉数据模型。

>[!NOTE]
>您可以生成数据模型的完整描述。 在[此页面](datamodel.md)中了解详情。

## [!DNL Campaign] API暂存机制

对于[!DNL Campaign]云数据库，由于性能（延迟和并发），不建议使用爆炸式统一调用。 批处理操作始终为首选。 为了确保API的最佳性能，Campaign会保持在本地数据库级别处理API调用。

[!DNL :bulb:] [本页详细介绍了API暂存机制](staging.md)

## 新API

提供了新的API，用于管理[!DNL Campaign]本地数据库与云数据库之间的数据同步。 还引入了一种新机制，用于在本地数据库级别处理API调用，以避免延迟并提高整体性能

[!DNL :bulb:] [本页详细介绍了新的API](new-apis.md)

**相关主题**

* [数据模型最佳实践](datamodel-best-practices.md)
