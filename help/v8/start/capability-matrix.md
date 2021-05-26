---
solution: Campaign v8
product: Adobe Campaign
title: Campaign Classicv7 - Campaign v8功能矩阵
description: 了解Campaign Classicv7和Campaign v8之间的差异
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 2%

---

# [!DNL Campaign Classic] v7 -  [!DNL Campaign] v8功能{#gs-matrix}

作为现有的[!DNL Campaign Classic] v7用户，您不应期望与[!DNL Adobe Campaign]的交互方式出现任何大中断。 v8中的大多数更改都不可见，除了UI和配置步骤中显示的小更改外。

关键更改：

* 区段的创建速度最多提高200倍
* 提高交付速度
* 使用多维数据集进行实时报告

作为[!DNL Campaign Classic]用户，请注意，大多数[!DNL Campaign Classic] v7功能在[!DNL Campaign] v8中可用，但在[此部分](#gs-removed)中列出的一小组功能除外。 其他的将来版本将推出。 [在此部分中了解更多信息](#gs-unavailable-features)

[!DNL :bulb:] 在本页了解 [!DNL Campaign] 有关v8架构的 [更多信息](../dev/architecture.md)。

## 产品配置更改

### [!DNL Campaign] 和  [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8与两个数据库配合使用：用于用户界面实时消息传送和统一查询和通过API写入的本地数据库，以及用于促销活动执行、批量查询和工作流执行的云数据库。

这是软件架构的基本变化。 数据现在是远程的，并且Campaign会联合整个数据，包括用户档案。 [!DNL Campaign] 流程现在可从定位到消息执行，进行端到端的扩展：数据摄取、分段、定位、查询、投放现在通常在几分钟内运行。此新版本在保持相同级别的灵活性和可扩展性的同时，解决了扩展的整个挑战。 用户档案的数量几乎无限，并且可以延长数据保留期。

云存储在&#x200B;**[!DNL Snowflake]**&#x200B;中执行：新的内置&#x200B;**外部帐户**&#x200B;可确保与云数据库的连接。 它由Adobe配置，不得修改。 [了解详情](../config/external-accounts.md)。

需要在云数据库中移动或复制的任何内置架构/表均在&#x200B;**xxl**&#x200B;命名空间下附带内置架构扩展。 这些扩展包含将内置架构从[!DNL Campaign]本地数据库移动到[!DNL Snowflake]云数据库并相应地调整其结构所需的任何修改：新UUID、更新的链接等

>[!CAUTION]
>
> 客户数据未存储在本地[!DNL Campaign]数据库中。 因此，需要在云数据库中创建任何自定义表。


特定API可用于管理本地数据库和云数据库之间的数据。 了解这些新API的工作方式以及如何在[本页](../dev/new-apis.md)中使用它们。

### 数据复制

特定的技术工作流处理需要出现在两侧的表（Campaign本地数据库和云数据库）的复制。 此工作流每小时触发一次，并且依赖于新的内置JavaScript库。

>[!NOTE]
>
> 已根据表的大小（XS、XL等）创建了多个复制策略。
> 有些表是实时复制的，另一些表是每小时复制一次。 有些表将进行增量更新，而另一些表将进行完整更新。


[了解有关数据复制的更多信息](../config/replication.md)

### ID管理

Campaign v8对象现在使用&#x200B;**通用唯一ID(UUID)**，该UUID允许无限制的唯一值来标识数据

请注意，此ID基于字符串，而不是连续的。

### 简化的维护

Campaign用户无需是数据库专家：不再需要复杂的数据库维护操作或复杂的表索引。

## 临时不可用功能{#gs-unavailable-features}

请注意，此第一个版本中尚未提供某些功能，例如：

* 营销资源管理
* 分布式营销
* 入站选件管理（交互模块）
* 活动优化
* 响应管理器
* 混合/内部部署模型

## 移除的功能{#gs-removed}

为了与Campaign v8新架构和部署模型保持一致，Campaign v8中不再提供一些历史Campaign Classicv7功能。

* 优惠券
* Web 跟踪
* 调查
* 社交媒体营销
* ACS Connector（Prime产品）

