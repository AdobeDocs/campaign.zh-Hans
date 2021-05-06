---
solution: Campaign Classic
product: campaign
title: 技术工作流和数据复制
description: 技术工作流和数据复制
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: 9efd6442336a62e627b0da4e17fa742f59f715f9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 1%

---

# 技术工作流和数据复制

## 技术工作流

Adobe Campaign附带一组内置技术工作流。 技术工作流在服务器上定期执行进程或作业。

这些工作流对投放日志库执行维护操作，利用数据库中的跟踪信息，创建循环活动等。

:arrow_upper_right:技术工作流的完整列表详见[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

除了这些技术工作流之外，活动 v8还依赖特定技术工作流来管理[数据复制](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流会自动复制需要在活动本地数据库(Postgres)和云数据库(Snowflake)上显示的参考表。计划每天每小时执行一次。 如果 
**lastModified** 字段存在，复制会以增量方式进行，否则会复制整个表。以下数组中表的顺序是复制工作流使用的顺序。
* **[!UICONTROL Replicate Staging data]**
此工作流将复制统一调用的暂存数据。计划每天每小时执行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
   此工作流会立即部署到云数据库。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流将复制给定外部帐户的XS数据。

这些技术工作流可从活动 Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]**&#x200B;节点中访问。

## 数据复制{#data-replication}

表将通过上面描述的专用工作流从活动数据库复制到Snowflake Cloud数据库。

复制策略基于表的大小。 将复制某些表。 一些表格将实时复制，而其他表格将按小时复制。 在替换其他表时，某些表将具有增量更新。

**我们应该列表所有表格吗？**

要检查

**相关主题**

:arrow_upper_right:了解如何开始使用[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)中的工作流

：灯泡：访问[此部分](../dev/datamodel-best-practices.md#data-retention)中的数据保留期
