---
title: 发送和监测事务性消息
description: 了解如何发送和监控事务性消息
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 2%

---

# 发送和监测事务性消息 {#delivery-execution}

## 发送消息{#send-transactional-msg}

扩充完成并将投放模板链接到事件后，将从执行实例发送投放。

>[!NOTE]
>
>与任何其他投放相比，事务型消息具有优先权。

所有投放都分组到&#x200B;**[!UICONTROL Administration > Production > Message Center > Default > Deliveries]**&#x200B;文件夹中。

默认情况下，它们按投放月份分类为子文件夹。 可以在消息模板属性中更改此设置。

## 监测消息 {#monitor-transactional-msg}

要监视事务性消息，请检查[投放日志](send.md)。

通过每小时运行一次的技术工作流(**[!UICONTROL Message Center execution instance]**)，将从执行实例发送的事务性投放同步回控制实例。

>[!NOTE]
>
>投放每周根据最新的事件更新而不是根据事件创建日期来累计事件。 因此，在从控制实例提取事务性消息投放日志时，与每个投放日志ID关联的投放ID可能会随着日志的更新（例如，当收到事件的入站退回时）而随着时间的推移而改变。

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## 报告{#reporting-transactional-msg}

Adobe Campaign提供了多个报表，可让您控制活动并顺利运行执行实例。

可以从&#x200B;**控件实例**&#x200B;的&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡访问这些消息中心报告。

![](assets/mc-reports.png)

### 消息中心事件历史记录 {#history-events}

**[!UICONTROL Message Center event history]**&#x200B;报表显示消息中心模块活动的概览，即作为事务型消息处理和投放的事件数。

在打开报告时，默认显示的信息与成功发送事务型消息的速率一致。 要查看更多级别，您可以打开各种节点，并将光标放在适当的级别上以将其选定。

您可以查看特定于每个事件类型、每个时段的数据。 **[!UICONTROL Events]**&#x200B;列对应于每个控件实例接收的事件数。 在&#x200B;**[!UICONTROL Sent]**&#x200B;列中详细列出了转换为个性化事务型消息的事件数。


### 消息中心处理时间 {#processing-time}

**[!UICONTROL Message Center processing time]**&#x200B;报告显示与实时队列相关的主要指标。 还可以通过控件实例上的&#x200B;**[!UICONTROL Monitoring]**&#x200B;选项卡访问此报告。

![](assets/mc-processing-time-report.png)

您可以选择显示全局统计信息或与特定执行实例相关的统计信息。 您还可以按渠道和特定时段过滤数据。

**[!UICONTROL Indicators over the period]**&#x200B;部分中显示的指示符是在所选时段内计算的：

* **[!UICONTROL Average queuing time]**：成功处理在消息中心花费的事件的平均时间。 仅考虑处理时间。
* **[!UICONTROL Average message sending time (s)]**：成功处理在消息中心花费的事件的平均时间。 只考虑mta投放时间。
* **[!UICONTROL Average processing time (s)]**：成功处理在消息中心花费的事件的平均时间。 该计算将处理时间和mta发送时间考虑在内。
* **[!UICONTROL Maximum number of queued events]**：在任何给定时刻消息中心队列中存在的最大事件数。
* **[!UICONTROL Minimum number of queued events]**：在任何给定时刻消息中心队列中存在的最小事件数。
* **[!UICONTROL Average number of queued events]**：在任何给定时刻消息中心队列中存在的平均事件数。

>[!NOTE]
>
>可以在Adobe Campaign部署向导中配置警告（橙色）和警报（红色）指示器阈值。 请参阅[监视器阈值](#thresholds)。



### 消息中心服务级别 {#service-level}

**[!UICONTROL Message Center service level]**&#x200B;报告显示与事务性消息相关的投放统计信息以及错误细分。 您可以单击错误类型以显示其详细信息。

还可以通过控件实例上的&#x200B;**[!UICONTROL Monitoring]**&#x200B;选项卡访问此报告。

您可以选择显示全局统计信息或与特定执行实例相关的统计信息。 您还可以按渠道和特定时段过滤数据。

**[!UICONTROL Indicators over the period]**&#x200B;部分中显示的指示符是在所选时段内计算的：

* **[!UICONTROL Incoming (throughput event/h)]**：在消息中心队列中输入的平均每小时事件数。
* **[!UICONTROL Incoming (event vol)]**：在消息中心队列中输入的事件数。
* **[!UICONTROL Outgoing (throughput msg/h)]**：成功的传出消息中心事件的平均小时数（由投放发送）。
* **[!UICONTROL Outgoing (msg vol)]**：成功的传出消息中心事件数（由投放发送）。
* **[!UICONTROL Average sending time (seconds)]**：成功处理事件的消息中心平均逗留时间。 该计算将处理时间和mta发送时间考虑在内。
* **[!UICONTROL Error rate]**：错误事件数与进入消息中心队列的事件数之比。 考虑以下错误：路由错误、过期事件（队列中的事件过长）、投放错误、被投放忽略（隔离等）。

>[!NOTE]
>
>可以在Adobe Campaign部署向导中配置警告（橙色）和警报（红色）指示器阈值。 请参阅[监视器阈值](#thresholds)。

### 监测阈值 {#thresholds}

您可以配置出现在&#x200B;**消息中心服务级别**&#x200B;和&#x200B;**消息中心处理时间**&#x200B;报告中的指示器的警告（橙色）和警报（红色）阈值。

为此请执行以下操作步骤：

1. 在&#x200B;**执行实例**&#x200B;上打开部署向导，并浏览到&#x200B;**[!UICONTROL Message Center]**&#x200B;页。
1. 使用箭头可更改阈值。

   ![](assets/mc-thresholds.png)
