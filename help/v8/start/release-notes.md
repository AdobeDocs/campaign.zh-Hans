---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3bc247ba81de3de56c26bdf8fa9b8aa5ea91fb2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 23%

---

# 最新版本 {#latest-release}

此页面列出了 Campaign v8（控制台）**最新版本**&#x200B;中的新增功能、改进和修复。要详细了解 Campaign 版本和升级，请参阅[此页面](upgrades.md)。其他版本列于本文档的先前版本部分。

## 版本 8.8.2 {#release-8-8-2}

_2025年10月9日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**限量发布版** (LA)。

### 新增功能 {#features-8-8-2}

**新SMS发送连接器**&#x200B;现在可用于[Campaign FFDA部署](../architecture/enterprise-deployment.md)。 请参阅[详细文档](../send/sms/sms.md)。

此版本还随附了一组可在Campaign Web用户界面中使用的功能：

* [事务性消息中的用户档案扩充](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [事务性消息传递、推送通知和短信的多语言功能](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

请参阅Campaign Web UI [发行说明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hans){target="_blank"}

### 修复 {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* 修复了可能导致数据库清理工作流失败的问题。 (NEO-87949)
* 修复了分布式营销中存在的一个问题，即协作营销活动投放的跟踪数据未记录。 (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* 修复了可能导致片段中的个性化无法正常运行的问题。 (NEO-88161)
* 修复了在迁移到新的Redshift ODBC连接器后，可能导致拆分工作流活动失败并出现SQL错误的问题。 (NEO-87466)
* 修复了可能导致工作流中排除计数不准确的问题。 (NEO-89207)
* 修复了可能导致推送通知的点击指示器不准确的问题。 (NEO-89503)
* 修复了短信投放日志更新不正确的问题，从而导致Adobe Campaign中无法准确报告状态。 (NEO-88479)
* 修复了投放内容中法语引号被错误地转换为英语引号的问题。 (NEO-89631)
* 修复了实时服务器为无效的IMS令牌返回错误响应代码的问题。 (NEO-87428)
* 修复了电子邮件和短信的投放统计信息未完全重新计算，从而导致成功指标不准确的问题。 (NEO-88106)
* 修复了新的SMS发送连接器问题，该问题导致投放日志错误地为一小部分消息分配投放状态。 (NEO-89581)
* 修复了新的SMS发送连接器的问题，该问题导致T-Mobile投放的成功量度在营销和中间服务器上未正确更新。 (NEO-89850)
* 修复了实时实例和营销实例之间的同步问题，该问题导致跟踪日志丢失和报告不正确。 (NEO-90247)
* 修复了在自定义架构中选择两个连续1-N链接中的字段时可能导致错误的工作流扩充问题。 (NEO-87682)

