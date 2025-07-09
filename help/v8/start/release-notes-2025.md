---
title: Campaign v8（控制台）2025 发行说明
description: 2025 Campaign v8版本的功能和改进列表
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 96%

---

# 2025 年发行说明 {#2025-rn}

此页面列出了 **2025 Campaign v8 版本**&#x200B;中的新增功能、改进和修复。有关最新版本，请参阅[此页面](release-notes.md)。

对于任何新实施或升级到现有环境，请安装[最新版本](release-notes.md)。

>[!BEGINSHADEBOX]

**本页面内容**

* [版本 8.6.5](#release-8-6-5)
* [版本 8.6.4](#release-8-6-4)
* [版本 8.7.4](#release-8-7-4)
* [版本 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## 版本 8.6.5 {#release-8-6-5}

_2025 年 4 月 25 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**限量发布版** (LA)。

### 新增功能 {#features-8-6-5}

**新短信发送连接器** - 短信发送连接器经过现代化改造和改进，可启用收发器模式 SMPP 连接、启用持久 SMPP 连接，并确保从 Adobe Campaign Standard 过渡的环境具有更好的兼容性。新的短信外部帐户现在可用于所有新的短信实施。现有实施仍受支持，但建议迁移到此新的现代化扩展连接器。[了解更多信息](../send/sms/sms.md)。

### 一般改进 {#improvements-8-6-5}

* 在企业 (FFDA) 部署中，应用程序的全局性能已得到改进，包括投放校样发送和数据库清理。

* 为提高应用程序之间所有通信的安全性，现在外部 API 调用支持 mTLS。

* 邮件传输代理 (MTA) - 修复了孤立 MTA 子项停留在 **[!UICONTROL Start pending]** 状态的问题。

### 修复 {#fixes-8-6-5}

此版本中还修复了以下问题：

NEO-67620、NEO-71534、NEO-80245、NEO-81105、NEO-81758、NEO-81908、NEO-82351、NEO-82742、NEO-83044、NEO-83138、NEO-83350、NEO-83729、NEO-83793、NEO-83809、NEO-84038、NEO-84108、NEO-85269、NEO-86121、NEO-86556、NEO-86739

## 版本 8.7.4 {#release-8-7-4}

_2025 年 4 月 10 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#features-8-7-4}

* **SMS REST API 支持** - 事务性消息传递 REST API 现可用于短信渠道。当负载中同时存在电子邮件和移动电话时，您可以使用“wishedChannel”字段来指定渠道。如果未提供，则默认使用电子邮件，除非 wishedChannel 明确要求使用短信。

* **多语言投放** - 从 4 月版的 Campaign Web 用户界面开始，您将能够以不同语言发送多个电子邮件投放，并访问相关的动态报告。此功能仅在 4 月底于 Adobe Campaign Web 用户界面中推出，并且需要服务器更新至 Campaign v8.7.4。

### 修复 {#fixes-8-7-4}

此版本中修复了以下问题：

NEO-80245、NEO-83559

## 版本 8.7.3 {#release-8-7-3}

_2025 年 2 月 14 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#features-8-7-3}

* **事务性消息的动态报告** - 您现在可以在动态报告用户界面中监控事务性消息。通过这些报告，营销人员能够实时查看事务性消息的所有报告量度和维度，并实时分析通过模板发送的投放。[了解更多信息](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

* **事务性消息传递 REST API** - 现在可以对电子邮件使用基于事件的事务性 API。[了解更多信息](../dev/api/get-started-apis.md)

### 修复 {#fixes-8-7-3}

此版本中修复了以下问题：

NEO-79373、NEO-81908、NEO-83081

## 版本 8.6.4 {#release-8-6-4}

_2025 年 1 月 15 日_

### 一般改进 {#improvements-8-6-4}

* 在[企业 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)环境中的投放分析期间，Campaign 应用程序的稳定性得到了改进。
* 此版本附带改进和增强的 FFDA 架构机制，包括密钥管理、暂存和数据复制。
* 已为[企业 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)引入新的技术工作流。这些工作流通过将并行复制请求集中到相应的表中，来复制投放和相关数据。这些工作流以 `Replicate nms` 开头。[了解更多信息](../architecture/replication.md)
* 工作流属性中现在有新的 **Enable watchdog supervisor to keep workflow running permanently** 选项。启用此选项后，工作流会在发生错误后自动重新启动。如果工作流仍然出错，将默认每 30 秒重新启动一次。要调整此间隔，您可以创建一个新的 `XtkWorkflow_WatchdogRestartTimerTimeout` 选项并设置整数数据类型以指定新延迟。此选项只应在技术工作流中启用。[了解更多信息](../../automation/workflow/workflow-properties.md#execution)

### 安全性改进 {#security-8-6-4}

通过 **[!UICONTROL Adobe Experience Cloud]** 外部帐户与 Adobe 解决方案和应用程序的连接已更新，以加强安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 兼容性更新 {#comp-8-6-4}

添加了以下 FDA 连接器。请参见[此页面](compatibility-matrix.md#FederatedDataAccessFDA)。

* 现在支持将 Databricks 用作 Adobe Campaign 联合数据访问 (FDA) 的外部数据库。

* 现已提供新的 Amazon Redshift FDA ODBC 连接器。它提供了改进的连接性、更轻松的维护以及增强的兼容性。此新版本提供了以下改进：

   * 新的连接器基于 ODBC 接口，该接口兼容我们最新的 FDA 连接器。这可确保实现长期支持。
   * 它还引入了一种使用 s3 存储桶的新数据加载机制，显著提高了性能。

  仍可使用旧版连接器。如果您想要试用新版，请联系您的 Adobe 代表。

### 修复 {#fixes-8-6-4}

此版本中修复了以下问题：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512、NEO-81520、NEO-81566、NEO-81704、NEO-81908、NEO-82195、NEO-82591、NEO-82592、NEO-82640、NEO-82665、NEO-82781、NEO-82920、NEO-83081、NEO-83096、NEO-83137、NEO-83143。

