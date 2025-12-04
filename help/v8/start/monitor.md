---
title: Campaign监控概述
description: 了解如何监测投放、工作流和您的活动实例
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 2%

---

# Campaign监控概述 {#monitor-campaign}

Adobe Campaign提供了一整套功能来监控您的流程、交付和环境，以确保获得最佳性能并主动解决问题。

>[!NOTE]
>
>作为Campaign管理员，您还可以使用[Campaign控制面板](#control-panel)来监视实例、管理性能以及配置具有自助服务功能的设置。

## 监测投放 {#monitor-deliveries}

在发送后监测投放是确保营销活动有效并接触到客户的关键步骤。 发送投放后，您可以在投放仪表板中监控其状态并跟踪关键量度。 仪表板提供对投放日志、排除日志、跟踪日志和其他监视功能的访问，可帮助您分析所有渠道的投放性能。

**电子邮件投放** — 监视电子邮件投放状态、跟踪关键量度并访问详细日志。 了解有关[在Campaign UI中监视投放](../send/delivery-dashboard.md)、[投放状态](../send/delivery-statuses.md)和[电子邮件投放监视](../send/send.md#email-monitoring)的详细信息。

**短信投放** — 跟踪SMS投放状态并在SMS投放仪表板中监视关键量度。 了解有关[SMS监控](../send/sms/sms-monitor.md)的更多信息。

**推送通知** — 监视推送通知投放，以确保它们能够有效地到达您的移动应用程序用户。 了解有关[推送通知监视](../send/push.md#push-test)的更多信息。

**事务性消息** — 对于由事件触发的消息，监视事件处理状态、消息执行和投放状态。 了解有关[事务性消息监视](../send/delivery-execution.md#monitor-messages)的详细信息。

**投放失败** — 了解投放失败的原因对于维护干净的数据库并确保良好的投放率至关重要。 投放失败分为硬退回、软退回和忽略消息。 了解有关[投放失败和隔离](../send/delivery-failures.md)的更多信息。

## 监测投放能力 {#monitor-deliverability}

可投放性监测帮助您确保邮件到达收件人的收件箱并避免垃圾邮件过滤器。 Adobe Campaign提供了多种内置工具来监控和改进可投放性，包括投放报告、收件箱呈现、SpamAssassin测试和广播统计数据。 遵循可投放性最佳实践（如维护干净的电子邮件列表、监控发件人信誉和验证发送域）对于保持良好的可投放性比率至关重要。

了解有关[可投放性监视工具](../send/monitoring-deliverability.md)和[可投放性最佳实践](../send/about-deliverability.md)的更多信息。

## 监测工作流 {#monitor-workflows}

工作流对于自动化营销活动和数据处理至关重要。 监视工作流执行可帮助您：

* 确保工作流成功完成
* 识别错误并排除错误
* 优化工作流性能

### 工作流监控功能 {#workflow-monitoring}

**监视以下工作流元素：**

**工作流执行状态** — 跟踪工作流是正在运行、已暂停、失败还是已完成。 [了解有关工作流执行的更多信息](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

**活动执行日志** — 访问每个工作流活动的详细日志，以解决问题并优化性能。

**工作流热图** — 可视化工作流执行模式，识别瓶颈并监视并发工作流。 Campaign管理员可以使用工作流热图。 [了解有关工作流热图的更多信息](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=zh-Hans){target="_blank"}

**工作流历史记录** — 跟踪一段时间内的所有工作流执行和修改，以了解工作流行为和性能。

## 监控实例 {#monitor-instance}

实例监控帮助您确保Adobe Campaign环境的运行状况和性能。

### 审核记录 {#audit-trail}

利用审核记录自助服务界面，可监控在Adobe Campaign实例中所做的更改。 审核记录可实时捕获实例中发生的操作和事件的全面列表。

**使用审核记录：**

* **跟踪组件更改**：监视您的工作流、架构、选项和其他组件发生了什么情况
* **确定更改者**：查看上次更新特定元素的人以及时间
* **了解用户操作**：查看用户在实例中的操作以进行故障排除或审核
* **维护合规性**：跟踪所有配置更改以实现合规性和安全性

审核记录可通过Campaign客户端控制台访问，并提供有关用户所执行操作的详细信息。

了解有关[审核记录](../reporting/audit-trail.md)的详细信息

### 性能监控 {#performance-monitoring}

Campaign v8提供了多种监视功能来跟踪实例性能并确保实现最佳操作：

**数据库监视** — 通过控制面板监视数据库的使用情况和容量，以确保最佳性能和存储管理。 [了解有关数据库监视的详细信息](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**活动配置文件监控** — 根据您的合同限制跟踪活动配置文件使用情况，以保持合规性并优化资源分配。 [了解有关活动用户档案的详细信息](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}

**工作流监视** — 监视工作流执行状态以识别长时间运行的工作流，并确保所有技术工作流都正常运行。 [了解有关技术工作流的详细信息](#technical-workflows)

**投放吞吐量和延迟** — 通过控制面板跟踪交易通信的投放吞吐量（每小时发送的消息）和延迟。 [了解有关吞吐量监视的详细信息](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>对于Campaign v8托管云服务，服务器基础架构(CPU、内存、磁盘)由Adobe进行监视和管理。

### 技术工作流 {#technical-workflows}

技术工作流是在后台运行以维护Campaign实例的基本流程。

**监测技术工作流是：**

* 按计划执行
* 成功完成，并且没有错误
* 正确处理数据

**要监视的关键技术工作流：**

| 工作流 | 用途 |
|----------|---------|
| **跟踪** | 处理电子邮件投放中的跟踪数据 |
| **清理** | 删除旧数据和日志以保持数据库性能 |
| **可投放性更新** | 更新可投放性规则和垃圾邮件过滤模式 |
| **数据库清理** | 清除旧的投放和跟踪日志 |

了解有关[技术工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}的详细信息

### Campaign 控制面板 {#control-panel}

Campaign控制面板为管理员提供自助服务功能，以监控和管理Campaign实例。

| 监控类型 | 功能 |
|-----------------|--------------|
| **性能** | 跟踪活动用户档案使用情况、监测数据库使用情况和容量、查看工作流执行状态、监测投放吞吐量和延迟 |
| **基础架构** | 监测SFTP存储容量，跟踪子域配置，监测SSL证书过期，管理IP允许列表 |
| **实例** | 查看内部版本和已安装的包，监视系统配置，管理授权的外部域 |

了解有关[控制面板](../config/self-service.md)和[控制面板性能监视](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=zh-Hans){target="_blank"}的更多信息

>[!NOTE]
>
>对于Campaign v8托管云服务，Adobe将监控和管理服务器基础架构、操作系统和应用程序层。 您可以使用本页和控制面板中所述的监视功能来监视实例性能、工作流和投放。

## 跟踪和报告 {#tracking-reporting}

### 消息跟踪 {#message-tracking}

跟踪收件人行为并衡量活动有效性：

* **打开次数**：跟踪收件人打开电子邮件的时间
* **点击次数**：监视收件人点击的链接
* **取消订阅**：跟踪选择退出请求
* **镜像页面查看次数**：查看浏览器中查看您电子邮件的收件人数量

了解有关[邮件跟踪](../send/tracking.md)的更多信息

### 投放报告 {#delivery-reports}

Adobe Campaign提供了一组全面的报告来分析您的交付性能：

* **投放摘要**：发送、投放和失败概述
* **跟踪指标**：打开次数、点击次数和点进率
* **个URL和点击流**：您的投放中最受欢迎的链接
* **热门点击**：收件人点击电子邮件位置的可视化表示

了解有关[传递报告](../reporting/delivery-reports.md)的更多信息

### 全局报告 {#global-reports}

访问全局报告以分析所有活动和投放的表现：

* **投放吞吐量**：随时间发送的消息
* **无法投放项和退回**：失败投放的分析
* **用户活动**：打开、点击和取消订阅所有营销活动

了解有关[全局报告](../reporting/global-reports.md)的详细信息

## 相关主题 {#related-topics}

* [投放最佳实践](delivery-best-practices.md)
* [隔离管理](../send/quarantines.md)
* [配置和发送投放](../send/configure-and-send.md)
* [报告快速入门](../reporting/gs-reporting.md)

