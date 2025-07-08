---
product: campaign
title: 在Adobe Campaign中监控投放能力
description: 了解Adobe Campaign中有关可投放性监视的工具和准则
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 2%

---

# 监控您的可投放性{#monitoring-deliverability}

在下方，您将找到有关Adobe Campaign提供的各种监控工具的详细信息，以及有关利用Adobe Campaign提供的功能来监控平台可投放性的其他准则。

## 监控工具 {#monitoring-tools}

Adobe Campaign允许您访问下面列出的所有可投放性工具。

* [收件箱呈现报告](inbox-rendering.md)允许您预览主要电子邮件客户端上的邮件，以便扫描内容和信誉。

* **[!UICONTROL Delivery throughput]**&#x200B;报告提供给定时段内整个平台的吞吐量概览。 有关更多信息，请参阅[此小节](../reporting/global-reports.md#delivery-throughput)。
* 每个投放为不同的Internet服务提供商(ISP)生成广播统计报告。 其中显示了一些可能会影响您的可投放性的数据质量和信誉指标，包括以下数字：
   * **[!UICONTROL Hard bounces]**&#x200B;指示数据质量。 此数字应小于2%。
   * **[!UICONTROL Soft bounces]**&#x200B;指示信誉。 对于任何给定的ISP，此数字不应大于10%。

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* 更一般而言，[投放仪表板](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}授予您访问：
   * 投放摘要，显示发送的详细信息，成功发送、处理和发送的消息数；
   * 投放日志和历史记录，显示已排除的目标以及排除原因；
   * 跟踪日志，其中显示打开数和点击数等跟踪信息。

## 监测准则 {#monitoring-guidelines}

以下是有关可投放性监测的其他准则：

* 定期检查整个平台的[投放吞吐量](../reporting/global-reports.md#delivery-throughput)，以验证它是否与原始设置一致。
* 检查投放模板中是否正确设置了[重试](delivery-failures.md#retries)（重试期间为30分钟，重试次数超过20次）。
* 定期验证[退回](delivery-failures.md#bounce-mail-qualification)邮箱是否可访问，以及帐户是否即将过期。
* 检查可从[投放仪表板](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}访问的每个投放吞吐量，以确保其与投放内容的有效性一致（例如，“闪速销售”应以分钟而不是天投放）。 是一个关键工具，用于监测投放情况以及发送消息期间可能出现的问题。
* 使用[波次](configure-and-send.md#sending-using-multiple-waves)时，请验证每个波次在触发下一个波次之前是否有足够的时间完成。
* 检查错误数和新的[隔离](quarantines.md)与其他投放是否一致。
* 列入阻止列表请仔细查阅[投放日志](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#delivery-logs-and-history){target="_blank"}以详细检查突出显示的错误类型（、DNS问题、反垃圾邮件规则等）。
