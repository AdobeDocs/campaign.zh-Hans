---
title: 技术工作流和数据复制
description: 技术工作流和数据复制
feature: Workflows, FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 5%

---

# 技术工作流和数据复制

## 技术工作流{#tech-wf}

在 [企业(FFDA)部署](enterprise-deployment.md),Adobe Campaign附带一组内置的技术工作流。 技术工作流会定期在服务器上执行进程或作业。

这些工作流对数据库执行维护操作，利用投放日志中的跟踪信息，创建定期活动等。

![](../assets/do-not-localize/glass.png) 技术工作流的完整列表详见 [本页](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html).

除了这些技术工作流之外，Campaign v8还依赖特定的技术工作流来管理 [数据复制](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
此工作流可自动复制Campaign本地数据库(Postgres)和云数据库([!DNL Snowflake])。 计划每小时执行一次。 如果 **lastModified** 字段存在，复制会以增量方式进行，否则将复制整个表。 下面数组中表的顺序是复制工作流使用的顺序。
* **[!UICONTROL Replicate Staging data]**
此工作流会为统一调用复制暂存数据。 计划每小时执行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
   此工作流会立即部署到云数据库。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流会复制给定外部帐户的XS数据。

这些技术工作流可从 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** Campaign Explorer节点。 **不得更改它们。**

如果需要，您可以手动启动数据同步。 要执行此操作，请右键单击 **调度程序** 活动，选择 **立即执行挂起任务**.

## 数据复制{#data-replication}

某些内置表从Campaign本地数据库复制到 [!DNL Snowflake] 通过上述专用工作流创建云数据库。

了解Adobe Campaign v8使用哪些数据库、为何要复制数据、正在复制哪些数据以及复制过程的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 数据复制策略{#data-replication-policies}

复制策略基于表的大小。 有些表将实时复制，有些表将按小时复制。 某些表在替换其他表时将进行增量更新。

除了内置 **复制参考表** 技术工作流中，您可以在工作流中强制进行数据复制。

您可以：

* 添加特定 **Javascript代码** 活动，其代码如下：

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 添加特定 **nlmodule** 活动时，使用以下命令：

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**相关主题**

* [了解如何开始使用工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans)

* [数据保留期](../dev/datamodel-best-practices.md#data-retention)
