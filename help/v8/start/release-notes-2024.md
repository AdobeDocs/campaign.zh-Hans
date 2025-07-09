---
title: Campaign v8（控制台）2024 发行说明
description: 2024 Campaign v8版本的功能和改进列表
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 90%

---

# 2024 年发行说明 {#2024-rn}

此页面列出了 **2024 Campaign v8 版本**&#x200B;中的新增功能、改进和修复。有关最新版本，请参阅[此页面](release-notes.md)。

对于任何新实施或升级到现有环境，请安装[最新版本](release-notes.md)。


>[!BEGINSHADEBOX]

**本页面内容**

* Campaign v8.7 - [版本 8.7.1](#release-8-7-1) | [版本 8.7.2](#release-8-7-2)
* Campaign v8.6 - [版本8.6.1](#release-8-6-1) | [版本8.6.2](#release-8-6-2) | [版本8.6.3](#release-8-6-3)
* Campaign v8.5 - [版本8.5.3](#release-8-5-3)

>[!ENDSHADEBOX]

## 版本 8.7.2 {#release-8-7-2}

_2024 年 9 月 3 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#new-8-7-2}

* **新短信发送连接器** - 短信发送连接器经过现代化改造和改进，可启用收发器模式 SMPP 连接、启用持久 SMPP 连接，并确保从 Adobe Campaign Standard 过渡的环境具有更好的兼容性。新的短信外部帐户现在可用于所有新的短信实施。现有实施仍受支持，但建议迁移到此新的现代化扩展连接器。[了解更多信息](../send/sms/sms.md)。

* **富媒体推送通知 (GA)** - 您现在可以发送富媒体推送通知。富媒体推送通知是移动通知的一种增强形式，它超越了简单的文本消息，融合了图像、交互式按钮或其他富媒体内容等多媒体元素。在此版本中，您可以为 iOS 和 Android 应用程序提供一组富媒体推送通知模板。[了解更多信息](../send/rich-push-android.md)。

* **品牌化** - 品牌化选项现在可用于所有渠道，包括短信和直邮。[了解更多信息](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

### 修复 {#fixes-8-7-2}

此版本中修复了以下问题：

NEO-48232、NEO-56832、NEO-72504、NEO-74855、NEO-75898、NEO-76097、NEO-76958、NEO-77014、NEO-77795、NEO-78843、NEO-79328。

## 版本 8.7.1 {#release-8-7-1}

_2024 年 5 月 2 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#new-8-7-1}

* **富媒体推送通知模板** - 您现在可以通过 Android 发送富媒体推送通知。富媒体推送通知是移动通知的一种增强形式，它超越了简单的文本消息，融合了图像、交互式按钮或其他富媒体内容等多媒体元素。[了解更多信息](../send/rich-push-ios.md)。

* **品牌化** - 作为 Campaign Standard 迁移用户，您的技术管理员现在可以定义一个或多个品牌，以集中处理影响品牌标识的参数。其中包括品牌徽标、登陆页面访问 URL 的域名或消息跟踪设置。您可以创建这些品牌并将它们链接到消息或登陆页面。此配置在模板中进行管理。[了解更多信息](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

* **Rest API** - 作为 Campaign Standard 迁移用户，您可以使用 Rest API 为 Adobe Campaign 创建集成，并通过将 Adobe Campaign 与所使用的技术面板连接来构建自己的生态系统。[了解更多信息](../dev/api/get-started-apis.md)

* **动态报告** - 作为 Campaign Standard 迁移用户，您可以访问动态报告，该功能提供完全可自定义的实时报告来衡量营销活动的影响。它增加了对轮廓数据的访问，除打开数和点击数等功能性电子邮件营销活动数据外，还支持按轮廓维度（如性别、城市和年龄）进行人口统计分析。[了解更多信息](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

### 兼容性更新 {#comp-8-7-1}

添加了以下 FDA 连接器。请参见[此页面](compatibility-matrix.md#FederatedDataAccessFDA)。

* 现在支持将 Databricks 用作 Adobe Campaign 联合数据访问 (FDA) 的外部数据库。

* 现已提供新的 Amazon Redshift FDA ODBC 连接器。它提供了改进的连接性、更轻松的维护以及增强的兼容性。此新版本提供了以下改进：

   * 新的连接器基于 ODBC 接口，该接口兼容我们最新的 FDA 连接器。这可确保实现长期支持。
   * 它还引入了一种使用 s3 存储桶的新数据加载机制，显著提高了性能。

  仍可使用旧版连接器。如果您想要试用新版，请联系您的 Adobe 代表。

### 迁移到 OAuth 服务器到服务器凭据 {#change-8-7-1}

从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。出站集成时，Adobe 将从 JWT 迁移到 OAuth，例如 Campaign-Analytics 集成或 Experience Cloud Triggers 集成。

如果您已实施与Campaign的入站集成，则必须迁移技术帐户，如[本文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}中所述。 现有服务帐户(JWT)凭据将继续工作，直到&#x200B;**2025年6月30日**。

### 一般改进 {#improvements-8-7-1}

* 多个架构已从 32 位更改为 64 位。这仅适用于从 Campaign Standard 迁移的客户。[了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=zh-Hans){target="_blank"}

* 在 Campaign 表中，现在默认按服务器日期和时间填充以下属性：`lastModified` 和 `created`。默认情况下，`createdBy-id` 属性值现在使用当前登录 ID 填充。 将忽略用户在 API 调用中提供的值。<!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* 为提高应用程序之间所有通信的安全性，现在外部 API 调用支持 mTLS。

### 修复 {#fixes-8-7-1}

此版本中修复了以下问题：

NEO-72648、NEO-71534、NEO-71473、NEO-70263、NEO-70195、NEO-69651、NEO-68704、NEO-68192、NEO-67814、NEO-67702、NEO-67620、NEO-66022、NEO-65774、NEO-65633、NEO-64199、NEO-63706、NEO-63705、NEO-63287、NEO-63197、NEO-62575、NEO-60250、NEO-60192、NEO-58596、NEO-58314、NEO-58004、NEO-40054



## 版本 8.6.3 {#release-8-6-3}

_2024 年 7 月 30 日_

### 新增功能 {#new-8-6-3}

* **富媒体推送通知** - 您现在可以发送富媒体推送通知。富媒体推送通知是移动通知的一种增强形式，它超越了简单的文本消息，融合了图像、交互式按钮或其他富媒体内容等多媒体元素。在此版本中，您可以为 iOS 和 Android 应用程序提供一组富媒体推送通知模板。[了解更多信息](../send/rich-push-android.md)。

* 从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。[了解详情](release-notes-2024.md#change-8-7-1)

### 一般改进 {#improvements-8-6-3}

* 为提高应用程序之间所有通信的安全性，现在外部 API 调用支持 mTLS。

### 修复 {#fixes-8-6-3}

此版本中修复了以下问题：

NEO-79328、NEO-78843、NEO-77795、NEO-77014、NEO-76958、NEO-76097、NEO-75898、NEO-72504、NEO-70263、NEO-67620、NEO-63197、NEO-58596、NEO-56832。

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## 2024年5月更新 {#may-updates}

以下更改已在 5 月发布，现在可供 Campaign v8 用户使用：

* **新的增强安全性加载项**：为了使网络连接更安全并为资源提供更好的安全性，Adobe Campaign 提供了新的增强安全性加载项，其中包括两项功能：安全 CMK 集成和安全 VPN 隧道。[了解更多信息](../config/enhanced-security.md)

## 版本 8.6.2 {#release-8-6-2}

_2024 年 2 月 23 日_

### 修复 {#fixes-8-6-2}

此版本修复了以下问题：

* 修复了中间源实例上可能出现的性能问题 (NEO-72595)。

## 版本 8.6.1 {#release-8-6-1}

_2024 年 2 月 14 日_

### 新增功能 {#new-8-6-1}

* 从此版本开始，您可以访问新的 **Campaign Web 用户界面**，该界面可通过中央 Adobe Experience Cloud 环境使用。Experience Cloud 是 Adobe 的数字营销应用程序、产品和服务的集成系列。通过其直观的界面，您可以快速访问云应用程序、产品功能和服务。[在此页面中](campaign-ui.md#ac-web-ui)了解如何连接到 Adobe Experience Cloud 并访问 Adobe Campaign Web 界面。

  >[!AVAILABILITY]
  >
  >Campaign Web 用户界面仅供通过 Adobe ID 连接到 Adobe Campaign 的用户使用。了解有关 [Adobe 身份管理系统 (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"} 的更多信息。
  >

* Adobe Campaign v8 现已集成 **Adobe Experience Manager as a Cloud Service**，仅通过 Adobe Campaign Web 用户界面提供创作功能。[了解详情](../connect/ac-aem.md)

* 现在，如何在 Adobe Campaign 实例上安装了与 Adobe Experience Cloud 包的集成，您可以将 **Adobe Experience Manager Assets 库**&#x200B;与 Experience Cloud Assets 一起使用。[了解详情](../connect/ac-aem.md#assets-library)

### 一般改进 {#improvements-8-6-1}

* Campaign v8.6 提高了&#x200B;**电子邮件投放跟踪指标的吞吐量**。通过我们优化的流程，可以减少跟踪收录和计算时间，并且可以更快地检查投放关键指标。


### 可投放性更新 {#deliverability-8-6-1}

* 到 2024 年 2 月，任何通过 Google 或 Yahoo! 发送超过 5000 封电子邮件的公司将必须开始使用身份验证技术，即“基于域的邮件身份验证、报告和符合性”(DMARC)。确保为您在 Adobe Campaign 中使用的所有子域设置 DMARC 记录。[了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=zh-Hans){target="_blank"}

* 自 2024 年 6 月 1 日起，Google 和 Yahoo! 将要求发件人使用一键式 List-Unsubscribe 功能。Adobe Campaign 现在支持此选项。[了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=zh-Hans#list-unsubscribe){target="_blank"}


### 修复 {#fixes-8-6-1}

此版本中修复了以下问题：

NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406、NEO-61580 NEO-61199， NEO-60786， NEO-59544， NEO-59198， NEO-59059， NEO-58637 55197 52542 50488 47789



## 版本 8.5.3 {#release-8-5-3}

_2024 年 5 月 28 日_

### 迁移到 OAuth 服务器到服务器凭据 {#change-8-5-3}

从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。[了解详情](#change-8-7-1)

### 修复 {#fixes-8-5-3}

此版本中修复了以下问题：

NEO-70263、NEO-64984、NEO-63657、NEO-63387、NEO-62964、NEO-62750、NEO-62686、NEO-59544、NEO-52542