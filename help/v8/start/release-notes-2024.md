---
title: Campaign v8（控制台） 2023年发行说明
description: 2023 Campaign v8 版本的功能和改进列表
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: 07e0bfdade0356eedb24641259aa754fdb1c6155
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 91%

---

# 2024版发行说明 {#2024-rn}

此页面列出了&#x200B;**2024 Campaign v8版本**&#x200B;中的新功能、改进和修复。



## 版本 8.5.3 {#release-8-5-3}

_2024 年 5 月 28 日_

### 迁移到 OAuth 服务器到服务器凭据 {#change-8-5-3}

从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。[了解详情](#change-8-7-1)

### 修复 {#fixes-8-5-3}

此版本中修复了以下问题：

NEO-70263、NEO-64984、NEO-63657、NEO-63387、NEO-62964、NEO-62750、NEO-62686、NEO-59544、NEO-52542


## 5 月更新 {#may-updates}

以下更改已在 5 月发布，现在可供 Campaign v8 用户使用：

* **新的增强安全性加载项**：为了使网络连接更安全并为资源提供更好的安全性，Adobe Campaign 提供了新的增强安全性加载项，其中包括两项功能：安全 CMK 集成和安全 VPN 隧道。[了解更多信息](../config/enhanced-security.md)


## 版本 8.7.1 {#release-8-7-1}

_2024 年 5 月 2 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#new-8-7-1}

* **富媒体推送通知模板** - 您现在可以通过 Android 发送富媒体推送通知。富媒体推送通知是移动通知的一种增强形式，它超越了简单的文本消息，融合了图像、交互式按钮或其他富媒体内容等多媒体元素。[了解更多信息](../send/rich-push-ios.md)。

* **品牌化** - 作为 Campaign Standard 迁移用户，您的技术管理员现在可以定义一个或多个品牌，以集中处理影响品牌标识的参数。其中包括品牌徽标、登陆页面访问 URL 的域名或消息跟踪设置。您可以创建这些品牌并将它们链接到消息或登陆页面。此配置在模板中进行管理。[了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-hans){target="_blank"}

* **Rest API** - 作为 Campaign Standard 迁移用户，您可以使用 Rest API 为 Adobe Campaign 创建集成，并通过将 Adobe Campaign 与所使用的技术面板连接来构建自己的生态系统。[了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=zh-hans){target="_blank"}

* **动态报告** - 作为 Campaign Standard 迁移用户，您可以访问动态报告，该功能提供完全可自定义的实时报告来衡量营销活动的影响。它增加了对用户档案数据的访问，除打开数和点击数等功能性电子邮件营销活动数据外，还支持按用户档案维度（如性别、城市和年龄）进行人口统计分析。[了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=zh-hans){target="_blank"}

### 兼容性更新 {#comp-8-7-1}

* 现在支持将 Databricks 用作 Adobe Campaign 联合数据访问 (FDA) 的外部数据库。请参阅[此页面](compatibility-matrix.md#FederatedDataAccessFDA)以了解详情。

### 迁移到 OAuth 服务器到服务器凭据 {#change-8-7-1}

从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。出站集成时，Adobe 将从 JWT 迁移到 OAuth，例如 Campaign-Analytics 集成或 Experience Cloud Triggers 集成。

如果您已实施与 Campaign 的入站集成，则必须迁移技术帐户，详情请参阅[本文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}。**2025 年 1 月 27 日**&#x200B;前，现有服务帐户 (JWT) 凭据仍将有效。

### 一般改进 {#improvements-8-7-1}

* 多个架构已从 32 位更改为 64 位。这仅适用于从 Campaign Standard 迁移的客户。[了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=zh-Hans){target="_blank"}

* 在 Campaign 表中，现在默认按服务器日期和时间填充以下属性：`lastModified` 和 `created`。默认情况下，`createdBy-id` 属性值现在使用当前登录 ID 填充。 将忽略用户在 API 调用中提供的值。<!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* 为提高应用程序之间所有通信的安全性，现在外部 API 调用支持 mTLS。

### 修复 {#fixes-8-7-1}

此版本中修复了以下问题：

NEO-72648、NEO-71534、NEO-71473、NEO-70263、NEO-70195、NEO-69651、NEO-68704、NEO-68192、NEO-67814、NEO-67702、NEO-67620、NEO-66022、NEO-65774、NEO-65633、NEO-64199、NEO-63706、NEO-63705、NEO-63287、NEO-63197、NEO-62575、NEO-60250、NEO-60192、NEO-58596、NEO-58314、NEO-58004、NEO-40054


## 版本 8.6.2 {#release-8-6-2}

_2024 年 2 月 23 日_

### 修复 {#fixes-8-6-2}

此版本修复了以下问题：

* 修复了中间源实例上可能出现的性能问题 (NEO-72595)。

## 版本 8.6.1 {#release-8-6-1}

_2024 年 2 月 14 日_

### 新增功能 {#new-8-6-1}

* 从此版本开始，您可以访问新的 **Campaign Web 用户界面**，该界面可通过中央 Adobe Experience Cloud 环境使用。Experience Cloud 是 Adobe 的数字营销应用程序、产品和服务的集成系列。通过其直观的界面，您可以快速访问云应用程序、产品功能和服务。[在此页面中](campaign-ui.md#ac-web-ui)了解如何连接到 Adobe Experience Cloud 并访问 Adobe Campaign Web 界面。


* Adobe Campaign v8 现已集成 **Adobe Experience Manager as a Cloud Service**，仅通过 Adobe Campaign Web 用户界面提供创作功能。[了解详情](../connect/ac-aem.md)

* 现在，如何在 Adobe Campaign 实例上安装了与 Adobe Experience Cloud 包的集成，您可以将 **Adobe Experience Manager Assets 库**&#x200B;与 Experience Cloud Assets 一起使用。[了解详情](../connect/ac-aem.md#assets-library)

### 一般改进 {#improvements-8-6-1}

* Campaign v8.6 提高了&#x200B;**电子邮件投放跟踪指标的吞吐量**。通过我们优化的流程，可以减少跟踪收录和计算时间，并且可以更快地检查投放关键指标。


### 可投放性更新 {#deliverability-8-6-1}

* 到 2024 年 2 月，任何通过 Google 或 Yahoo! 发送超过 5000 封电子邮件的公司将必须开始使用身份验证技术，即“基于域的邮件身份验证、报告和符合性”(DMARC)。确保为您在 Adobe Campaign 中使用的所有子域设置 DMARC 记录。[了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=zh-Hans){target="_blank"}

* 自 2024 年 6 月 1 日起，Google 和 Yahoo! 将要求发件人使用一键式 List-Unsubscribe 功能。Adobe Campaign 现在支持此选项。[了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=zh-Hans#one-click-list-unsubscribe){target="_blank"}


### 修复 {#fixes-8-6-1}

此版本中修复了以下问题：

NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406、NEO-61580 -61199， NEO-60786， NEO-59544， NEO-59198， NEO-59059， NEO-58637 55197 52542 50488 47789