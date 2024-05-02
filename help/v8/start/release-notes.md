---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: b4f54deaf35c852012a88d1445268bce9be4e8c1
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 51%

---

# 最新版本{#latest-release}

Adobe Campaign 会定期更新。这种定期更新旨在让您掌握最新、最充分的信息，保持环境的安全，并改进您对我们产品的体验。Adobe强烈建议所有客户升级到最新版本。

作为托管云服务用户，您的实例会由 Adobe 通过每个新版本升级。Adobe 将与您联系并升级您的环境。Campaign 客户端控制台&#x200B;**必须升级到与 Campaign 服务器相同的版本**。通过此页面了解如何升级您的客户端控制台 [页面](../start/connect.md#upgrade-ac-console).

此外，作为客户，请确保您使用的是 [兼容性矩阵](compatibility-matrix.md).

## 版本 8.7.1 {#release-8-7-1}

_2024年5月2日_

>[!AVAILABILITY]
>
>此版本位于 **有限可用性** （洛杉矶）。 仅限于迁移的客户 **从Adobe Campaign Standard到Adobe Campaign v8**&#x200B;和无法部署在任何其他环境中。
>
>作为过渡到Campaign v8的Campaign Standard用户，请参阅 [Campaign Standard过渡到Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration) 和 [面向Campaign Standard用户的功能](https://experienceleague.adobe.com/docs/experience-cloud/campaign/campaign-standard-migration-home.html).

### 新增功能 {#new-8-7-1}

* **富推送通知模板**  — 您现在可以通过Android发送富推送通知。 富推送通知是移动通知的一种增强形式，它通过合并多媒体元素（如图像、交互式按钮或其他富媒体内容）而超出简单的文本消息。 [了解更多信息](../send/rich-push.md)

* **品牌化**  — 作为Campaign Standard迁移的用户，您的技术管理员现在可以定义一个或多个品牌，以集中处理影响品牌识别的参数。 其中包括品牌徽标、登陆页面访问 URL 的域名或消息跟踪设置。您可以创建这些品牌并将它们链接到消息或登陆页面。 此配置在模板中进行管理。 [了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html)

* **Rest API**  — 作为Campaign Standard迁移用户，您可以使用Rest API为Adobe Campaign创建集成，并通过将Adobe Campaign与您使用的技术面板连接来构建您自己的生态系统。 [了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html)

* **动态报告**  — 作为Campaign Standard迁移的用户，您可以访问动态报表，其中提供完全可自定义的实时报表以衡量营销活动的影响。 它增加了对用户档案数据的访问权限，从而除了功能电子邮件促销活动数据（如打开数和点击数）之外，还可按用户档案维度（如性别、城市和年龄）进行人口统计分析。 [了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html)

<!--
* **New Enhanced security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling.
-->

### 兼容性更新 {#comp-8-7-1}

数据库现在支持作为具有Adobe Campaign联合数据访问(FDA)的外部数据库。 请参阅[此页面](compatibility-matrix.md#FederatedDataAccessFDA)以了解详情。

### 一般改进 {#improvements-8-7-1}

* 多个架构已从32位更改为64位。 这仅适用于从Campaign Standard迁移的客户。 [阅读更多](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html)。

* 在Campaign表中，通过新标记可处理对lastModified、createdBy-id和createdBy-id属性的修改。 当标记打开时，用户提供给这些属性的值将被忽略。 仅使用来自用户上下文的服务器时间和ID。 当标记关闭时，将使用这些属性的用户提供的值。 ignoreTimestampsID标志位于serverConf.xml中的“共享”节点下。

### 修复 {#fixes-8-7-1}

本发行版中修复了以下问题：NEO-72648、NEO-71534、NEO-71473、NEO-70263、NEO-70195、NEO-69651、NEO-68704、NEO-68192、NEO-67814、NEO-67702、NEO-67620、NEO-66022、NEO-65774、NEO-65633、NEO-64199、NEO-63706、NEO-63705、NEO-63287、NEO-63197、NEO-62575， NEO-60250 60192 58596 58314 58004 40054

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

此版本修复了以下问题：
NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406、NEO-61580、NEO-61199、NEO-60786、NEO-59544、NEO-59198、NEO-59059、NEO-58637、NEO-55197、NEO-52542、NEO-50488、NEO-47789