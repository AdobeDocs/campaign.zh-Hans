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
source-git-commit: 2c6140065272892d40ad66da0c0c89dfe169ce19
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 5%
---
# Campaign选项 {#campaign-options}

选项是控制Campaign实例行为方式的参数，例如电子邮件中图像的默认大小限制、同时运行的工作流数量或投放模板的默认路由提供程序。 某些选项是内置的，而其他选项是在需要时创建的。 可用的选项取决于实例上安装的包。 在[内置包](built-in-packages.md)中了解详情。

>[!CAUTION]
>
>仅修改Campaign文档中记录的选项，并且仅修改所述选项。 未记录的选项是内部选项，不得修改。 修改选项是为专家用户保留的。

## 存储选项的位置 {#where-options-are-stored}

选项存储在Campaign数据库的&#x200B;**xtkOption**&#x200B;表（架构&#x200B;**xtk:option**）中。 在Campaign Explorer中，它们位于&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**&#x200B;下。

## 使用选项 {#use-options}

1. 在Campaign Explorer中，浏览到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**。
1. Select选项，然后更新其值。 如果选项不存在，则使用文档中提供的确切名称创建该选项。
1. 设置文档所需类型的值。 例如，CRM同步日期的文本选项或工作流重新启动延迟的整数选项。

某些选项包含凭据。 使用`cryptString`函数加密密钥，如[使用Campaign和Adobe Experience Platform登录页](../connect/ac-aep-landing-pages.md)中所述。 旋转凭据时，同时旋转选项中存储的凭据。 请参阅[凭据轮换指南](../../technotes/security/credential-rotation-guide.md#ac-options-credentials)以了解详情。

## 为Campaign v8记录的选项 {#documented-options}

下表列出了Campaign v8文档要求您使用的选项，以及描述如何使用的页面的链接。

### 投放 {#delivery-options}

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

### 营销活动和工作流 {#campaign-workflow-options}

| 选项 | 说明 |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | 创建它并将其设置为1，以便活动所有者可以确认发送，即使定义了审阅人也是如此。 将其设置为0可取消激活。 [了解详情](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | 活动同时处理的投放、工作流、假设和模拟作业的最大数量。 默认值为10。 [了解详情](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | 两次检查暂停的工作流之间的间隔天数。 [了解详情](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | 将其创建为整数选项，以更改自动检查并重新启动工作流的30秒间隔。 [了解详情](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | 将其设置为0可取消激活SQL代码活动对受阻的SQL方法的保护。 [了解详情](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | SQL活动阻止或警告的SQL方法的列表。 [了解详情](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |

### 电子邮件默认值 {#email-default-options}

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

| 选项 | 说明 |
|---|---|
| NmsNPAI_EmailMaxError | 在收件人被隔离之前，电子邮件渠道上接受的最大软错误数。 |
| NmsNPAI_EmailSignalErrorDelay | 在电子邮件渠道上发生上一个软错误后且未考虑新软错误之前必须经过的最短时间。 |
| NmsNPAI_MobileMaxError | 在收件人被隔离之前，移动渠道上接受的最大软错误数。 |
| NmsNPAI_MobileSignalErrorDelay | 在移动渠道上上一次软错误之后，必须经过的最短时间，之后才会考虑新的软错误。 |

了解有关[投放失败](../send/delivery-failures.md)中的软错误和隔离的更多信息。

### 消息中心阈值 {#message-center-options}

每个实时事件量度都有警告阈值和警报阈值。 选项名称以Warning或Alert结尾，例如MC_RtEventErrorWarning和MC_RtEventErrorAlert。 在[Campaign事务性消息传递](../send/transactional.md)中了解有关事务性消息传递的更多信息。

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

### 隐私请求 {#privacy-options}

| 选项 | 说明 |
|---|---|
| Privacy_Request_ConfirmDeletePending | 将其设置为1可在第二步中手动确认界面中的每个删除。 否则，删除数据而不进行确认。 |
| Privacy_Request_ConfirmDeletePendingDelay | 延迟的时间，在此之后会取消等待删除确认的请求。 |
| Privacy_Request_MaxErrorAllowed | 处理或删除隐私请求时允许的最大错误数。 |
| Privacy_Request_PurgeDelay | 在队列中创建请求和删除其数据之间的延迟。 |

在[管理隐私请求](../start/privacy.md)中了解有关隐私请求的更多信息。

### 审核跟踪 {#audit-trail-options}

将审计线索选项设置为1可启用实体的审计线索，设置为0可禁用该实体：XtkAudit_Workflows、XtkAudit_DataSchema、XtkAudit_Option、XtkAudit_Delivery、XtkAudit_ExtAccount、XtkAudit_DeliveryMapping、XtkAudit_WebApp、XtkAudit_Offer、XtkAudit_Operator。 对每个实体使用XtkAudit_Enable_All。 在[审核记录](../reporting/audit-trail.md#enable-disable-audit-trail)中了解详情。

### 集成和调查 {#integration-options}

| 选项 | 说明 |
|---|---|
| IMS_CLIENT_ID、IMS_CLIENT_SECRET、IMS_ORG_ID、IMS_CLIENT_API_KEY | 用于登录Adobe Experience Platform页面的Adobe Developer Console凭据。 [了解详情](../connect/ac-aep-landing-pages.md) |
| 拉斯廷波特_<instance>_<activity> | 通用CRM连接器活动上次同步的日期。 手动创建该文本作为文本选项，格式为`yyyy/MM/dd hh:mm:ss`。 [了解详情](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | 创建并将其设置为1以保存所有调查的原始答案的副本（默认情况下）。 [了解详情](../dev/surveys/managing-answers.md) |

## 相关主题 {#related-topics}

* [内置软件包](built-in-packages.md)
* [全局原则](general-architecture.md)
* [凭据轮换指南](../../technotes/security/credential-rotation-guide.md)
