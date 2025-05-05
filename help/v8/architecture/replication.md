---
title: 数据复制
description: 技术工作流和数据复制
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: b8f774ce507cff67163064b6bd1341b31512c08f
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%

---


# 数据复制 {#wf-data-replication}

## 原则

在[Enterprise (FFDA)部署](enterprise-deployment.md)的上下文中，数据复制可确保Campaign本地数据库(PostgreSQL)和云数据库([!DNL Snowflake])这两个数据库并行运行并保持实时同步。

云数据库([!DNL Snowflake])已针对处理大型数据批次（如更新100万个地址）进行了优化。 同时，Campaign本地数据库(PostgreSQL)更适合于单个或小容量操作，例如更新单个种子地址。 同步在后台自动且透明地进行，确保Campaign本地数据库(PostgreSQL)中的数据实时在云数据库([!DNL Snowflake])中重复，从而使两个数据库保持同步。 数据同步涉及架构和表以及数据。

➡️[了解数据复制在视频中的工作方式](#video)

## 复制模式 {#modes}

根据用例的不同，数据复制可能会以不同的模式进行。

* **动态复制**&#x200B;处理实时复制至关重要的情况。 它依靠特定的技术线程立即复制数据，以用于创建扩散或更新种子地址等用例。
* 在不需要立即同步时使用&#x200B;**计划的复制**。 计划的复制使用每小时运行一次的特定[技术工作流](#workflows)来同步数据，如类型规则。

## 复制策略

复制策略定义从Campaign本地数据库(PostgreSQL)表复制的数据量。 这些策略取决于表的大小和特定的用例。 某些表将具有增量更新，而其他表将被完全复制。 有三种主要类型的复制策略：

* **XS**：此策略用于大小较小的表。 将整个表复制为一个快照。 增量复制通过使用时间戳指针仅复制最近的更改来避免重复复制相同的数据。
* **SingleRow**：此策略一次只复制一行。 它通常用于涉及当前Campaign对象和相关对象的动态复制。
* **SomeRows**：此策略设计用于使用查询定义或筛选器复制有限的数据子集。 它用于需要选择性复制的大型表。

## 复制工作流 {#workflows}

Campaign v8依靠特定的技术工作流来管理计划的数据复制。 这些技术工作流可从Campaign Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]**&#x200B;节点中获取。 **不能修改它们。**

技术工作流在服务器上定期执行进程或作业。 [此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=zh-Hans){target="_blank"}中详细列出了技术工作流的完整列表。

确保数据复制的技术工作流程如下所示：

| 技术工作流 | 说明 |
|------|-----------|
| **[!UICONTROL Replicate Reference tables]** (ffdaReplicateReferenceTables) | 执行需要存在于Campaign本地数据库(PostgreSQL)和云数据库([!DNL Snowflake])上的内置表的自动复制。 按计划每天每小时执行一次。 如果存在&#x200B;**lastModified**&#x200B;字段，则会增量进行复制，否则将复制整个表。 |
| **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) | 为单一调用复制暂存数据。 按计划每天每小时执行一次。 |
| **[!UICONTROL Deploy FFDA immediately]** (ffdaDeploy) | 对云数据库执行立即部署。 |
| **[!UICONTROL Replicate FFDA data immediately]** (ffdaReplicate) | 复制给定外部帐户的XS数据。 |

如果需要，您可以手动启动数据同步。 为此，请右键单击&#x200B;**调度程序**&#x200B;活动，然后选择&#x200B;**立即执行待处理任务**。

除了内置&#x200B;**复制引用表**&#x200B;技术工作流之外，您还可以使用以下方法之一在工作流中强制复制数据

+++如何强制数据复制

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

+++

<br/>

>[!NOTE]
>
>动态复制由特定的技术线程而不是工作流处理。 此模式的配置在serverConf.xml文件中进行管理。 您可以配置serverConf.xml以匹配特定的用例，例如请求XS表以增量方式复制，而不是完全复制。 有关更多信息，请与您的 Adobe 代表联系。

## API

API允许将自定义数据和开箱即用数据从Campaign本地数据库(PostgreSQL)复制到云数据库([!DNL Snowflake])。 这些API允许您绕过预定义的工作流，并根据特定要求（如复制自定义表）自定义复制。

例如：

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="cus:recipient"/>
    </params>
);
```

## 复制队列

如果同时发生大量复制请求，则云数据库([!DNL Snowflake])中可能会出现性能问题，这是由于在MERGE操作期间出现表级锁定所致。 为了缓解这种情况，集中化的复制工作流会将请求分组到队列中。

每个队列都由一个技术工作流处理，该工作流管理特定表的复制，作为单个MERGE操作执行挂起请求。 这些工作流每20秒触发一次，以处理新的复制请求：

| 技术工作流 | 说明 |
|------|-----------|
| **复制nmsDelivery队列** (ffdaReplicateQueueDelivery) | `nms:delivery`表的队列。 |
| **复制nmsDlvExclusion队列** (ffdaReplicateQueueDlvExclusion) | `nms:dlvExclusion`表的队列。 |
| **复制nmsDlvMidRemoteIdRel队列** (ffdaReplicateQueueDlvMidRemoteIdRel) | `nms:dlvRemoteIdRel`表的队列。 |
| **复制nmsTrackingUrl队列** (ffdaReplicateQueueTrackingUrl)<br/>**以并行方式复制nmsTrackingUrl队列** (ffdaReplicateQueueTrackingUrl_2) | `nms:trackingUrl`表的并发队列，利用两个工作流根据不同的优先级处理请求，从而提高效率。 |

## 教程 {#video}

此视频介绍Adobe Campaign v8使用哪些数据库、为何复制数据、正在复制哪些数据以及复制过程的工作方式等关键概念。

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)

[此处](https://experienceleague.adobe.com/zh-hans/docs/campaign-learn/tutorials/overview)提供了其他Campaign v8客户端控制台教程。
