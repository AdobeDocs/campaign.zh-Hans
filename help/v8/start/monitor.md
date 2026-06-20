---
title: Campaign监控概述
description: 了解如何监测投放、工作流和您的活动实例
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: e8438b85eec144e83b2660f9d66444c1a01863ab
workflow-type: tm+mt
source-wordcount: 2101
ht-degree: 2%

---

# Campaign监控概述 {#monitor-campaign}

Adobe Campaign提供了各个级别的可见性 — 从单个消息是否已投放、工作流失败的原因到实例剩余的数据库容量。 此页面列出了所有监控功能，以便您了解在出现需要关注的问题时应该查看的位置。 作为Campaign管理员，您还可以使用[Campaign控制面板](#control-panel)来监视实例、管理性能以及配置具有自助服务功能的设置。

>[!TIP]
>
>**不确定从何处开始？**
>
>- 营销人员正在检查营销活动→ [监控您的投放](#monitor-deliveries)
>- 针对[监控工作流](#monitor-workflows)→工作流疑难解答
>- 管理员检查实例运行状况→ [监视您的实例](#monitor-instance)

## 监测投放 {#monitor-deliveries}

在发送后监测投放是确保营销活动有效并接触到客户的关键步骤。 发送投放后，您可以跟踪其进度并从投放仪表板诊断问题。 通过仪表板，您可以访问您使用的每个渠道的投放日志、排除日志、跟踪日志和其他数据。

>[!NOTE]
>
>**新加入促销活动？** 投放仪表板是您的主要日常屏幕。 打开任何已发送的投放，单击&#x200B;**日志**&#x200B;选项卡，您将看到哪些收件人已收到邮件、哪些收件人已被排除以及为什么收到邮件，以及哪些人点击或打开了邮件。

**电子邮件投放** — 监视电子邮件投放状态、跟踪关键量度并访问详细日志。 了解有关[在Campaign UI中监视投放](../send/delivery-dashboard.md)、[投放状态](../send/delivery-statuses.md)和[电子邮件投放监视](../send/send.md#email-monitoring)的详细信息。

**短信投放** — 跟踪SMS投放状态并在SMS投放仪表板中监视关键量度。 了解有关[SMS监控](../send/sms/sms-monitor.md)的更多信息。

**推送通知** — 监视推送通知投放，以确保它们能够有效地到达您的移动应用程序用户。 了解有关[推送通知监视](../send/push.md#push-test)的更多信息。

**事务性消息** — 对于由事件触发的消息，监视事件处理状态、队列深度和执行结果。 了解有关[事务性消息监视](../send/delivery-execution.md#monitor-messages)的详细信息。

**投放失败** — 了解投放失败的原因对于维护干净的数据库和确保良好的投放率至关重要。 投放失败分为三种类型 — 了解这些差异有助于您决定要采取的操作：

| 失败类型 | 它的含义 | 营销活动的功能 |
| --- | --- | --- |
| **硬退回** | 地址永久无效（不存在，域未知） | 联系人会被自动隔离 — 在未来的投放中不会将其设为目标 |
| **软退回** | 临时问题（邮箱已满，服务器暂时不可用） | Campaign会在配置的时间段内自动重试 |
| **已忽略** | 地址在发送前已被隔离或阻止列表 | 未尝试；与退回次数分开计数 |

了解有关[投放失败和隔离](../send/delivery-failures.md)的更多信息。

## 监测投放能力 {#monitor-deliverability}

可投放性是衡量邮件成功到达收件人收件箱的程度，而不是被过滤为垃圾邮件或拒绝的程度。 Adobe Campaign提供了几个内置工具，可帮助您了解和提高收件箱放置率。

>[!NOTE]
>
>计为“已投放”的消息表示接收服务器已接受该消息，但不保证收件箱的位置。 可投放性监视可告知您发送域身份验证、IP信誉和电子邮件内容是否符合收件箱提供商标准。

Adobe Campaign提供了以下内置可投放性工具：

- **传递报告** — 显示一段时间的发送量、退件率和取消订阅的内置报告。
- **收件箱呈现** — 预览电子邮件在发送之前或之后在主要客户端(Gmail、Outlook、Apple Mail)中的显示方式。
- **SpamAssassin测试** — 根据常见的垃圾邮件过滤规则对电子邮件内容进行评分，以在投放前捕获问题。
- **广播统计信息** — 跨发送卷和IP信誉聚合投放数据。

遵循可投放性最佳实践（如维护干净的电子邮件列表、监控发件人信誉和验证发送域）对于保持良好的可投放性比率至关重要。

了解有关[可投放性监视工具](../send/monitoring-deliverability.md)和[可投放性最佳实践](../send/about-deliverability.md)的更多信息。

## 监测工作流 {#monitor-workflows}

工作流是营销自动化和数据处理的引擎。 监控这些活动可确保计划活动按预期完成，并在错误影响投放或数据质量之前捕获到错误。

>[!TIP]
>
>如果工作流显示&#x200B;**失败**&#x200B;状态，请将其打开，右键单击红色活动，然后选择&#x200B;**显示日志**。 错误消息准确地指明了哪里出错了，以及在哪条记录上。

### 工作流监控功能 {#workflow-monitoring}

**监视以下工作流元素：**

**工作流执行状态** — 跟踪工作流是正在运行、已暂停、失败还是已完成。 一眼即可发现卡住或长时间运行的工作流。 [了解有关工作流执行的更多信息](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

**活动执行日志** — 深入查看每个活动的日志，以了解每个步骤发生的情况 — 对于故障排除失败的过渡或意外的数据输出非常有用。

**工作流热图** — 在实例中同时运行的所有工作流的视觉概览。 使用它可以确定峰值负载期间，发现占用过多资源的工作流，并规划计划以避免执行冲突。 仅适用于Campaign管理员。 [了解有关工作流热图的更多信息](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=zh-Hans){target="_blank"}

**工作流历史记录** — 跟踪一段时间内的所有工作流执行和修改，以了解工作流行为和性能模式。

## 监控实例 {#monitor-instance}

实例监控涵盖了Campaign环境的运行状况 — 数据库容量、配置文件使用情况、吞吐量和基础架构。 对于Campaign v8托管云服务，Adobe会代表您监视和管理基础基础架构，但您可以通过客户端控制台和控制面板保持完全可见性。 了解有关[Adobe管理的监视](#adobe-cloud-monitoring)的详细信息。

### 审核记录 {#audit-trail}

通过审核记录自助服务界面，您可以监控在Adobe Campaign实例中所做的每项重大更改。 审核记录可实时捕获实例中发生的操作和事件的全面列表。

**使用审核记录：**

- **跟踪组件更改** — 监视您的工作流、架构、选项和其他组件发生了什么情况
- **确定进行更改的人员** — 查看上次修改元素的用户以及修改时间
- **意外行为疑难解答** — 通过用户操作回溯以查找何时以及如何引入问题
- **支持合规性和审核** — 维护所有配置更改的完整、不可篡改的记录

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
>对于Campaign v8托管云服务，服务器基础架构（CPU、内存、磁盘）由Adobe进行监视和管理。 本页和控制面板中介绍的监控功能是互补的 — 它们使您能够查看数据和配置，而无需访问基础结构。 Adobe执行的某些操作会显示在您的Campaign日志中的&#x200B;**campaign-loginmonitor**&#x200B;用户下。 了解有关[Adobe管理的监视](#adobe-cloud-monitoring)的详细信息。

### Adobe管理的监控 {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services通过灵活的云基础架构为满足苛刻的客户体验交付需求提供关键任务支持。 这使组织能够启动、监控和优化客户体验，而无需自行管理或操作Campaign基础架构。

Adobe全天候监控Campaign Cloud Services环境，以检测技术问题并最大程度地减少中断。 检测到问题时，系统会使用自动重新启动和自动启动机制来尝试修复。 如果系统无法自行修复，Adobe电话技术支持会根据预定义的警报Runbook进行干预。

>[!TIP]
>
>您可以通过[Campaign控制面板](#control-panel)订阅实时实例警报，并针对检测到的问题（例如，接近过期的SSL证书）接收建议的修正步骤。

**监视层**

Adobe跨三个层监控您的环境。 第1级问题影响最广，响应速度最快：

| 层 | 组 | 您可能会遇到什么 |
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
>Adobe Campaign Cloud Services基于多云策略构建，在AWS和Azure上进行部署。 AWS、Azure和其他数据中心部署中的监控功能有所不同。 除非另有说明，否则上表适用于托管在AWS上的Campaign Cloud Services客户。 Adobe Campaign目前不会向客户公开由电话随叫随到工程使用的所有监控数据。

### 技术工作流 {#technical-workflows}

技术工作流在后台静默运行，以维护您的Campaign实例。 它们不是由用户创建的 — 而是随产品一起提供的。 如果技术工作流失败，它可能会直接影响投放和数据质量。

验证每个技术工作流是否都按计划执行，无错误完成，并正确处理数据。

| 工作流 | 用途 | 如果失败 |
| --- | --- | --- |
| **跟踪** | 处理电子邮件投放中的跟踪数据 | 单击并打开量度可在报表中停止更新 |
| **清理** | 删除旧数据和日志以保持数据库性能 | 数据库增长不受控制，查询和投放性能下降 |
| **可投放性更新** | 更新可投放性规则和垃圾邮件过滤模式 | 规则过时；筛选准确性可能会降低 |
| **数据库清理** | 清除旧的投放和跟踪日志 | 日志累积会随时间减慢查询和报告的速度 |

了解有关[技术工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}的详细信息

### Campaign 控制面板 {#control-panel}

Campaign控制面板为管理员提供自助服务功能，无需支持票证即可监控和管理Campaign实例。

| 监视类型 | 功能 |
| --- | --- |
| **性能** | 活动用户档案使用情况与合同限制、数据库使用情况和容量、工作流执行状态、投放吞吐量和延迟 |
| **基础架构** | SFTP存储容量、子域配置、SSL证书到期警报、IP允许列表 |
| **实例** | 内部版本和已安装的包、系统配置概述、授权的外部域 |

了解有关[控制面板](../config/self-service.md)和[控制面板性能监视](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=zh-Hans){target="_blank"}的更多信息

>[!NOTE]
>
>对于Campaign v8托管云服务，Adobe将监控和管理服务器基础架构、操作系统和应用程序层。 本页中介绍的监控功能与控制面板是互补的 — 它们使您能够查看数据和配置，而无需访问基础结构。

## 跟踪和报告 {#tracking-reporting}

### 消息跟踪 {#message-tracking}

跟踪记录收件人如何在投放后与您的邮件进行交互。 所有跟踪的事件都存储在跟踪日志中，并显示在投放报告中。

- **打开次数** — 加载跟踪像素时录制（仅限电子邮件）
- **点击次数** — 为消息中的每个跟踪链接记录
- **取消订阅** — 通过取消订阅链接发出选择退出请求
- **镜像页面查看次数** — 在浏览器中查看电子邮件的收件人

了解有关[邮件跟踪](../send/tracking.md)的更多信息

### 投放报告 {#delivery-reports}

Adobe Campaign提供了一组全面的报告来分析您的交付性能：

- **投放摘要** — 单个投放的发送、投放和失败概述
- **跟踪指标** — 打开次数、点击次数和点进率以及随时间变化的趋势
- **URL和点击流** — 点击次数最多的链接排名，包含计数和百分比
- **热门点击** — 显示收件人点击电子邮件正文位置的可视化叠加

了解有关[传递报告](../reporting/delivery-reports.md)的更多信息

### 全局报告 {#global-reports}

访问全局报告以分析所有活动和投放的表现：

- **投放吞吐量** — 在一段时间内所有投放中每小时发送的消息数
- **无法投放项和退回** — 按失败类型和原因细分失败的投放
- **用户活动** — 在所有营销活动中聚合打开、点击和取消订阅次数

了解有关[全局报告](../reporting/global-reports.md)的详细信息

## 相关主题 {#related-topics}

- [投放最佳实践](delivery-best-practices.md)
- [隔离管理](../send/quarantines.md)
- [配置和发送投放](../send/configure-and-send.md)
- [报告快速入门](../reporting/gs-reporting.md)
