---
solution: Campaign
product: Adobe Campaign
title: Campaign Classic v7 - 活动 v8功能矩阵
description: 了解Campaign Classic v7和活动 v8之间的差异
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: e1308398e5a33f2ad9659ad632aeb05af9916e69
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 3%

---

# Campaign Classic v7 - 活动 v8功能{#gs-matrix}


作为现有的Campaign Classic v7用户，您不应期望与Adobe Campaign的交互方式出现任何大中断。 除了UI和配置步骤中显示的小更改外，v8中的大多数更改都不可见。

关键更改：

* 将细分创建速度提高200倍

* 提高投放

* 实时报告

作为Campaign Classic用户，请注意，Campaign Classic v7的大多数功能都随活动 v8提供，但[本节](#gs-removed)列出的一小组功能除外。 其他将在未来版本中发布。 [了解详情](#gs-unavailable-features)


## 产品配置更改

### 活动和[!DNL Snowflake] {#ac-gs-snowflake}

云存储在[!DNL Snowflake]中执行：新的外部帐户可确保与云数据库的连接。 [了解详情](#ac-gs-snowflake)。

这是软件体系结构的基本变化。 数据现在是远程的，活动将整个数据(包括用户档案)联合起来。 活动流程现在从定位到消息执行，逐个扩展：数据摄取、细分、定位、查询、投放通常在几分钟内即可运行。

此新版本解决了扩展的全部难题，同时保持相同级别的灵活性和可扩展性。 用户档案的数量几乎是无限的，而且可以扩展数据保留。

新的内置&#x200B;**外部帐户**&#x200B;专用于“完全联合数据访问”。 这是云数据库连接的核心。 我们建议按原样离开。

需要在云模式库中移动或复制的任何内置模式/表都在&#x200B;**xxl**&#x200B;命名空间下附带内置扩展。

这些扩展包含将内置模式从活动本地数据库移动到[!DNL Snowflake]云数据库并相应地调整其结构所需的任何修改：新的UUID、更新的链接等。

>[!CAUTION]
>
> 客户数据不存储在本地活动数据库中。 因此，任何自定义表都需要在Cloud数据库中创建。


### 数据复制

特定的技术工作流程可处理需要在两侧(活动本地数据库和云数据库)上显示的表的复制。 此工作流每小时都会触发一次，并且依赖于新的内置JavaScript库。

>[!NOTE]
>
> 已根据表（XS、XL等）的大小创建了多个复制策略。
> 一些表是实时复制的，其他表是每小时复制一次。 某些表将具有增量更新，而其他表将进行完整更新。


[了解有关数据复制的更多信息](../config/replication.md)

### ID管理

活动 v8对象现在使用&#x200B;**通用唯一ID(UUID)**，它允许无限的唯一值来标识数据

请不要说此ID是基于字符串的，不是按顺序的。

### 简化的维护

活动用户不需要成为数据库专家：不再需要复杂的数据库维护操作或复杂的表索引。

## 临时不可用功能{#gs-unavailable-features}

请注意，第一个版本中尚未提供某些功能，例如：

* 营销资源管理
* 分布式营销
* 入站优惠管理（交互模块）
* 活动优化
* 响应管理器
* 混合/内部部署模型

## 移除的功能{#gs-removed}

为了与活动 v8的新架构和部署模型保持一致，活动 v8中不再提供某些具有历史意义的Campaign Classic v7功能。

* 优惠券
* Web 跟踪
* 调查
* 社交媒体营销
* ACS连接器（Prime提供）

