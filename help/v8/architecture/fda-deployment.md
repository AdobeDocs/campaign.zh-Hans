---
title: Campaign FDASnowflake部署入门
description: Campaign FDASnowflake部署入门
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] 部署{#gs-fda-snowflake}

在 [!DNL Snowflake] FDA（默认）部署， [!DNL Adobe Campaign] v8已连接到 [!DNL Snowflake] 访问数据 [联合数据访问](../connect/fda.md) 功能：您可以访问和处理存储在贵机构中的 [!DNL Snowflake] 数据库，而不更改Adobe Campaign数据的结构。

## 好处{#fda-benefits}

此部署模型具有以下优势：

* **存储和性能**
您可以将历史数据移动到 [!DNL Snowflake] 然后将依赖关系降低到Adobe Campaign ID限制。 此体系结构还降低了您对PostgreSQL存储和性能限制的依赖性。 由于Campaign数据库中存储的数据较少，因此性能会更好，并且执行维护任务会更快。

* **数据模型扩展和数据管理**
您可以在中创建表 [!DNL Snowflake] 并将它们链接到Adobe Campaign，例如，使用保留期内的存档数据，或运行性能卓越的分段过程。

   此架构还允许您在中使用数据管理工作流功能 [!DNL Snowflake]. 出于个性化和投放目的，仅将聚合和临时表移动到Campaign。


## 架构{#fda-archi}

通过此部署模型，Adobe Campaign用户可以将其数据扩展到 [!DNL Snowflake] 并利用单个集成数据平台的优势，实时提供强大的营销活动数据洞察。 它通过提供单一、统一且易于使用的数据分析平台，为用户提供了从数据中发掘巨大价值的能力。 云数据平台无需管理，因为它可无限扩展以支持来自Adobe Campaign的任何数量营销数据。

服务器和进程之间的一般通信按照以下模式进行：

![](assets/fda-architecture.png)

PostgreSQL是主数据库，Snowflake是辅助数据库。 您可以扩展数据模型并将数据存储在Snowflake上。 随后，您可以对具有出色性能的大型数据集运行ETL、分段和报告。
