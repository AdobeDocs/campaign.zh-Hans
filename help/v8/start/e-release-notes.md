---
title: 早期 Campaign v8 发行说明
description: 早期 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 0b4fc6da8761d2efe57d8eb0ff87cd11d0e2d250
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 74%

---

# 早期发行说明 {#e-new-release}

此页面介绍了下一个 Campaign v8 版本中包含的改进和修复。**以下早期发行说明在发行可用日期之前如有更改，恕不另行通知**。链接、屏幕和更新的文档会于发布日期在[发行说明](release-notes.md)中发布。

<!--
## Release 8.7.2 {#release-8-7-2}

_July 30, 2024_


>[!AVAILABILITY]
>
>This release is in **Limited Availability** (LA). It is restricted to customers migrating **from Adobe Campaign Standard to Adobe Campaign v8**, and cannot be deployed on any other environment.
>
>As a Campaign Standard user transitioning to Campaign v8, learn more about this transition in [Campaign v8 web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### New features {#new-8-7-2}

* **New SMS sending connector** - The SMS sending connector has been modernized and improved to enable transceiver mode SMPP connections, enable persistent SMPP connections, and ensure better compatibility for environments transitioning from Adobe Campaign Standard. A new SMS External account is now available for all new SMS implementations. Existing implementation are still supported, however recommendation is to move to this new modern and extended connector.

* **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 

* **Branding** - Branding options are now available for all channels, including SMS and Direct mail. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html){target="_blank"}


### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-76039, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-76663, NEO-73602, NEO-72915, NEO-78134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-76926, NEO-76495, NEO-77168, NEO-41058, NEO-75581, NEO-74647, NEO-74585, NEO-74586, NEO-74831, NEO-77319, NEO-78607.
-->

## 版本 8.6.3 {#release-8-6-3}

_2024年7月30日_

### 新增功能 {#new-8-6-3}

* **富推送通知** — 您现在可以发送富推送通知。 富媒体推送通知是移动通知的一种增强形式，它超越了简单的文本消息，融合了图像、交互式按钮或其他富媒体内容等多媒体元素。在此版本中，现在为您的iOS和Android应用程序提供了一组富推送通知模板。 [了解更多信息](../send/rich-push-android.md)。

* 从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。[了解详情](release-notes.md#change-8-7-1)

### 一般改进 {#improvements-8-6-3}

* 为提高应用程序之间所有通信的安全性，现在外部 API 调用支持 mTLS。

### 修复 {#fixes-8-6-3}

此版本中修复了以下问题：

NEO-77014、NEO-76958、NEO-76097、NEO-75898、NEO-72504、NEO-70263、NEO-67620、NEO-63197、NEO-58596、NEO-56832。

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->