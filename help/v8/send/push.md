---
solution: Campaign v8
product: Adobe Campaign
title: 使用Adobe Campaign发送推送通知
description: Campaign中推送通知入门
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 1%

---

# 创建和发送推送通知

移动设备应用程序投放允许您向iOS和Android系统发送通知。

要在Adobe Campaign中发送推送通知，您需要：

1. 配置Campaign环境
1. 为移动应用程序创建移动应用程序类型信息服务。
1. 将应用程序的iOS和Android版本添加到此服务。
1. 为iOS和Android创建投放。

:arrow_upper_right:了解如何在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)中开始使用移动应用程序

## 与AdobeSDK集成

### 集成Campaign SDK

Campaign SDK可帮助您将移动应用程序集成到Adobe Campaign平台。

:arrow_upper_right:了解如何在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)中将Campaign SDK与您的应用程序集成

### 在Launch中配置Campaign扩展

您可以利用Campaign Classic扩展，将Adobe Experience Platform Launch SDK与Campaign集成。

:arrow_upper_right:请参阅[AdobeMobile SDK文档](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)，以了解更多信息

## 在Campaign中配置应用程序设置

您必须在Adobe Campaign中定义iOS和Android应用程序设置。

:arrow_upper_right:[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)中详细介绍了iOS的配置准则

:arrow_upper_right:[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)中详细介绍了Android的配置准则

## 创建您的第一个推送通知

:arrow_upper_right:了解如何在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)中创建第一个推送通知


>[!CAUTION]
>
>现在，使用Campaign v8进行移动注册的方式为&#x200B;**异步**。 [了解详情](../dev/staging.md)。
