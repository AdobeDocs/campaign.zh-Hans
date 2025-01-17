---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 0c11cdd3c0b623333e6a7cff66c734f18e3d3985
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 51%

---

# 最新版本 {#latest-release}

本页列出了Campaign v8 （控制台）**最新版本**&#x200B;中的新功能、改进和修复。 在[此页面](upgrades.md)中了解有关Campaign版本、版本和升级的详细信息。 其他版本列于本文档的先前版本部分。

## 版本 8.6.4 {#release-8-6-4}

_2025年1月15日_

### 一般改进 {#improvements-8-6-4}

* 在[Enterprise (FFDA)部署](../../v8/architecture/enterprise-deployment.md)上下文中的投放分析期间，营销活动应用程序稳定性已得到改进。
* 此版本附带改进和增强的FFDA架构机制，包括密钥管理、暂存和数据复制。
* 已为[企业(FFDA)部署](../../v8/architecture/enterprise-deployment.md)引入新的技术工作流。 这些工作流通过将并行复制请求集中到相应的表中，来复制投放和相关数据。 这些工作流以`Replicate nms`开头。
* 工作流属性中现在有新的&#x200B;**启用监视程序监督器以保持工作流永久运行**&#x200B;选项。 启用此选项后，工作流会在发生错误后自动重新启动。 如果工作流仍然出错，默认情况下，每30秒重新启动一次。 要调整此间隔，您可以创建一个新的`XtkWorkflow_WatchdogTimerTimeout`选项并设置Integer数据类型以指定新延迟。 此选项只应在技术工作流中启用。 [了解更多信息](../../automation/workflow/workflow-properties.md#execution)

### 安全性改进 {#security-8-6-4}

已更新通过&#x200B;**[!UICONTROL Adobe Experience Cloud]**&#x200B;外部帐户与Adobe解决方案和应用程序的连接，以加强安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 兼容性更新 {#comp-8-6-4}

现在支持将 Databricks 用作 Adobe Campaign 联合数据访问 (FDA) 的外部数据库。请参阅[此页面](compatibility-matrix.md#FederatedDataAccessFDA)以了解详情。

### 修复 {#fixes-8-6-4}

此版本中修复了以下问题：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512 NEO-81520， NEO-81566， NEO-81704， NEO-81908， NEO-82195， NEO-82591， NEO-82592， NEO-82640， NEO-82665， NEO-82781， NEO-82920， NEO-83081 83096 83137 83143。

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

* **品牌化** - 品牌化选项现在可用于所有渠道，包括短信和直邮。[了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-hans){target="_blank"}

### 修复 {#fixes-8-7-2}

此版本中修复了以下问题：

NEO-48232、NEO-56832、NEO-72504、NEO-74855、NEO-75898、NEO-76097、NEO-76958、NEO-77014、NEO-77795、NEO-78843、NEO-79328。