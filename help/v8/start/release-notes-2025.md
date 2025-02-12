---
title: Campaign v8（控制台） 2025年发行说明
description: 2025 Campaign v8 版本的功能和改进列表
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 82622a4517356eaba1f7eba23d4b3050d8ca37c9
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 90%

---

# 2025 年发行说明 {#2025-rn}

此页面列出了&#x200B;**2025 Campaign v8版本**&#x200B;中的新功能、改进和修复。 [此页面](release-notes.md)中列出了最新版本。

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
