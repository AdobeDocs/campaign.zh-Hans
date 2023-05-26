---
product: campaign
title: 技术工作流
description: 详细了解Campaign提供的技术工作流
feature: Workflows
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1639'
ht-degree: 3%

---

# 技术工作流{#about-technical-workflows}

Adobe Campaign附带一组内置的技术工作流。 他们管理计划在服务器上定期执行的操作和作业。 它们允许您对数据库进行维护、转发投放跟踪信息或设置投放的临时流程。 技术工作流可通过以下方式配置 **[!UICONTROL Administration > Production > Technical workflows]** 节点。

![](assets/navtree.png)

本机模板可用于创建技术工作流。 它们可以根据您的需求进行配置。

此 **[!UICONTROL Campaign process]** 子文件夹可集中用于在营销策划内执行流程所需的工作流：任务通知、库存管理、成本计算等。

![](assets/campaign-processes-wf.png)


>[!NOTE]
>
>随每个模块一起安装的技术工作流列表可在中找到 [专用部分](technical-workflows.md).

您可以在中创建其他技术工作流 **[!UICONTROL Administration > Production > Technical workflows]** 树结构的节点。 但是，此过程是为专家用户保留的。

提供的活动与定位工作流相同。 [了解详情](targeting-workflows.md)

此部分中详述的工作流随其他Adobe Campaign内置包一起安装。 这些软件包和相关技术工作流取决于您的许可协议。

默认情况下，技术工作流在以下节点的子文件夹中可用： **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**.

请注意，技术工作流只能由具有管理权限的操作员启动和修改。

>[!NOTE]
>
>默认情况下，与消息中心加载项相关的技术工作流在以下位置提供： **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Message Center]** > **[!UICONTROL Technical workflows]** 节点。

请参阅此了解如何监测技术工作流 [专用部分](monitor-technical-workflows.md).


## 技术工作流的列表 {#list-technical-workflows}

| 技术工作流 | 包 | 说明 |
|------|--------|-----------|
| **别名清理** (aliasCleansing) | 默认安装 | 此工作流可标准化枚举值。 默认情况下，此工作流于每日凌晨3点触发。 |
| **计费** （计费） | 默认安装 | 此工作流会通过电子邮件将系统活动报告发送到“billing”操作员。 它会在每月25日在营销实例上触发。 |
| **营销活动作业** (operationMgt) | 默认安装 | 此工作流用于管理营销活动（启动项定位、文件提取等）的作业。 它还创建与循环和定期活动相关的工作流。 |
| **为HeatMap服务收集数据** (collectDataHeatMapService) | 默认安装 | 此工作流可检索HeatMap服务所需的数据。 |
| **收集隐私请求** (collectPrivacyRequests) | 隐私数据保护规定 | 此工作流会生成存储在Adobe Campaign中的收件人数据，并在隐私请求屏幕中提供下载。 |
| **成本计算** (budgetMgt) | 默认安装 | 此工作流会开始计算预算、计划、方案、营销策划、投放和任务中的费用和成本行。 |
| **数据库清理** （清理） | 默认安装 | 此工作流是数据库维护工作流：它根据统计和流程进行不同的计算，并根据部署助手中定义的配置从数据库中删除过时的数据。 默认情况下，此工作流于每日凌晨4点触发。 |
| **删除被阻止的LINE用户** (deleteBlockedLineUsersV2) | LINE 渠道 | 此工作流可确保在LINE V2用户阻止LINE官方帐户180天后删除这些用户数据。 |
| **删除隐私请求数据** (deletePrivacyRequestsData) | 隐私数据保护规定 | 此工作流会删除存储在Adobe Campaign中的收件人数据。 |
| **投放指标** (deliveryIndicator) | 中间源平台 | 此工作流用于更新投放的投放跟踪指示器。 默认情况下，此工作流每小时触发一次。 |
| **分布式营销流程** (centralLocalmgt) | 中央/本地营销（分布式营销） | 此工作流开始处理与使用分布式营销模块相关。 它启动本地营销活动的创建，并管理与订单和营销活动包可用性相关的通知。 |
| **事件清除** (webAnalyticsPurgeWebEvents) | 网站分析连接器 | 通过此工作流，可根据生命周期字段中配置的时段，从数据库字段删除每个事件。 |
| **将受众导出到Adobe Experience Cloud** (exportSharedAudience) | 与Adobe Experience Cloud集成 | 此工作流将受众导出为共享受众/区段。 您可在所用的不同 Adobe Experience Cloud 解决方案中使用这些受众。 |
| **预测** （预测） | 投放 | 此工作流会分析保存在临时日历中的投放（创建临时日志）。 默认情况下，此工作流于每日凌晨1点触发。 |
| **完全聚合计算(propositionrcp cube)** (agg_nmspropositionrcp_full) | 优惠引擎（交互） | 此工作流可更新优惠建议多维数据集的完全聚合。 默认情况下，此工作流于每日早上6点触发。 此聚合捕获以下维度：渠道、投放、营销选件和日期。 优惠建议多维数据集随后用于根据优惠生成报告。 请在[此部分](../../v8/reporting/gs-cubes.md)中了解有关多维数据集的更多信息。 |
| **已转换联系人的标识** (webAnalyticsFindConverted) | 网站分析连接器 | 此工作流会为再营销活动后完成购买的网站访客编制索引。 通过此工作流恢复的数据可在再营销效率报表中进行访问（请参阅此页面）。 |
| **从Adobe Experience Cloud导入受众** (importSharedAudience) | 与Adobe Experience Cloud集成 | 利用此工作流，可将受众/区段从不同的Adobe Experience Cloud解决方案导入到Adobe Campaign中。 |
| **营销活动中投放的作业** (deliveryMgt) | 默认安装 | 此工作流会触发已批准的投放，并开始后处理外部投放的服务提供程序。 它还会发送批准通知和提醒。 |
| **服务提供商上的作业** (supplierMgt) | 默认安装 | 在投放获得批准后，此工作流将开始处理提供商（通过电子邮件发送到路由器并进行后处理）。 |
| **MID到LineUserID迁移** (MIDToUserIDMigration) | LINE 渠道 | 此工作流会生成LINE V2用户的ID，以便从LINE V1迁移到LINE V2。 |
| **消息中心 &lt;external_account_name>** (mcSynch_&lt;external_account_name>) | 事务性消息控制（消息中心 — 控制） | 此工作流： <ul><li>恢复操作处理的事件列表。</li><li>与NmsBroadLogMsg表同步，以恢复投放消息资格。</li><li>与NmsBroadLogMsg表的同步完成后，立即恢复事件投放日志。</li><li>与NmsTrackingUrl表同步，以恢复对投放URL的跟踪。</li><li>与NmsTrackingUrl表的同步完成后，立即恢复事件跟踪URL。</li><li>用于在发送投放后，每三小时恢复一次所有被隔离的电子邮件地址。</li></ul> |
| **MessageCenter完全聚合计算** (agg_messageCenter_full) | 事务性消息控制（消息中心 — 控制） | 此工作流会更新消息中心多维数据集的完全聚合。 默认情况下，此工作流于每日凌晨3点触发。 此聚合捕获以下维度：渠道、日期、状态和事件类型。 然后，使用消息中心多维数据集根据事件生成报告。 您可以在中了解关于多维数据集的更多信息  |
| **中间源（投放计数器）** (defaultMidSourcingDlv) | 传输到中间源 | 此工作流收集中间源服务器上投放的计数信息。 计数信息包括常规投放指标，例如已发送的投放数量等。 不包括打开次数等跟踪信息。 默认情况下，每10分钟触发一次。 |
| **中间源（投放日志）** (defaultMidSourcingLog) | 传输到中间源 | 此工作流在中间源服务器上收集投放日志。 默认情况下，每小时触发一次。 |
| **NMAC选择退出管理** (mobileAppOptOutMgt) | 移动应用程序渠道（推送） | 此工作流可更新移动设备上的取消订阅通知。 从凌晨1点到午夜，每6小时触发一次。 |
| **优惠通知** (offerMgt) | 默认安装 | 此工作流可将已批准的优惠部署到在线环境中，以及优惠目录中包含的每个类别。 |
| **暂停的工作流清理** (cleanupPausedWorkflows) | 默认安装 | 此工作流会分析严重性设置为正常的已暂停工作流，并在暂停时间过长时触发警告和通知。 一个月后，暂停的技术工作流将无条件停止。 默认情况下，此工作流于每周一凌晨5点触发。 有关更多信息，请参阅 [处理暂停的工作流](monitor-workflow-execution.md#handling-of-paused-workflows). |
| **隐私请求清理** (cleanupPrivacyRequest) | 隐私数据保护规定 | 此工作流会清除90天以前的访问请求文件。 |
| **处理批次事件** (batchEventsProcessing) | 事务性消息执行（消息中心 — 执行） | 利用此工作流，可将批量事件先放入队列中，然后再与消息模板关联。 |
| **处理实时事件** (rtEventsProcessing) | 事务性消息执行（消息中心 — 执行） | 通过此工作流，在将实时事件与消息模板关联之前，您可以将实时事件放入队列中。 |
| **建议同步** (propositionSynch) | 使用执行实例控制优惠引擎 | 此工作流可在营销实例和用于交互的执行实例之间同步建议。 |
| **Web事件的恢复** (webAnalyticsGetWebEvents) | 网站分析连接器 | 每小时，此工作流都会下载指定网站上Internet用户行为的区段，将其放入Adobe Campaign数据库并启动再营销工作流。 |
| **报告聚合** (reportingAggregates) | 投放 | 此工作流可更新报告中使用的聚合。 默认情况下，此工作流于每日凌晨2点触发。 |
| **发送指标和营销活动属性** (webAnalyticsSendMetrics) | 网站分析连接器 | 此工作流允许您通过Adobe® Analytics连接器，将电子邮件促销活动指标从Adobe Campaign发送到Adobe Experience Cloud Suite。 相关指标如下： Sent (iSent)、打开总数(iTotalRecipientOpen)、点击的收件人总数(iTotalRecipientClick)、错误(iError)、选择退出（选择退出）(iOptOut)。 |
| **库存：订单和警报** (stockMgt) | 默认安装 | 此工作流可启动订单行上的库存计算，并管理警告警报阈值。 |
| **跟踪** (跟踪 | 默认安装 | 此工作流执行跟踪信息的恢复和整合。 它还确保重新计算跟踪和投放统计数据，特别是消息中心归档工作流使用的统计数据。 默认情况下，每小时触发一次。 |
| **更新事件状态** (updateEventsStatus) | 事务性消息执行（消息中心 — 执行） | 利用此工作流，可为事件分配状态。 事件状态如下：<ul><li>挂起：事件在队列中。 尚未为其关联任何消息模板。</li><li>待处理投放：事件处于队列中，已为其关联消息模板，并且投放当前正在处理该模板。</li><li>已发送：此状态复制于投放日志。 这意味着投放已发送。</li><li>被投放忽略：此状态复制于投放日志。 这意味着投放已被忽略。</li><li>投放错误：此状态复制于投放日志。 这意味着投放失败。</li><li>未涵盖的事件：该事件未能与消息模板关联。 将不会重新处理该事件。</li></ul> |
| **可投放性更新** (deliverabilityUpdate) | 默认安装 | 安装可投放性监控（电子邮件可投放性）包后，此工作流将在夜间运行，并管理退回电子邮件鉴别规则以及域和MX的列表。 这要求在平台上打开HTTPS端口。 |
