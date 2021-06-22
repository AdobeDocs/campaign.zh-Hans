---
product: Adobe Campaign
title: 技术工作流和数据复制
description: 技术工作流和数据复制
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 3%

---

# 技术工作流和数据复制

## 技术工作流{#tech-wf}

Adobe Campaign附带一组内置的技术工作流。 技术工作流会定期在服务器上执行进程或作业。

这些工作流对数据库执行维护操作，利用投放日志中的跟踪信息，创建定期活动等。

[!DNL :arrow_upper_right:] 技术工作流的完整列表详见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;}


除了这些技术工作流之外，Campaign v8还依赖特定的技术工作流来管理[数据复制](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流可自动复制Campaign本地数据库(Postgres)和云数据库([!DNL Snowflake])上需要存在的内置表。计划每小时执行一次。 如果存在&#x200B;**lastModified**&#x200B;字段，则会以增量方式进行复制，否则会复制整个表。 下面数组中表的顺序是复制工作流使用的顺序。
* **[!UICONTROL Replicate Staging data]**
此工作流会为统一调用复制暂存数据。计划每小时执行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
   此工作流会立即部署到云数据库。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流会复制给定外部帐户的XS数据。

Campaign Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]**&#x200B;节点提供了这些技术工作流。 **不得更改它们。**

如果需要，您可以手动启动数据同步。 要执行此操作，请右键单击&#x200B;**调度程序**&#x200B;活动，然后选择&#x200B;**立即执行挂起任务**。

## 数据复制{#data-replication}

某些内置表通过上述专用工作流从Campaign本地数据库复制到[!DNL Snowflake]云数据库。

复制策略基于表的大小。 有些表将实时复制，有些表将按小时复制。 某些表在替换其他表时将进行增量更新。

除了内置的&#x200B;**复制参考表**&#x200B;技术工作流之外，您还可以在工作流中强制进行数据复制。

您可以：

* 使用以下代码添加特定的&#x200B;**Javascript代码**&#x200B;活动：

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 使用以下命令添加特定的&#x200B;**nlmodule**&#x200B;活动：

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)

**相关主题**

[!DNL :arrow_upper_right:] 了解如何开始使用 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}中的工作流

[!DNL :bulb:] 在此部分中访问数据保 [留期](../dev/datamodel-best-practices.md#data-retention)
