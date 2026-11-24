---
title: Campaign选项
description: 了解什么是Campaign选项、这些选项的存储位置以及如何使用为Campaign v8记录的选项
feature: Architecture
role: Admin, Developer
level: Intermediate
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 36111995a9a550d5089107bbc1f734c204db8aff
workflow-type: tm+mt
source-wordcount: '2828'
ht-degree: 3%
---
# Campaign选项 {#campaign-options}

选项是控制Campaign实例行为方式的参数，例如电子邮件中图像的默认大小限制、同时运行的工作流数量或投放模板的默认路由提供程序。 某些选项是内置的，而其他选项是在需要时创建的。 可用的选项取决于实例上安装的包。 在[内置包](built-in-packages.md)中了解详情。

>[!CAUTION]
>
>仅修改Campaign文档中记录的选项，并且仅修改所述选项。 未记录的选项是内部选项，不得修改。 修改选项是为专家用户保留的。

## 存储选项的位置 {#where-options-are-stored}

选项存储在Campaign数据库的&#x200B;**xtkOption**&#x200B;表（架构&#x200B;**xtk:option**）中。 在Campaign Explorer中，它们位于&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**&#x200B;下。 在Campaign Web用户界面中，它们位于&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Options]**&#x200B;下。 两个列表相同。 请参阅[配置Campaign选项](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options){target="_blank"}以了解详情。

## 使用选项 {#use-options}

1. 在Campaign Explorer中，浏览到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**。
1. Select选项，然后更新其值。 如果选项不存在，则使用文档中提供的确切名称创建该选项。
1. 设置文档所需类型的值。 例如，CRM同步日期的文本选项或工作流重新启动延迟的整数选项。

您还可以创建自己的选项，例如存储工作流的中间数据。 输入名称，选择数据类型，然后设置值。 请参阅[配置Campaign选项](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#create){target="_blank"}以了解详情。

某些选项包含凭据。 使用`cryptString`函数加密密钥，如[使用Campaign和Adobe Experience Platform登录页](../connect/ac-aep-landing-pages.md)中所述。 旋转凭据时，同时旋转选项中存储的凭据。 请参阅[凭据轮换指南](../../technotes/security/credential-rotation-guide.md#ac-options-credentials)以了解详情。

## 在工作流和个性化中使用选项 {#use-options-in-processes}

您可以从JavaScript代码、个性化和查询中读取和写入选项值。

* **JavaScript代码**，如JavaScript代码工作流活动： `getOption('OptionName')`返回选项的值，`setOption('OptionName', value, 'description')`设置它。 例如，`getOption('IMS_ORG_ID')`。 在[getOption](../../campaign-api/f-getoption.md)和[setOption](../../campaign-api/f-setoption.md)中了解详情。
* **投放个性化**： `<%@ include option='OptionName' %>`插入选项的值。 例如，`<%@ include option='NmsServer_URL' %>`将服务器URL包含在LINE消息中指向Web应用的链接中。 使用Adobe Campaign[&#128279;](../send/line/line.md)在发送直销邮件中了解更多信息。
* **查询编辑器**：在&#x200B;**值**&#x200B;字段中键入`$(options:OPTION_NAME)`以使用选项的值。 在[设计查询](../start/design-queries.md)中了解详情。

## 可用选项 {#available-options}

下表列出了Campaign v8中按区域分组的可用选项。 当文档的其他页面描述某个选项时，表将链接到该选项。

### 投放 {#delivery-options}

这些选项控制如何准备和发送投放。 其中包括图像和附件限制、默认路由提供程序、中间源拆分阈值、打开跟踪脚本、公共服务器URL、投放有效性、重复项和延迟投放的处理以及条形码。 在[附加文件](../send/attaching-files.md)、[电子邮件参数](../send/email-parameters.md)、[投放最佳实践](../start/delivery-best-practices.md)、[开始使用Campaign架构](architecture.md#split)、[有关电子邮件跟踪像素的指南](../start/cnil-pixel-tracking.md)和[发送直销邮件](../send/line/line.md)中了解更多信息。

| 选项 | 说明 |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | 从个性化URL下载并附加到电子邮件的图像的最大字节数。 默认值为100,000字节(100 KB)。 [了解详情](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendedAttachments | 电子邮件或事务性电子邮件模板中在显示警告之前的最大附件数。 默认值为1。 [了解详情](../send/attaching-files.md) |
| NmsEmail_DefaultErrorAddr | 实例的默认错误电子邮件地址，在投放将错误地址留空时使用。 [了解详情](../send/email-parameters.md) |
| XtkEmail_Characters | 电子邮件地址的有效字符。 [了解详情](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | 新投放模板的默认路由提供程序。 将其设置为拆分外部帐户的名称，以默认使用拆分投放。 [了解详情](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | 投放在多个中间源实例之间进行拆分的大小。 默认值为100K。 [了解详情](architecture.md#split) |
| NmsTracking_OpenFormula | 计算打开的跟踪URL的脚本。 为每个像素定义一个选项。 [了解详情](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | 公共Web应用程序服务器的基本URL。 例如，用于在LINE消息中包含Web应用程序链接。 [了解详情](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | 投放的默认有效期（以秒为单位）。 |
| NmsBroadcast_RemoveDuplicatesRecipients | 将其设置为1可自动忽略重复的收件人。 |
| NmsDelivery_ImageServerTimeout | 检索从个性化URL下载并附加到电子邮件的图像时从服务器获取响应的超时（以秒为单位）。 如果超出超时，则无法发送消息。 默认值为60秒。 |
| NmsDeliveryWizard_ShowDeliveryWeight | 在投放助理中显示消息权重。 |
| NmsMTA_Alert_Delay | 延迟（以分钟为单位），超过该时间后，投放将被视为延迟。 默认值为30分钟。 |
| NmsServer_MirrorPageUrl | 镜像页面服务器的URL。 路由定义未指定URL时，这是电子邮件投放的默认值。 默认情况下，它与跟踪服务器URL相同。 |
| XtkBarcode_SpecialChar | 启用或禁用对Code128条形码的特殊字符的支持。 |
| XtkSecurity_Restrict_EditXML | 将其添加为值0以禁用对投放的XML代码的编辑（编辑XML源或Ctrl+F4）。 |
| NMS_ActivateOwnerConfirmation | 将其设置为1，以便当指定特定操作员或组开始投放时，负责投放的操作员可以确认发送。 将其设置为0可取消激活：只有指定的操作员或组或管理员才能确认发送。 |
| NmsDelivery_senderAddressMask | 电子邮件投放的“发件人”字段中允许的发件人地址列表（以逗号分隔）。 当选项具有值时，该字段会成为下拉列表。 该限制是全局性的：适用于每个品牌和投放模板，并且仅支持静态地址。 [了解详情](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#restrict-sender-address){target="_blank"} |

### 营销活动和工作流 {#campaign-workflow-options}

这些选项可控制营销策划和工作流的运行方式。 其中包括发送的所有者确认、同时处理的作业数以及工作流检查和自动重新启动。 它们还包括对SQL活动的保护、默认促销活动有效性以及导出报告的徽标。 了解有关[营销活动投放](../../automation/campaigns/marketing-campaign-deliveries.md)、[工作流最佳实践](../../automation/workflow/workflow-best-practices.md)、[监测工作流执行](../../automation/workflow/monitor-workflow-execution.md)、[工作流属性](../../automation/workflow/workflow-properties.md)以及[SQL代码和JavaScript代码](../../automation/workflow/sql-code-and-javascript-code.md#important-notes)的更多信息。

| 选项 | 说明 |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | 创建它并将其设置为1，以便活动所有者可以确认发送，即使定义了审阅人也是如此。 将其设置为0可取消激活。 [了解详情](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | 活动同时处理的投放、工作流、假设和模拟作业的最大数量。 默认值为10。 [了解详情](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | 两次检查暂停的工作流之间的间隔天数。 [了解详情](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | 将其创建为整数选项，以更改自动检查并重新启动工作流的30秒间隔。 [了解详情](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | 将其设置为0可取消激活SQL代码活动对受阻的SQL方法的保护。 [了解详情](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | SQL活动阻止或警告的SQL方法的列表。 [了解详情](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | 营销活动的默认有效期（以秒为单位）。 |
| NmsOperation_TimeRange | 计划模式下定位和提取条件的时间段。 |
| NmsOperation_OperationMgtDebug | 将其设置为1可在工作流审核日志中记录operationMgt技术工作流的执行信息。 |
| NmsOperation_DeliveryPreparationWindow | 达到该天数后，operationMgt技术工作流会从运行的投放计数中排除状态不一致的投放。 默认值为7。 |
| Workflow_AnalysisThreshold | 受影响的记录数，之后将自动重新计算表统计信息。 |
| XtkReport_Logo | 徽标显示在导出报告的右上角。 |

### 电子邮件默认值 {#email-default-options}

这些选项定义电子邮件的默认发件人、回复地址和标签。 当投放将相应字段留空时，Campaign会使用它们。 在[电子邮件参数](../send/email-parameters.md)和[使用投放模板](../send/create-templates.md)中了解更多信息。

| 选项 | 说明 |
|---|---|
| NmsEmail_DefaultFromAddr | 实例的默认发件人地址，在投放将其留空时使用。 |
| NmsEmail_FromName | 实例的默认From标签，在投放将其留空时使用。 |
| NmsEmail_DefaultReplyToAddr | 实例的默认回复地址，在投放将其留空时使用。 |
| NmsEmail_ReplyToName | 实例的默认回复标签，在投放将其留空时使用。 |
| NmsEmail_DefaultErrorAddr | 实例的默认错误地址，在投放将其留空时使用。 [了解详情](../send/email-parameters.md) |
| NmsDelivery_FromAddressMasks | 发送消息时使用的发件人地址的语法。 |
| NmsDelivery_ErrorAddressMasks | 回复消息时使用的错误地址的语法。 |
| NmsEmail_ExpOrganization | 贵组织的通用名称，用于向收件人显示的一些警告消息。 |

### 软错误和隔离 {#error-options}

这些选项定义在软错误（即临时投放失败）后将收件人隔离的时间。 在Campaign[&#128279;](../send/quarantines.md#soft-error-management)的[隔离管理和Campaign](../send/delivery-failures.md#retries)的投放失败中了解更多信息。

| 选项 | 说明 |
|---|---|
| NmsNPAI_EmailMaxError | 在收件人被隔离之前，电子邮件渠道上接受的最大软错误数。 |
| NmsNPAI_EmailSignalErrorDelay | 在电子邮件渠道上发生上一个软错误后且未考虑新软错误之前必须经过的最短时间。 |
| NmsNPAI_MobileMaxError | 在收件人被隔离之前，移动渠道上接受的最大软错误数。 |
| NmsNPAI_MobileSignalErrorDelay | 在移动渠道上上一次软错误之后，必须经过的最短时间，之后才会考虑新的软错误。 |

### 渠道 {#channel-options}

这些选项定义直邮的发件人地址、LINE和SMS渠道的设置以及入站电子邮件的允许转发地址。 在[使用Adobe Campaign发送直邮](../send/direct-mail.md)、[使用Adobe Campaign发送直邮](../send/line/line.md)和[使用Adobe Campaign发送SMS](../send/sms/sms.md)中了解更多信息。

| 选项 | 说明 |
|---|---|
| NmsPaper_SenderLine1， NmsPaper_SenderLine3， NmsPaper_SenderLine4， NmsPaper_SenderLine6， NmsPaper_SenderLine7 | 直邮投放的发件人地址的第1、3、4、6和7行。 |
| NmsLine_AESKey | lineImage servlet用于对LINE渠道中的URL进行编码的AES键。 |
| NmsLine_MessageCenterURL | 用于在LINE渠道中发送欢迎消息的消息中心服务器URL。 |
| NmsSMS_Priority | 已发送短信消息的优先级，传输到短信网关。 |
| NmsInmail_AllowlistEmails | 入站邮件处理模块的授权转发电子邮件地址，用逗号分隔。 使用*可允许所有地址。 |

### 消息中心阈值 {#message-center-options}

这些选项定义了在处理实时事件（触发事务性消息）降级时引发警告或警报的阈值。 每个量度都有警告阈值和警报阈值。 选项名称以Warning或Alert结尾，例如MC_RtEventErrorWarning和MC_RtEventErrorAlert。 在[Campaign事务性消息传递](../send/transactional.md)和[Campaign事务性消息传递设置](../config/transactional-msg-settings.md)中了解详情。

| 选项名称前缀 | 量度 |
|---|---|
| MC_RtEventAvgDeliveryTime | 实时事件的平均发送时间。 |
| MC_RtEventAvgProcessTime | 实时事件的平均处理时间。 |
| MC_RtEventAvgQueueTime | 实时事件的平均排队时间。 |
| MC_RtEventAvgQueue | 已排队实时事件的平均数。 |
| MC_RtEventMaxQueue | 已排队实时事件的最大数量。 |
| MC_RtEventMinQueue | 已排队实时事件的最小数目。 |
| MC_RtEventQueue | 挂起实时事件的队列。 警报阈值是关键条件。 |
| MC_RtEventError | 实时事件的处理错误。 |
| MC_RtEventThroughput | 实时事件的吞吐量。 |

### 数据保留和数据库 {#database-options}

清理工作流会清除旧记录，以防止数据库增长。 这些选项定义Campaign保留每种类型数据的时间。 当您在界面中更改延迟时，会自动创建清除延迟选项。 如果从选项列表中编辑它，则以秒为单位表示该值。 在[一般架构](general-architecture.md)和[安全准则](../config/security.md#consent)中了解详情。

| 选项 | 说明 |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | 擦除投放日志(broadlog)后的延迟。 |
| NmsCleanup_TrackingLogPurgeDelay | 延迟时间，超过此时间将擦除跟踪日志。 |
| NmsCleanup_TrackingStatPurgeDelay | 延迟时间，超过此时间将擦除跟踪统计信息。 |
| NmsCleanup_EventPurgeDelay | 事件被擦除后的延迟。 |
| NmsCleanup_EventHistoPurgeDelay | 延迟时间，在此时间之后将擦除事件历史记录。 |
| NmsCleanup_EventStatPurgeDelay | 擦除事件统计信息之后的延迟。 |
| NmsCleanup_PropositionPurgeDelay | 延迟时间，超过此时间将擦除建议。 |
| NmsCleanup_QuarantineMailboxFull | 延迟时间，超过此时间将擦除隔离。 |
| NmsCleanup_RecycledDeliveryPurgeDelay | 延迟时间，过了这段时间，已回收的投放将被擦除。 |
| NmsCleanup_RejectsPurgeDelay | 延迟时间，超过此时间将擦除拒绝。 |
| NmsCleanup_VisitorPurgeDelay | 访客被擦除后的延迟。 |
| NmsCleanup_WorkflowResultPurgeDelay | 延迟时间，超过此时间将擦除工作流结果。 |
| XtkCleanup_NoStats | 将其设置为1，以便清理工作流不会更新数据库统计信息。 |
| WdbcKillSessionPolicy | PostgreSQL上无条件停止工作流的行为。 0（默认）：停止工作流进程而不影响数据库。 1：停止进程并取消查询(pg_cancel_backend)。 2：停止进程并终止查询(pg_terminate_backend)。 |
| XtkSequence_AutoGeneration | 适用于在设置此选项后创建的自定义架构，具有autopk=&quot;true&quot;且没有pkSequence属性：Campaign会自动生成序列。 |

### 消息中心自定义 {#message-center-customization}

这些选项允许您自定义Campaign如何丰富和路由实时事件和批量事件。 在[Campaign事务性消息传递](../send/transactional.md)和[Campaign事务性消息传递设置](../config/transactional-msg-settings.md)中了解详情。

| 选项 | 说明 |
|---|---|
| MC_EnrichmentCustomJs | JavaScript库，用于丰富各种活动。 它必须为实时事件实施extendsRtEvents(aiEventId)，并为批处理事件实施extendsBatchEvents(aiEventId)。 这两个函数都丰富了事件并将它们保存在数据库中。 |
| MC_RoutingCustomJs | 用于路由事件的JavaScript库。 它必须实现dispatchRtEvent(iEventId)和dispatchBatchEvent(iEventId)，这两者返回为实时事件或批处理事件选择的事务性消息的内部名称。 |
| NmsMessageCenter_RoutingBatchSize | 用于事件路由的组的大小。 |
| NmsTracking_RT_ClickFormula， NmsTracking_RT_OpenFormula | 在激活品牌策略时，用于实时投放的点击和打开跟踪的公式。 它们是在RT控制实例上配置的。 [了解详情](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |
| Branding_RT_ListXtkOptions_toPublish | 包含自定义跟踪公式的选项列表（以逗号分隔），以便RT投放可以应用它们。 [了解详情](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |

### 互动（选件管理） {#interaction-options}

这些选项适用于选件管理模块Campaign Interaction。 它们控制如何写入建议以及同步控制实例和执行实例的方式。 在[Campaign交互 — 选件管理](../interaction/interaction.md)和交互架构的[维护选项](../interaction/interaction-architecture.md#maintenance-options)中了解更多信息。

| 选项 | 说明 |
|---|---|
| NmsInteraction_UseDaemon | 将其设置为1可启用异步写入建议，设置为0可禁用建议。 |
| NmsInteraction_MapWorkflowId | 所有生成的同步工作流的列表。 控制实例的维护选项。 |
| NmsExecutionInstanceId | 执行实例的标识符。 在执行实例上可用。 |

以下选项也是控制实例的维护选项：

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**：在给定实例上同步环境的上次日期。
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**：架构建议从一个实例同步到另一个实例的上次日期。

>[!CAUTION]
>
>仅将维护选项用于特定维护案例。

以下选项适用于企业(FFDA)部署中不可用的优惠券。 在[个性化优惠券](../send/personalized-coupons.md)中了解详情。

| 选项 | 说明 |
|---|---|
| NmsModule_CouponsEnabled | 启用优惠券。 |
| NmsCoupons_MaxPerTransac | 每个SQL事务更新的优惠券数。 |

### 隐私请求 {#privacy-options}

这些选项控制Campaign如何处理隐私请求，例如删除确认、允许的错误数以及请求数据的保留时间。 请参阅[在Campaign中管理隐私请求](../start/privacy.md)以了解详情。

| 选项 | 说明 |
|---|---|
| Privacy_Request_ConfirmDeletePending | 将其设置为1可在第二步中手动确认界面中的每个删除。 否则，删除数据而不进行确认。 |
| Privacy_Request_ConfirmDeletePendingDelay | 延迟的时间，在此之后会取消等待删除确认的请求。 |
| Privacy_Request_MaxErrorAllowed | 处理或删除隐私请求时允许的最大错误数。 |
| Privacy_Request_PurgeDelay | 在队列中创建请求和删除其数据之间的延迟。 |
| realtimeReporting_collectPII | 选择用于动态报告的个人身份信息(PII)协议。 值1对应于“稍后询问我”、2对应于“拒绝”、3对应于“接受”。 [了解详情](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reporting/dynamic-reporting/pii-agreement){target="_blank"} |

### 审核跟踪 {#audit-trail-options}

审核记录会记录对营销活动实体所做的更改。 使用这些选项可为实体启用或禁用它，例如节省数据库中的空间。 将该值设置为1可启用审核跟踪，设置为0可禁用审核跟踪。 在[审核记录](../reporting/audit-trail.md#enable-disable-audit-trail)中了解详情。

| 选项 | 已审计实体 |
|---|---|
| XtkAudit_Workflows | 工作流 |
| XtkAudit_DataSchema | 架构 |
| XtkAudit_Option | 选项 |
| XtkAudit_Delivery | 投放 |
| XtkAudit_ExtAccount | 外部帐户 |
| XtkAudit_DeliveryMapping | 投放映射 |
| XtkAudit_WebApp | Web 应用程序 |
| XtkAudit_Offer | 产品建议 |
| XtkAudit_Operator | 运算符 |
| XtkAudit_Enable_All | 所有实体 |

### 集成和调查 {#integration-options}

这些选项存储集成和调查的设置：登陆页面的Adobe Developer Console凭据、CRM Connector活动的上次同步日期以及调查答案的默认备份。 在[从Adobe Experience Platform登录页面](../connect/ac-aep-landing-pages.md)更新Adobe Campaign配置文件[、CRM Connectors数据同步](../connect/crm-data-sync.md)和[管理答案](../dev/surveys/managing-answers.md)中了解更多信息。

| 选项 | 说明 |
|---|---|
| IMS_CLIENT_ID、IMS_CLIENT_SECRET、IMS_ORG_ID、IMS_CLIENT_API_KEY | 用于登录Adobe Experience Platform页面的Adobe Developer Console凭据。 [了解详情](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_ ，后跟实例的内部名称和活动名称 | 通用CRM连接器活动上次同步的日期。 手动创建该文本作为文本选项，格式为`yyyy/MM/dd hh:mm:ss`。 [了解详情](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | 创建并将其设置为1以保存所有调查的原始答案的副本（默认情况下）。 [了解详情](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter | 可以在Campaign中使用的Adobe Experience Manager资源类型，以逗号分隔。 [了解详情](../connect/ac-aem.md) |
| nmsPipeline_config | Adobe Experience Cloud触发器的配置（JSON格式）。 将其创建为长文本选项。 [了解详情](../connect/ac-triggers.md) |
| TNT_EdgeServer | 用于集成的Adobe Target服务器，默认设置。 它是Adobe Target域服务器，后跟/m2，例如tt.omtrdc.net/m2。 [了解详情](../connect/ac-at.md) |
| TNT_TenantName | Adobe Target组织（客户端）的名称。 [了解详情](../connect/ac-at.md) |
| AAM_DataSourceId， AAM_DestinationId | 与Adobe Audience Manager集成使用的标识符。 [了解详情](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDw | Azure Synapse (Azure SQL Data Warehouse)连接器的选项。 [了解详情](../connect/fda.md) |

## 相关主题 {#related-topics}

* [内置软件包](built-in-packages.md)
* [全局原则](general-architecture.md)
* [凭据轮换指南](../../technotes/security/credential-rotation-guide.md)
