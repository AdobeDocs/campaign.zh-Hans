---
title: Campaign FDA部署入门
description: Campaign FDA部署入门
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 561e4b6d2c99e98e068132c80c2bebb756b60a44
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# [!DNL Campaign] FDA部署{#gs-fda}

在其Campaign FDA（默认）部署中，[!DNL Adobe Campaign] v8可以连接到[!DNL Snowflake]以通过[联合数据访问](../connect/fda.md)功能访问数据：然后，您可以访问和处理存储在[!DNL Snowflake]数据库中的外部数据和信息，而无需更改Adobe Campaign数据的结构。

>[!NOTE]
>
>在此部署模型中，[!DNL Snowflake]辅助数据库仅在请求时可用。 若要使用[!DNL Snowflake]更新部署，请联系您的Adobe过渡经理。
>

## 好处{#fda-benefits}

此部署模型具有以下优势：

* **存储和性能**
您可以将历史数据移动到[!DNL Snowflake]，然后将依赖关系减少到Adobe Campaign ID限制。 此体系结构还降低了您对PostgreSQL存储的依赖性和性能限制。 由于Campaign数据库中存储的数据较少，因此性能会更好，并且执行维护任务的速度会更快。

* **数据模型扩展和数据管理**
您可以在[!DNL Snowflake]中创建表并将它们链接到Adobe Campaign，例如，使用保留期内的存档数据，或运行性能卓越的分段过程。

  此架构还允许您在[!DNL Snowflake]中使用数据管理工作流功能。 出于个性化和投放目的，仅将聚合和临时表移动到Campaign。


## 架构{#fda-archi}

利用此部署模型，Adobe Campaign用户可以将其数据扩展到[!DNL Snowflake]，并利用单个集成数据平台的好处实时提供强大的营销活动数据洞察。 它为用户提供了一个单一、统一且易于使用的数据分析平台，从而为用户提供了从其数据发掘巨大价值的能力。 云数据平台无需管理，因为它可无限扩展以支持Adobe Campaign的任何数量营销数据。

服务器和进程之间的一般通信按照以下模式进行：

![](assets/fda-architecture.png)

PostgreSQL是主数据库，Snowflake可用作辅助数据库。 您可以扩展数据模型并将数据存储在Snowflake上。 随后，您可以对具有出色性能的大型数据集运行ETL、分段和报告。
