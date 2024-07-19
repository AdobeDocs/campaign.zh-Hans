---
title: 技术工作流和数据复制
description: 技术工作流和数据复制
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# 技术工作流和数据复制 {#wf-data-replication}

## 技术工作流 {#tech-wf}

在[企业(FFDA)部署](enterprise-deployment.md)的上下文中，Adobe Campaign提供了一组内置的技术工作流。 技术工作流在服务器上定期执行进程或作业。

这些工作流对数据库执行维护操作，利用投放日志中的跟踪信息，创建循环活动等。

[此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}中详细列出了技术工作流的完整列表。

除了这些技术工作流之外，Campaign v8还依赖特定的技术工作流来管理[数据复制](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流会对Campaign本地数据库(Postgres)和云数据库([!DNL Snowflake])上需要存在的内置表执行自动复制。 按计划每天每小时执行一次。 如果存在&#x200B;**lastModified**&#x200B;字段，则会增量进行复制，否则将复制整个表。 以下数组中表的顺序是复制工作流使用的顺序。
* **[!UICONTROL Replicate Staging data]**
此工作流会复制单一调用的暂存数据。 按计划每天每小时执行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
  此工作流执行到云数据库的即时部署。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流会复制给定外部帐户的XS数据。

这些技术工作流可从Campaign Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]**&#x200B;节点中获取。 **不能修改它们。**

如果需要，您可以手动启动数据同步。 要执行此操作，请右键单击&#x200B;**调度程序**&#x200B;活动，然后选择&#x200B;**立即执行待处理任务**。

## 数据复制 {#data-replication}

某些内置表通过上述专用工作流从Campaign本地数据库复制到[!DNL Snowflake]云数据库。

了解Adobe Campaign v8使用哪些数据库、复制数据的原因、复制的数据以及复制过程的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 数据复制策略 {#data-replication-policies}

复制策略基于表的大小。 有些表是实时复制的，有些表是每小时复制一次。 某些表将具有增量更新，而其他表将被替换。

除了内置的&#x200B;**复制参考表**&#x200B;技术工作流之外，您还可以强制在工作流中进行数据复制。

您可以：

* 使用以下代码添加特定&#x200B;**Javascript代码**&#x200B;活动：

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 使用以下命令添加特定&#x200B;**nlmodule**&#x200B;活动：

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**相关主题**

* [了解如何开始使用工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}

* [数据保留期](../dev/datamodel-best-practices.md#data-retention)
