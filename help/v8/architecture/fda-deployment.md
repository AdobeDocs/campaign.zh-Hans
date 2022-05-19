---
title: Campaign FDASnowflake部署入门
description: Campaign FDASnowflake部署入门
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] 部署{#gs-fda-snowflake}

在 [!DNL Snowflake] FDA（默认）部署， [!DNL Adobe Campaign] v8连接到 [!DNL Snowflake] 通过 [联合数据访问](../connect/fda.md) 功能：您可以访问和处理存储在 [!DNL Snowflake] 数据库，而不改变Adobe Campaign数据的结构。

## 好处{#fda-benefits}

此部署模型具有以下优势：

* **存储和性能**
您可以将历史数据移至 [!DNL Snowflake] 然后，减少对Adobe Campaign ID的依赖性限制。 此体系结构还降低了您对PostgreSQL存储和性能限制的依赖性。 由于Campaign数据库中存储的数据较少，因此性能更好，执行维护任务的速度也更快。

* **数据模型扩展和数据管理**
您可以在 [!DNL Snowflake] 并将它们链接到Adobe Campaign，例如在保留期内使用存档数据，或运行性能卓越的分段流程。

   此架构还允许您在 [!DNL Snowflake]. 只有聚合表和临时表会移动到Campaign中以用于个性化和投放。


## 架构{#fda-archi}

通过此部署模型，Adobe Campaign用户可以将其数据扩展到 [!DNL Snowflake] 并利用单个集成数据平台的优势，实时分析强大的营销活动数据。 它为用户提供了一个用于数据分析的统一且易于使用的平台，让用户能够从其数据中释放出深层价值。 云数据平台无需管理，因为它可以无限扩展以支持来自Adobe Campaign的任意数量的营销数据。

服务器和进程之间的一般通信按照以下模式进行：

![](assets/fda-architecture.png)

PostgreSQL是主数据库，Snowflake是次数据库。 您可以扩展数据模型并在Snowflake上存储数据。 随后，您可以对性能卓越的大型数据集运行ETL、分段和报告。
