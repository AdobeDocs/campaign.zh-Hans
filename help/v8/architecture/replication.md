---
title: 技术工作流和数据复制
description: 技术工作流和数据复制
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 5%

---

# 技术工作流和数据复制 {#wf-data-replication}

## 技术工作流 {#tech-wf}

在上下文中 [企业(FFDA)部署](enterprise-deployment.md)，Adobe Campaign附带一组内置的技术工作流。 技术工作流在服务器上定期执行进程或作业。

这些工作流对数据库执行维护操作，利用投放日志中的跟踪信息，创建循环活动等。

![](../assets/do-not-localize/glass.png) 有关技术工作流的完整列表，请参见 [此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html).

除了这些技术工作流之外，Campaign v8还依靠特定的技术工作流来管理 [数据复制](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
此工作流可自动复制需要存在于Campaign本地数据库(Postgres)和云数据库([!DNL Snowflake])。 按计划每天每小时执行一次。 如果 **lastModified** 字段存在，增量进行复制，否则复制整个表。 以下数组中表的顺序是复制工作流使用的顺序。
* **[!UICONTROL Replicate Staging data]**
此工作流会复制单一调用的暂存数据。 按计划每天每小时执行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
  此工作流执行到云数据库的即时部署。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流会复制给定外部帐户的XS数据。

这些技术工作流可从 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** Campaign资源管理器节点。 **不得更改它们。**

如果需要，您可以手动启动数据同步。 要执行此操作，请右键单击 **计划程序** 活动和选择 **立即执行挂起的任务**.

## 数据复制 {#data-replication}

某些内置表从Campaign本地数据库复制到 [!DNL Snowflake] 通过上述专用工作流访问云数据库。

了解Adobe Campaign v8使用哪些数据库、复制数据的原因、复制的数据以及复制过程的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 数据复制策略 {#data-replication-policies}

复制策略基于表的大小。 有些表将实时复制，有些表将每小时复制一次。 某些表将具有增量更新，而其他表将被替换。

除了内置 **复制引用表** 技术工作流，您可以在工作流中强制数据复制。

您可以：

* 添加特定 **Javascript代码** 活动，代码如下：

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 添加特定 **nlmodule** 使用下列命令执行活动：

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**相关主题**

* [了解如何开始使用工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans)

* [数据保留期](../dev/datamodel-best-practices.md#data-retention)
