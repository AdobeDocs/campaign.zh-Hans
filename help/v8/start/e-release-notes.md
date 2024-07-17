---
title: 早期 Campaign v8 发行说明
description: 早期 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 09b8ced170ff28b24713722e0a82852038053201
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 57%

---

# 早期发行说明 {#e-new-release}

此页面介绍了下一个 Campaign v8 版本中包含的改进和修复。**以下早期发行说明在发行可用日期之前如有更改，恕不另行通知**。链接、屏幕和更新的文档会于发布日期在[发行说明](release-notes.md)中发布。

## 版本 8.7.2 {#release-8-7-2}

_2024年7月30日_


>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#new-8-7-2}

* **新SMS发送连接器** - SMS发送连接器已进行现代化和改进，可启用收发器模式SMPP连接、启用永久性SMPP连接，并确保与从Adobe Campaign Standard过渡的环境之间有更好的兼容性。 新的短信外部帐户现在可用于所有新的短信实施。 现有实施仍受支持，但建议迁移到此新的现代化扩展连接器。

* **富推送通知(GA)** — 您现在可以发送富推送通知。 富媒体推送通知是移动通知的一种增强形式，它超越了简单的文本消息，融合了图像、交互式按钮或其他富媒体内容等多媒体元素。在此版本中，现在为您的iOS和Android应用程序提供了一组富推送通知模板。 [了解更多信息](../send/rich-push.md)。

* **品牌策略** — 品牌策略选项现在可用于所有渠道，包括短信和直邮。 [了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=zh-Hans){target="_blank"}

<!--
### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-76039, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-76663, NEO-73602, NEO-72915, NEO-78134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-76926, NEO-76495, NEO-77168, NEO-41058, NEO-75581, NEO-74647, NEO-74585, NEO-74586, NEO-74831, NEO-77319, NEO-78607.-->

## 版本 8.6.3 {#release-8-6-3}

_2024年7月30日_


### 新增功能 {#new-8-6-3}

* **富推送通知** — 您现在可以发送富推送通知。 富媒体推送通知是移动通知的一种增强形式，它超越了简单的文本消息，融合了图像、交互式按钮或其他富媒体内容等多媒体元素。在此版本中，现在为您的iOS和Android应用程序提供了一组富推送通知模板。 [了解更多信息](../send/rich-push.md)。

* 从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。[了解详情](release-notes.md#change-8-7-1)


### 一般改进 {#improvements-8-6-3}

* 为了提高应用程序之间所有通信的安全性，现在外部API调用支持mTLS。

<!--
### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:
-->