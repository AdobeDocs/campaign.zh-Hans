---
product: Adobe Campaign
title: Campaign Classic v7 - Campaign v8 功能矩阵
description: 了解 Campaign Classic v7 和 Campaign v8 之间的差异
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 40b38168a3704f171f1f389e2d232e6a2c6f1d85
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 44%

---

# [!DNL Campaign Classic] v7 -  [!DNL Campaign] v8功能{#gs-matrix}

作为现有的[!DNL Campaign Classic] v7用户，您不应期望与[!DNL Adobe Campaign]的交互方式出现任何大中断。 除了 UI 和配置步骤中显现的小变化外，v8 中的大多数变化都不明显。

关键变化：

* 区段创建速度提高 200 倍
* 投放速度提升
* 实时报告 包含多维数据集

作为[!DNL Campaign Classic]用户，请注意，大多数[!DNL Campaign Classic] v7功能在[!DNL Campaign] v8中可用，但在[此部分](#gs-removed)中列出的一小组功能除外。 其他功能将在未来版本中发布。[在此部分中了解更多信息](#gs-unavailable-features)

[!DNL :bulb:] 在本页了解 [!DNL Campaign] 有关v8架构的 [更多信息](../dev/architecture.md)。

## 产品配置变化

### [!DNL Campaign] 和  [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8与两个数据库配合使用：用于用户界面实时消息传送和统一查询和通过API写入的本地数据库，以及用于促销活动执行、批量查询和工作流执行的云数据库。

这是软件架构的重大变化。数据现在位于远程位置，Campaign 会联合所有数据（包括用户档案）。[!DNL Campaign]从定位到消息执行， 流程现在实现了端到端扩展：数据摄取、分段、定位、查询、投放现在通常可在几分钟内运行。这个新版本解决了扩展的全部难题，同时保持了相同级别的灵活性和可扩展性。用户档案的数量几乎是无限的，而且可以延长数据保留时间。

云存储在&#x200B;**[!DNL Snowflake]**&#x200B;中执行：新的内置&#x200B;**外部帐户**&#x200B;可确保与云数据库的连接。 它由Adobe配置，不得修改。 [了解详情](../config/external-accounts.md)。

需要在云数据库中移动或复制的任何内置模式/表格都在 **xxl** 命名空间下附带内置模式扩展。这些扩展包含将内置架构从[!DNL Campaign]本地数据库移动到[!DNL Snowflake]云数据库并相应地调整其结构所需的任何修改：新UUID、更新的链接等

>[!CAUTION]
>
> 客户数据未存储在本地[!DNL Campaign]数据库中。 因此，所有自定义表格都需要在云数据库中创建。


特定API可用于管理本地数据库和云数据库之间的数据。 了解这些新API的工作方式以及如何在[本页](../dev/new-apis.md)中使用它们。

### 数据复制

特定的技术工作流可处理需要存在于两端（Campaign 本地数据库和云数据库）的表格的复制操作。此工作流每小时都会触发一次，并且依赖于新的内置 JavaScript 库。

>[!NOTE]
>
> 已根据表格的大小（XS、XL等）创建了多种复制策略。
> 部分表格是实时复制的，其他表格则是每小时复制一次。部分表格将具有增量更新，而其他表格则将进行全面更新。


[了解有关数据复制的更多信息](../config/replication.md)

### ID 管理

Campaign v8 对象现在使用&#x200B;**通用唯一标识符 (UUID)**，允许使用无限的唯一值来标识数据。

请注意，此ID基于字符串，而不是连续的。 主键不是Campaign v8中的数字值，您需要在架构中使用&#x200B;**autouuid**&#x200B;和&#x200B;**autopk**&#x200B;属性。

在Campaign Classicv7及更早版本中，架构（即表）中键的唯一性在数据库引擎的级别处理。 更一般地， PostgreSQL、Oracle或SQL Server等经典数据库引擎包括本机机制，以防止通过主键和/或唯一索引根据列或一组列插入重复的行。 在数据库级别设置正确的索引和主键后，这些版本中不存在重复的ID。

Adobecampaign v8以Snowflake为核心数据库。 随着查询规模的显着增加，Snowflake数据库的分布式架构不提供这样的机制来管理然后强制表中某个密钥的唯一性。 因此，使用Adobe Campaign v8时，没有任何内容会阻止在表中摄取重复的键。 最终用户现在负责确保Adobe Campaign数据库中密钥的一致性。 [了解详情](../dev/keys.md)。


### 简化的维护

Campaign 用户不需要成为数据库专家：不再需要执行复杂的数据库维护操作或编制复杂的表格索引。

## 不可用功能{#gs-unavailable-features}

请注意，此第一个版本中没有某些功能，例如：

* 营销资源管理
* 分布式营销
* 入站 Offer Decisioning（交互模块）
* 活动优化
* 响应管理器
* 混合/内部部署模型

>[!CAUTION]
>
>目前，Campaign v8仅&#x200B;****&#x200B;可用作托管Cloud Service，不能部署在内部部署或混合环境中。
>
>从现有Campaign Classicv7环境进行迁移的功能尚不可用。
>
>如果您不确定部署模型或有任何问题，请与您的客户团队联系。

## 移除的功能{#gs-removed}

为了与 Campaign v8 的新架构和部署模型保持一致，Campaign v8 中不再提供某些 Campaign Classic v7 的旧功能。

* 优惠券
* Web 跟踪
* 调查
* 社交媒体营销
* ACS 连接器（高级服务）

