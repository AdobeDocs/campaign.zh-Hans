---
product: campaign
title: 在Adobe Campaign中监控投放能力
description: 了解Adobe Campaign中有关可投放性监视的工具和准则
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# 监控您的可投放性{#monitoring-deliverability}

在下方，您将找到有关Adobe Campaign提供的各种监控工具的详细信息，以及有关利用Adobe Campaign提供的功能来监控平台可投放性的其他准则。

## 监控工具 {#monitoring-tools}

通过Adobe Campaign，您可以访问下面列出的可投放性工具。

### 收件箱呈现 {#inbox-rendering-tool}

[收件箱呈现报告](inbox-rendering.md)允许您预览主要电子邮件客户端上的邮件，以便扫描内容和信誉。

### 投放吞吐量 {#throughput-reports}

**[!UICONTROL Delivery throughput]**&#x200B;报告提供给定时段内整个平台的吞吐量概览。 有关更多信息，请参阅[此小节](../reporting/global-reports.md#delivery-throughput)。

### 广播统计信息 {#broadcast-statistics}

每个投放为不同的Internet服务提供商(ISP)生成广播统计报告。 其中显示了一些可能会影响您的可投放性的数据质量和信誉指标，包括以下数字：

**[!UICONTROL Hard bounces]**&#x200B;指示数据质量。 此数字应小于2%。

**[!UICONTROL Soft bounces]**&#x200B;指示信誉。 对于任何给定的ISP，此数字不应大于10%。

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### 投放仪表板 {#delivery-dashboard-monitoring}

更一般而言，[投放仪表板](delivery-dashboard.md)授予您访问：

投放摘要，显示发送的详细信息，以及成功发送、处理和发送的消息数。

投放日志和历史记录，其中显示了已排除的目标以及排除原因。

跟踪日志，显示打开和点击量等跟踪信息。

### SpamAssassin测试 {#spam-testing}

使用[SpamAssassin](spamassassin.md)测试您的电子邮件内容并为其评分，以确定邮件在接收时是否面临被反垃圾邮件工具视为垃圾邮件的风险。

### 控制面板 {#control-panel-monitoring}

>[!NOTE]
>
>控制面板适用于Campaign v8托管云服务用户。 了解有关[控制面板](../config/self-service.md)的更多信息。

Campaign [控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans){target="_blank"}提供可投放性的监视功能，包括子域和证书管理、活动配置文件监视以及投放吞吐量和延迟量度。

## 监测准则 {#monitoring-guidelines}

以下是有关可投放性监测的其他准则：

### 平台吞吐量监控

定期检查整个平台的[投放吞吐量](../reporting/global-reports.md#delivery-throughput)，以验证它是否与原始设置一致。

### 重试配置

检查投放模板中是否正确设置了[重试](delivery-failures.md#retries)（重试期间为30分钟，重试次数超过20次）。

### 退回邮箱验证

定期验证[退回](delivery-failures.md#bounce-mail-qualification)邮箱是否可访问，以及帐户是否即将过期。

### 投放性能检查

检查可从[投放仪表板](delivery-dashboard.md)访问的每个投放吞吐量，以确保其与投放内容的有效性一致（例如，“闪速销售”应以分钟而不是天投放）。

### 波次计时验证

使用[波次](configure-and-send.md#sending-using-multiple-waves)时，请验证每个波次在触发下一个波次之前是否有足够的时间完成。

### 隔离监测

检查错误数和新的[隔离](quarantines.md)与其他投放是否一致。

### 投放日志分析

列入阻止列表请仔细查阅[投放日志](delivery-dashboard.md#delivery-logs-and-history)以详细检查突出显示的错误类型（、DNS问题、反垃圾邮件规则等）。

## 相关主题

[Adobe可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}提供了有关可投放性策略、定义、指标和最佳实践的综合性指导。

[什么是可投放性](about-deliverability.md)介绍了关键可投放性概念以及如何提高Campaign中的可投放性。

[投放失败和退回](delivery-failures.md)描述了不同类型的投放失败、Campaign如何处理它们，并包括常见问题的故障排除指导。

[隔离管理](quarantines.md)说明Campaign如何管理隔离地址以保护您的发送信誉。

[控制消息内容](control-message-content.md)提供了有关如何确保内容已针对可投放性进行了优化的指导。
