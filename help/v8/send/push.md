---
product: Adobe Campaign
title: 使用Adobe Campaign发送推送通知
description: Campaign中推送通知入门
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# 创建和发送推送通知

移动设备应用程序投放允许您向iOS和Android系统发送通知。

要在Adobe Campaign中发送推送通知，您需要：

1. 配置Campaign环境
1. 为移动应用程序创建移动应用程序类型信息服务。
1. 将应用程序的iOS和Android版本添加到此服务。
1. 为iOS和Android创建投放。

[!DNL :arrow_upper_right:] 在v7文档中了解如何开始使用移 [动应用程序](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## 与AdobeSDK集成

### 集成Campaign SDK

Campaign SDK可帮助您将移动应用程序集成到Adobe Campaign平台。

[!DNL :arrow_upper_right:] 在v7文档中了解如何将Campaign SDK与您的应 [用程序集成](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### 在Launch中配置Campaign扩展

您可以利用Campaign Classic扩展，将Adobe Experience Platform Launch SDK与Campaign集成。

[!DNL :arrow_upper_right:] 请参阅 [AdobeMobile SDK文档](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## 在Campaign中配置应用程序设置

您必须在Adobe Campaign中定义iOS和Android应用程序设置。

[!DNL :arrow_upper_right:] iOS的配置准则详见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

[!DNL :arrow_upper_right:] Campaign Classicv7文档中详细介绍了 [Android的配置准则](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## 创建您的第一个推送通知

[!DNL :arrow_upper_right:] 在v7文档中了解如何创建您的第 [一个推送通知](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>现在，使用Campaign v8进行移动注册的方式为&#x200B;**异步**。 [了解详情](../dev/staging.md)。
