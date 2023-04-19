---
title: 发送和监控事务型消息
description: 了解如何发送和监控事务型消息
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 2%

---

# 发送和监控事务型消息 {#delivery-execution}

## 发送消息{#send-transactional-msg}

扩充完成并将投放模板链接到事件后，将从执行实例发送投放。

>[!NOTE]
>
>事务型消息比任何其他投放具有优先级。

所有投放都分组在 **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** 文件夹。

默认情况下，这些文件夹会按提交月分类为子文件夹。 可以在消息模板属性中更改此设置。

## 监视消息 {#monitor-transactional-msg}

要监视事务型消息，请检查 [投放日志](send.md).

从执行实例发送的事务性投放通过技术工作流(**[!UICONTROL Message Center execution instance]**)每小时运行一次。

>[!NOTE]
>
>投放每周会根据最新事件更新而不是事件创建日期来累计事件。 因此，在从控制实例提取事务性消息传递投放日志时，与每个投放日志ID关联的投放ID可能会随着日志更新而随时间而改变（例如，当收到事件的入站退件时）。

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## 报告{#reporting-transactional-msg}

Adobe Campaign提供了多个报表，用于控制活动并顺利运行执行实例。

可以从 **[!UICONTROL Reports]** 选项卡 **控制实例**.

![](assets/mc-reports.png)

### 消息中心事件历史记录 {#history-events}

的 **[!UICONTROL Message Center event history]** 报表显示消息中心模块活动的概述，即处理和交付为事务型消息的事件数。

打开报表时，默认显示的信息与成功发送事务型消息的速率一致。 要查看更多级别，您可以打开各种节点并将光标放在相应的级别上以选择它。

您可以查看每个时间段中特定于每个事件类型的数据。 的 **[!UICONTROL Events]** 列对应于每个控制实例接收的事件数。 转换为个性化事务型消息的事件数在 **[!UICONTROL Sent]** 列。


### 消息中心处理时间 {#processing-time}

的 **[!UICONTROL Message Center processing time]** 报表显示与实时队列相关的主要指标。 此报表也可通过 **[!UICONTROL Monitoring]** 选项卡。

![](assets/mc-processing-time-report.png)

您可以选择显示全局统计信息或与特定执行实例相关的统计信息。 您还可以按渠道和特定时段过滤数据。

显示在 **[!UICONTROL Indicators over the period]** 部分会在选定的时段内计算：

* **[!UICONTROL Average queuing time]**:成功处理事件在消息中心花费的平均时间。 只考虑处理时间。
* **[!UICONTROL Average message sending time (s)]**:成功处理事件在消息中心花费的平均时间。 只考虑mta提交时间。
* **[!UICONTROL Average processing time (s)]**:成功处理事件在消息中心花费的平均时间。 计算时会考虑处理时间和mta发送时间。
* **[!UICONTROL Maximum number of queued events]**:消息中心队列中在任何给定时刻存在的最大事件数。
* **[!UICONTROL Minimum number of queued events]**:消息中心队列中在任何给定时刻存在的最小事件数。
* **[!UICONTROL Average number of queued events]**:消息中心队列在任何给定时刻存在的平均事件数。

>[!NOTE]
>
>可以在Adobe Campaign部署向导中配置警告（橙色）和警报（红色）指示器阈值。 请参阅 [监视阈值](#thresholds).



### 消息中心服务级别 {#service-level}

的 **[!UICONTROL Message Center service level]** 报表显示与事务型消息相关的投放统计信息以及错误划分。 您可以单击错误类型以显示其详细信息。

此报表也可通过 **[!UICONTROL Monitoring]** 选项卡。

您可以选择显示全局统计信息或与特定执行实例相关的统计信息。 您还可以按渠道和特定时段过滤数据。

显示在 **[!UICONTROL Indicators over the period]** 部分会在选定的时段内计算：

* **[!UICONTROL Incoming (throughput event/h)]**:在消息中心队列中输入的平均每小时事件数。
* **[!UICONTROL Incoming (event vol)]**:在消息中心队列中输入的事件数。
* **[!UICONTROL Outgoing (throughput msg/h)]**:成功传出消息中心事件（由投放发送）的平均每小时数。
* **[!UICONTROL Outgoing (msg vol)]**:成功传出消息中心事件的数量（由投放发送）。
* **[!UICONTROL Average sending time (seconds)]**:成功处理事件的消息中心平均逗留时间。 计算时会考虑处理时间和mta发送时间。
* **[!UICONTROL Error rate]**:与进入消息中心队列的事件数相比，出现错误的事件数。 考虑了以下错误：路由错误、过期事件（队列中的事件过长）、投放错误，被投放忽略（隔离等）。

>[!NOTE]
>
>可以在Adobe Campaign部署向导中配置警告（橙色）和警报（红色）指示器阈值。 请参阅 [监视阈值](#thresholds).

### 监测阈值 {#thresholds}

您可以为 **消息中心服务级别** 和 **消息中心处理时间** 报表。

为此请执行以下操作步骤：

1. 在 **执行实例**，然后浏览到 **[!UICONTROL Message Center]** 页面。
1. 使用箭头更改阈值。

   ![](assets/mc-thresholds.png)
