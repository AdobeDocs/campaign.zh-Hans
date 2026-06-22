---
title: Campaign监控概述
description: 了解如何监测投放、工作流和您的活动实例
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6cf587ecc9cc1e4cf9b3de0d2067e0c4562afe01
workflow-type: tm+mt
source-wordcount: 2206
ht-degree: 1%

---

# Campaign监控概述 {#monitor-campaign}

Adobe Campaign提供了各个级别的可见性 — 从单个消息是否已投放、工作流失败的原因到实例剩余的数据库容量。 此页面列出了所有监控功能，以便您了解在出现需要关注的问题时应该查看的位置。

>[!NOTE]
>
>作为Campaign管理员，您还可以使用[Campaign控制面板](#control-panel)来监视实例、管理性能以及配置具有自助服务功能的设置。

>[!TIP]
>
>**不确定从何处开始？**
>
>- 营销人员正在检查营销活动→ [监控您的投放](#monitor-deliveries)
>- 针对[监控工作流](#monitor-workflows)→工作流疑难解答
>- 管理员检查实例运行状况→ [监视您的实例](#monitor-instance)

## 监测投放 {#monitor-deliveries}

在发送后监测投放是确保营销活动有效并接触到客户的关键步骤。 发送投放后，您可以在投放仪表板中监控其状态并跟踪关键量度。 仪表板提供对投放日志、排除日志、跟踪日志和其他监视功能的访问，可帮助您分析所有渠道的投放性能。

>[!NOTE]
>
>**新加入促销活动？** 投放仪表板是您的主要日常屏幕。 打开任何已发送的投放，单击&#x200B;**日志**&#x200B;选项卡，您将看到哪些收件人已收到邮件、哪些收件人已被排除以及为什么收到邮件，以及哪些人点击或打开了邮件。

**电子邮件投放** — 监视电子邮件投放状态、跟踪关键量度并访问详细日志。 了解有关[在Campaign UI中监视投放](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-dashboard)、[投放状态](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-statuses)和[电子邮件投放监视](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/emails/send#email-monitoring)的详细信息。

**短信投放** — 跟踪SMS投放状态并在SMS投放仪表板中监视关键量度。 了解有关[SMS监控](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/sms/sms-monitor)的更多信息。

**推送通知** — 监视推送通知投放，以确保它们能够有效地到达您的移动应用程序用户。 了解有关[推送通知监视](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/push/push#push-test)的更多信息。

**事务性消息** — 对于由事件触发的消息，监视事件处理状态、消息执行和投放状态。 了解有关[事务性消息监视](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages)的详细信息。

**投放失败** — 了解投放失败的原因对于维护干净的数据库并确保良好的投放率至关重要。 投放失败分为三种类型 — 了解这些差异有助于您决定要采取的操作：

| 失败类型 | 它的含义 | 营销活动的功能 |
| --- | --- | --- |
| **硬退回** | 地址永久无效（不存在，域未知） | 联系人会被自动隔离 — 在未来的投放中不会将其设为目标 |
| **软退回** | 临时问题（邮箱已满，服务器暂时不可用） | Campaign会在配置的时间段内自动重试 |
| **已忽略** | 地址在发送前已被隔离或阻止列表 | 未尝试；与退回次数分开计数 |

了解有关[投放失败和隔离](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-failures)的更多信息。

## 监测投放能力 {#monitor-deliverability}

>[!NOTE]
>
>计为“已投放”的消息表示接收服务器已接受该消息，但不保证收件箱的位置。 可投放性监视可告知您发送域身份验证、IP信誉和电子邮件内容是否符合收件箱提供商标准。

可投放性监测帮助您确保邮件到达收件人的收件箱并避免垃圾邮件过滤器。 Adobe Campaign提供了多种内置工具来监控和改进可投放性，包括投放报告、收件箱呈现、SpamAssassin测试和广播统计数据。 遵循可投放性最佳实践（如维护干净的电子邮件列表、监控发件人信誉和验证发送域）对于保持良好的可投放性比率至关重要。

了解有关[可投放性监视工具](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability)和[可投放性最佳实践](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability)的更多信息。

## 监测工作流 {#monitor-workflows}

工作流对于自动化营销活动和数据处理至关重要。 监视工作流执行可帮助您：

- 确保工作流成功完成
- 识别错误并排除错误
- 优化工作流性能

>[!TIP]
>
>如果工作流显示&#x200B;**失败**&#x200B;状态，请将其打开，右键单击红色活动，然后选择&#x200B;**显示日志**。 错误消息准确地指明了哪里出错了，以及在哪条记录上。

### 工作流监控功能 {#workflow-monitoring}

**监视以下工作流元素：**

**工作流执行状态** — 跟踪工作流是正在运行、已暂停、失败还是已完成。 [了解有关工作流执行的更多信息](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**活动执行日志** — 访问每个工作流活动的详细日志，以解决问题并优化性能。

**工作流热图** — 在实例中同时运行的所有工作流的视觉概览。 使用它可以确定峰值负载期间，发现占用过多资源的工作流，并规划计划以避免执行冲突。 仅适用于Campaign管理员。 [了解有关工作流热图的更多信息](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**工作流历史记录** — 跟踪一段时间内的所有工作流执行和修改，以了解工作流行为和性能。

## 监控实例 {#monitor-instance}

实例监控帮助您确保Adobe Campaign环境的运行状况和性能。 对于Campaign v8托管云服务，Adobe还代表您监控和管理基础架构。 了解有关[Adobe管理的监视](#adobe-cloud-monitoring)的详细信息。

### 审核记录 {#audit-trail}

利用审核记录自助服务界面，可监控在Adobe Campaign实例中所做的更改。 审核记录可实时捕获实例中发生的操作和事件的全面列表。

**使用审核记录：**

- **跟踪组件更改**：监视您的工作流、架构、选项和其他组件发生了什么情况
- **确定更改者**：查看上次更新特定元素的人以及时间
- **了解用户操作**：查看用户在实例中的操作以进行故障排除或审核
- **维护合规性**：跟踪所有配置更改以实现合规性和安全性

审核记录可通过Campaign客户端控制台访问，并提供有关用户所执行操作的详细信息。

了解有关[审核记录](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/audit-trail)的详细信息

### 性能监控 {#performance-monitoring}

Campaign v8提供了多种监视功能来跟踪实例性能并确保实现最佳操作：

**数据库监视** — 通过控制面板监视数据库的使用情况和容量，以确保最佳性能和存储管理。 [了解有关数据库监视的详细信息](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**活动配置文件监控** — 根据您的合同限制跟踪活动配置文件使用情况，以保持合规性并优化资源分配。 [了解有关活动用户档案的详细信息](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**工作流监视** — 监视工作流执行状态以识别长时间运行的工作流，并确保所有技术工作流都正常运行。 [了解有关技术工作流的详细信息](#technical-workflows)

**投放吞吐量和延迟** — 通过控制面板跟踪交易通信的投放吞吐量（每小时发送的消息）和延迟。 [了解有关吞吐量监视的详细信息](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>对于Campaign v8托管云服务，服务器基础架构（CPU、内存、磁盘）由Adobe进行监视和管理。 了解有关[Adobe管理的监视](#adobe-cloud-monitoring)的详细信息。

### Adobe管理的监控 {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services通过灵活的云基础架构为满足苛刻的客户体验交付需求提供关键任务支持。 这使组织能够启动、监控和优化客户体验，而无需自己管理或操作Campaign基础架构。

Adobe监控您的Campaign Cloud Services环境，通过检测技术问题并提供有关性能和持续项目的持续反馈，帮助管理各种问题并将中断降至最低。

**Adobe如何响应**

Adobe全天候监控Campaign网络上的所有关键网络设备，并在需要修复或升级时接收来自监控系统的通知。 检测到问题时，系统会使用自动重新启动和自动启动机制来尝试修复。 如果系统无法自行修复，Adobe电话技术支持会介入，根据预定义的警报Runbook执行故障排除。

>[!NOTE]
>
>Adobe执行的某些监视操作显示在&#x200B;**campaign-loginmonitor**&#x200B;用户下的Campaign日志中。

除了Adobe的内部监控之外，您还可以直接通过Campaign客户端控制台或[Campaign控制面板](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service)访问监控功能。 通过控制面板，您可以订阅有关实例的实时警报，并针对已识别的事件（例如，临近过期的SSL证书）接收建议的修正步骤。

**正在监视分类**

Adobe跨三个层监控您的环境：

| 层 | 组 | 潜在业务影响 |
| --- | --- | --- |
| **第1层：基础架构** | 数据库空间耗尽 | 性能问题，包括无法登录、运行批量投放或执行查询 |
| **第1层：基础架构** | 数据库可用性 | 用户和服务可能无法使用系统 |
| **第1层：基础架构** | 数据库过载（突发平衡） | 性能问题，包括无法登录、运行批量投放或执行查询 |
| **第1层：基础架构** | 数据库序列和交易ID耗尽 | 无法创建新工作流、投放或发送批量电子邮件 |
| **第1层：基础架构** | SFTP存储 | 无法更新或检索SFTP服务器上的数据 |
| **第2层：平台和Web** | 登录 | 用户可能无法登录；计划活动和工作流程可能无法执行 |
| **第2层：平台和Web** | API锁定 | 用户或服务可能无法验证或执行操作 |
| **第2层：平台和Web** | Web | 无法创建与Campaign的新连接 |
| **第2层：平台和Web** | 数据中心网络 | 数据中心的用户存在性能问题或完全不可用 |
| **第3层：软件** | 投放跟踪 | 跟踪日志的处理不可用 |
| **第3层：软件** | inMail | 没有关于电子邮件投放错误和退回的反馈 |
| **第3层：软件** | 消息中心状态 | 无法发送任何事务性投放 |
| **第3层：软件** | MTA | 无法发送计划的和临时电子邮件投放 |
| **第3层：软件** | 工作流服务器状态 | 无法执行工作流 |
| **第3层：软件** | Web API可用性 | 无法处理HTTP请求或执行API调用 |
| **第3层：软件** | 入站交互 | 无法处理入站交互 |

>[!NOTE]
>
>Adobe Campaign Cloud Services基于多云策略构建，并提供在AWS和Azure上的部署。 由于供应商差异，AWS、Azure和其他数据中心部署中的监控功能有所不同。 除非另有说明，否则上表适用于托管在AWS上的Campaign Cloud Services客户。 另请注意，Adobe Campaign目前不会向客户公开由电话随叫随到工程使用的所有监控数据。

### 技术工作流 {#technical-workflows}

技术工作流是在后台运行以维护Campaign实例的基本流程。

**监测技术工作流是：**

- 按计划执行
- 成功完成，并且没有错误
- 正确处理数据

**要监视的关键技术工作流：**

| 工作流 | 用途 | 如果失败 |
| --- | --- | --- |
| **跟踪** | 处理电子邮件投放中的跟踪数据 | 单击并打开量度可在报表中停止更新 |
| **清理** | 删除旧数据和日志以保持数据库性能 | 数据库增长不受控制，查询和投放性能下降 |
| **可投放性更新** | 更新可投放性规则和垃圾邮件过滤模式 | 规则过时；筛选准确性可能会降低 |
| **数据库清理** | 清除旧的投放和跟踪日志 | 日志累积会随时间减慢查询和报告的速度 |

了解有关[技术工作流](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)的详细信息

### Campaign 控制面板 {#control-panel}

Campaign控制面板为管理员提供自助服务功能，以监控和管理Campaign实例。

| 监控类型 | 功能 |
| --- | --- |
| **性能** | 跟踪活动用户档案使用情况、监测数据库使用情况和容量、查看工作流执行状态、监测投放吞吐量和延迟 |
| **基础架构** | 监测SFTP存储容量，跟踪子域配置，监测SSL证书过期，管理IP允许列表 |
| **实例** | 查看内部版本和已安装的包，监视系统配置，管理授权的外部域 |

了解有关[控制面板](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service)和[控制面板性能监视](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)的更多信息

>[!NOTE]
>
>对于Campaign v8托管云服务，Adobe将监控和管理服务器基础架构、操作系统和应用程序层。 了解有关[Adobe管理的监视](#adobe-cloud-monitoring)的详细信息。 您可以使用本页和控制面板中所述的监视功能来监视实例性能、工作流和投放。

## 跟踪和报告 {#tracking-reporting}

### 消息跟踪 {#message-tracking}

跟踪收件人行为并衡量活动有效性：

- **打开次数**：跟踪收件人打开电子邮件的时间
- **点击次数**：监视收件人点击的链接
- **取消订阅**：跟踪选择退出请求
- **镜像页面查看次数**：查看浏览器中查看您电子邮件的收件人数量

了解有关[邮件跟踪](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/analytics/tracking/tracking)的更多信息

### 投放报告 {#delivery-reports}

Adobe Campaign提供了一组全面的报告来分析您的交付性能：

- **投放摘要**：发送、投放和失败概述
- **跟踪指标**：打开次数、点击次数和点进率
- **个URL和点击流**：您的投放中最受欢迎的链接
- **热门点击**：收件人点击电子邮件位置的可视化表示

了解有关[传递报告](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)的更多信息

### 全局报告 {#global-reports}

访问全局报告以分析所有活动和投放的表现：

- **投放吞吐量**：随时间发送的消息
- **无法投放项和退回**：失败投放的分析
- **用户活动**：打开、点击和取消订阅所有营销活动

了解有关[全局报告](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)的详细信息

## 相关主题 {#related-topics}

- [投放最佳实践](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/delivery-best-practices)
- [隔离管理](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/quarantines)
- [配置和发送投放](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [报告快速入门](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/gs-reporting)
