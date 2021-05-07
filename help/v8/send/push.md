---
solution: Campaign
product: Adobe Campaign
title: 发送带Adobe Campaign的推送通知
description: 开始使用活动中的推送通知
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# 创建和发送推送通知

移动应用程序投放可让您向iOS和Android系统发送通知。

要在Adobe Campaign中发送推送通知，您需要：

1. 配置活动环境
1. 为您的移动应用程序创建移动应用程序类型信息服务。
1. 将应用程序的iOS和Android版本添加到此服务。
1. 为iOS和Android创建投放。

:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)中开始使用移动应用程序

## 与Adobe SDK集成

### 集成活动 SDK

活动 SDK简化了移动应用程序与Adobe Campaign平台的集成。

:arrow_upper_right:了解如何在[活动文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)中将Campaign Classic SDK与您的应用程序集成

### 在启动中配置活动扩展

您可以通过利用活动扩展，将Adobe Experience Platform Launch SDK与Campaign Classic集成。

:arrow_upper_right:了解有关[Adobe Mobile SDK文档的更多信息](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## 在活动中配置应用程序设置

您必须在Adobe Campaign中定义iOS和Android应用程序设置。

:arrow_upper_right:[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)中详细介绍了iOS的配置准则

:arrow_upper_right:[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)中详细介绍了Android的配置准则

## 创建您的第一个推送通知

:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)中创建您的第一个推送通知
