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
source-git-commit: 369ddafcc64fa418a479ab03092d3475f1c811b2
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# 技术工作流和数据复制

## 技术工作流

Adobe Campaign附带一组内置技术工作流。 技术工作流在服务器上定期执行进程或作业。

这些工作流对投放日志库执行维护操作，利用数据库中的跟踪信息，创建循环活动等。

:arrow_upper_right:技术工作流的完整列表详见[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

除了这些技术工作流之外，活动 v8还依赖特定技术工作流来管理[数据复制](#data-replication)。

* **[!UICONTROL Replicate Reference tables]**
此工作流会自动复制需要在活动本地数据库(Postgres)和云数据库()上显示的参考[!DNL Snowflake]表。计划每天每小时执行一次。 如果存在&#x200B;**lastModified**&#x200B;字段，则复制会以增量方式进行，否则将复制整个表。 以下数组中表的顺序是复制工作流使用的顺序。
* **[!UICONTROL Replicate Staging data]**
此工作流将复制统一调用的暂存数据。计划每天每小时执行一次。
* **[!UICONTROL Deploy FFDA immediately]**\
   此工作流会立即部署到云数据库。
* **[!UICONTROL Replicate FFDA data immediately]**
此工作流将复制给定外部帐户的XS数据。

这些技术工作流可从活动 Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]**&#x200B;节点中访问。

**我们应该添加这个吗？https://wiki.corp.adobe.com/display/neolane/Full+FDA+%3A%3A+Replication+strategy**


**相关主题**

:arrow_upper_right:了解如何开始使用[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)中的工作流

：灯泡：访问[此部分](../dev/datamodel-best-practices.md#data-retention)中的数据保留期


## 数据复制{#data-replication}

表将通过上面描述的专用工作流从活动数据库复制到[!DNL Snowflake]云数据库。

复制策略基于表的大小。 将复制某些表。 一些表格将实时复制，而其他表格将按小时复制。 某些表在替换其他表时将具有增量更新。

| 命名空间 | 表 | 工作流复制 | 实时复制 |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| **XTK** | xtk:enum<br>xtk:enumValue<br>xtk:enumAlias<br>xtk:folder<br>xtk:formRendering<br>xtk:operator<br>xtk:group<br>xtk:olapCube<br>xtk:xtk<br>xtk:olapMeasure<br>xtk:dictionaryString<br><br> | 是（增量） | 是 |
| **XTK** | xtk:opsecurity<br>xtk:rights<br>xtk:operatorGroup<br>xtk:reportHistory<br>xtk:reportRights | 是（完整） | 是 |
| **NMS** | nms:budget<br>nms:项目<br>nms:operation<br>nms:plan<br>nms:typologyRule<br>nms:typology<br>nms:extAccount<br>nms:deliveryMapping<br>nms:投放（即时复制）<br>nms:seedMember<br>nms:seedMembernms:webApp<br>nms:trackingUrl（即时复制）<br>nms:service<br>nms:offerEnv<br>nms:offerCategory<br>nms:offerSpace<br>:优惠<br>nms offerView<br>nms:收件人（增量？）<br>nms:<br>groupnms:<br>dlvExclusionnms:stock | 是（增量） | 是 |
| **NMS** | nms:country<br>nms:localOrgUnit<br>nms:state<br>nms:suppressionAddress<br>nms:suppressionDomain<br>nms:类别<br>nms:trackingUrlInfo<br>nms:webTrackingLog<br>nms:mobip<br>nnms:budgetCategory<br>nms:costType<br>nms:costCenter<br>nms:costStructure<br>nms:stockLine<br>nms:expenseLine<br>nms:costLine | 是（完整） | 是 |
| **NMS** | nms:address<br>nms:userAgent<br>nms:userAgentReject<br>nms:userAgentStats<br>nms:broadLogMsg<br>nms:broadLog<br>nms:trackingLog<br>nms:deleliveryLogSta7/>nmsLogStats<br>nms订阅<br>nms:compation<br>nms:rcpGrpRel<br>nms:broadLogRcp<br>nms:excludeLogRcp<br>nms:trackingLogRcp<br>nms:compatitionRcp<br>nms:localValidationRcp<br>nms:访客<br>nms:broadLogVisitor<br>nms:trackingLogVisitor<br>nms:compationVisitor<br>nms:webAppLogRcp<br>nms:appSubscriptionRcp<br>nms:broadLogAppSubRcp<br>nms:excludeLogAppSubRcp<br>nms:trackingLogAppSubRcp<br>nms:eventHistoa25/>nms:broadLogEventHisto<br>nms:trackingLogEventHisto<br>nms:订阅<br>nms:subHisto<br>nms:trackingStats(仅Snowflake使用)<br>nms:nms广播(仅限Snowflake使用)<br>nms:tmpBroadcastExclusion(仅限Snowflake使用)<br>nms:tmpBroadcastPaper(仅限Snowflake使用)<br> | 否 | 否 |

