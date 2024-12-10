---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e0dbeb7402a46f76a26c28dd226bc069d52f2609
workflow-type: ht
source-wordcount: '422'
ht-degree: 100%

---

# 最新版本 {#latest-release}

此页面列出了 Campaign v8（控制台）最新版本中的新增功能、改进和修复。要详细了解 Campaign 版本和升级，请参阅[此页面](upgrades.md)。

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
