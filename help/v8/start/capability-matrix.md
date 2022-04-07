---
title: Campaign Classic v7 - Campaign v8 功能矩阵
description: 了解 Campaign Classic v7 和 Campaign v8 之间的差异
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 2d0b40e49afdfd71e8bb5c3f0b1d569a715420b2
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 98%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8 功能{#gs-matrix}

作为现有的 [!DNL Campaign Classic] v7 用户，您与 [!DNL Adobe Campaign] 的交互方式不会发生任何大的变化。除了 UI 和配置步骤中显现的小变化外，v8 中的大多数变化都不明显。

关键变化：

* 区段创建速度提高 200 倍
* 投放速度提升
* 实时报告包含多维数据集

作为 [!DNL Campaign Classic] 用户，请注意， v7 的大多数功能[!DNL Campaign Classic]都可以在[!DNL Campaign] v8 中使用，但[本节](#gs-removed)所列的一小部分功能除外。其他功能将在以后的版本中发布。[在本节中了解详情](#gs-unavailable-features)

![](../assets/do-not-localize/glass.png)如需详细了解[!DNL Campaign] v8 架构，请参阅[此页面](../dev/architecture.md)。

## 产品配置变化

### [!DNL Campaign] 和 [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 可与两个数据库配合使用：用于用户界面实时消息传递和统一查询、通过 API 写入的本地数据库，以及用于活动执行、批量查询和工作流执行的云数据库。

这是软件架构的重大变化。数据现在位于远程位置，Campaign 会联合所有数据（包括用户档案）。[!DNL Campaign] 流程现在实现了端到端扩展，从定位到消息执行：数据摄取、分段、定位、查询、投放一般只需要几分钟即可运行。这个新版本解决了扩展的全部难题，同时保持了相同级别的灵活性和可扩展性。用户档案的数量几乎是无限的，而且可以延长数据保留时间。

云存储在 **[!DNL Snowflake]** 中执行：一种新的内置&#x200B;**外部帐户**&#x200B;可确保与云数据库的连接。它由 Adobe 配置，不可修改。[了解详情](../config/external-accounts.md)

需要在云数据库中移动或复制的任何内置模式/表格都在 **xxl** 命名空间下附带内置模式扩展。这些扩展包含将内置模式从[!DNL Campaign]本地数据库移动到 [!DNL Snowflake] 云数据库并相应地调整其结构所需的任何修改：新的 UUID、更新的链接等。

>[!CAUTION]
>
> 客户数据并不存储在本地 [!DNL Campaign] 数据库中。因此，所有自定义表格都需要在云数据库中创建。

特定 API 可用于管理本地数据库和云数据库之间的数据。在[本页面](../dev/new-apis.md)中了解这些新 API 的工作方式以及如何使用它们。

### 数据复制

特定的技术工作流可处理需要存在于两端（Campaign 本地数据库和云数据库）的表格的复制操作。此工作流每小时都会触发一次，并且依赖于新的内置 JavaScript 库。

>[!NOTE]
>
> 已根据表格的大小（XS、XL等）创建了多种复制策略。
> 部分表格是实时复制的，其他表格则是每小时复制一次。部分表格将具有增量更新，而其他表格则将进行全面更新。

[了解关于数据复制的更多信息](../config/replication.md)

### ID 管理

Campaign v8 对象现在使用&#x200B;**通用唯一标识符 (UUID)**，允许使用无限的唯一值来标识数据。

请注意，此 ID 是基于字符串的，而不是按顺序的。主密钥不是 Campaign v8 中的数字值，您需要在模式中使用 **autouuid** 和 **autopk** 属性。

在 Campaign Classic v7 及更早的版本中，模式（即表格）中密钥的唯一性在数据库引擎级别进行处理。一般来说，PostgreSQL、Oracle 或 SQL Server 等 Classic 数据库引擎包含原生机制，以防止通过主密钥和/或唯一索引根据列或一组列插入重复的行。在数据库级别设置正确的索引和主密钥后，这些版本中不存在重复的 ID。

Adobe Campaign v8以Snowflake为核心数据库。 随着查询规模的显着增长，Snowflake 数据库的分布式架构无法提供这样的机制来管理并对表格中某个密钥强制执行唯一性。因此，使用 Adobe Campaign v8 时，没有任何内容会阻止在表格中摄取重复的密钥。现在，最终用户负责确保 Adobe Campaign 数据库中密钥的一致性。[了解详情](../dev/keys.md)

### 简化的维护

Campaign 用户不需要成为数据库专家：不再需要执行复杂的数据库维护操作或编制复杂的表格索引。

## 连接至 Campaign

Campaign 用户通过其 Adobe ID 进行连接。使用同一个 Adobe ID 来管理与单个帐户关联的所有 Adobe 计划和产品。

![](../assets/do-not-localize/glass.png) 有关如何连接到 [!DNL Campaign]，请参阅[此页面](connect.md)。

## 报告

请注意，与 Adobe Campaign v7 相比，Campaign Classic 报表已得到优化，并提供了更好的扩展功能。 多维数据集的限制不适用。

## 工作流 {#workflow}

Campaign v8 增添了一个定位工作流活动：**[!UICONTROL Change data source]**。

利用 **[!UICONTROL Change data source]** 活动，可更改工作流 **[!UICONTROL Working table]** 的数据源，以管理跨不同数据源（如 FDA、FFDA 和本地数据库）的数据。

![](../assets/do-not-localize/glass.png) 有关 **[!UICONTROL Change data source]** 活动的更多信息，请参阅[此页面](../config/workflows.md#change-data-source-activity)。

## 不可用功能{#gs-unavailable-features}

请注意，在此版本 Campaign 中未提供某些功能，例如：

* 营销资源管理
* 分布式营销
* 响应管理器
* 混合/内部部署模型

>[!CAUTION]
>
>* 目前，Campaign v8 **仅**&#x200B;作为托管云服务提供，不能部署在内部部署或混合环境中。
>
>* 从现有 Campaign Classic v7 环境进行迁移的功能尚不可用。
>
>* 如果您不确定部署模式或有任何问题，请与您的客户团队联系。


## 不支持的功能{#gs-removed}

为了与 Campaign v8 的新架构和部署模型保持一致，Campaign v8 不再支持某些 Campaign Classic v7 的旧功能，例如：

* 优惠券
* Web 跟踪
* 调查
* 社交媒体营销使用 Facebook
* ACS 连接器（高级服务）
* 与 LDAP 集成
* 用户/密码登录

>[!NOTE]
>
>用户界面中仍会显示某些不可用或不支持的功能。
