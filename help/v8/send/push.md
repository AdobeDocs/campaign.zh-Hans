---
product: Adobe Campaign
title: 使用Adobe Campaign发送推送通知
description: Campaign中推送通知入门
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: 09979331284757527fc9a24479a53d2d488f4649
workflow-type: tm+mt
source-wordcount: '781'
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

本节详细介绍特定于iOS和Android通知交付的元素。

[!DNL :arrow_upper_right:] 有关创建推送通知的所有步骤，请参阅 [Campaign Classicv7文档](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en)

>[!CAUTION]
>
>使用Campaign v8时，移动注册现在为&#x200B;**异步**。 [了解详情](../dev/staging.md)

要创建新投放，请浏览&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL Deliveries]** ，然后单击现有投放列表上方的&#x200B;**[!UICONTROL Create]**&#x200B;按钮。

![](assets/delivery_step_1.png)

[!DNL :arrow_upper_right:] 有关如何创建投放的全局信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages)。

### 在iOS {#send-notifications-on-ios}上发送通知

1. 选择&#x200B;**[!UICONTROL Deliver on iOS]**&#x200B;投放模板，然后单击&#x200B;**[!UICONTROL Continue]**。

   ![](assets/push-template-ios.png)

1. 要定义通知的目标，请单击&#x200B;**[!UICONTROL To]**&#x200B;链接，然后单击&#x200B;**[!UICONTROL Add]**。

   ![](assets/push-ios-select-target.png)

1. 选择&#x200B;**[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，选择与移动设备应用程序相关的服务，然后选择应用程序的iOS版本。

   ![](assets/push-ios-subscribers.png)

1. 选择通知类型：**[!UICONTROL Alert]**、**[!UICONTROL Badge]**、**[!UICONTROL Alert and badge]**&#x200B;或&#x200B;**[!UICONTROL Silent Push]**。

   ![](assets/push-ios-alert.png)

1. 在&#x200B;**[!UICONTROL Title]**&#x200B;字段中，输入要在通知中显示的标题标签。

1. 根据所选通知类型输入&#x200B;**[!UICONTROL Message]**&#x200B;和&#x200B;**[!UICONTROL Value of the badge]**。

1. 您还可以定义以下元素：

   * **[!UICONTROL Action button]**&#x200B;允许您为出现在警报通知（有效负载的&#x200B;**action_loc_key**&#x200B;字段）中的操作按钮定义标签。

   * 在&#x200B;**[!UICONTROL Play a sound]**&#x200B;字段中，选择要在收到通知时由移动终端播放的声音。

   * 在&#x200B;**[!UICONTROL Application variables]**&#x200B;字段中，输入每个变量的值。 例如，您可以配置在用户激活通知时显示的特定应用程序屏幕。

1. 配置通知后，单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡以预览通知。

   ![](assets/push-ios-preview.png)

[!DNL :arrow_upper_right:] 有关在iOS上创建和发送推送通知的所有详细步骤，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)

### 在Android {#send-notifications-on-android}上发送通知

1. 选择&#x200B;**[!UICONTROL Deliver on Android (android)]**&#x200B;投放模板。

   ![](assets/push-template-android.png)

1. 要定义通知的目标，请单击&#x200B;**[!UICONTROL To]**&#x200B;链接，然后单击&#x200B;**[!UICONTROL Add]**。

   ![](assets/push-android-select-target.png)

1. 选择&#x200B;**[!UICONTROL Subscribers of an Android mobile application]**，选择与移动应用程序相关的服务（在本例中为Neotrips），然后选择应用程序的Android版本。

   ![](assets/push-ios-subscribers.png)

1. 然后输入通知的内容。

   ![](assets/push-android-content.png)

1. 单击&#x200B;**[!UICONTROL Insert emoticon]**&#x200B;图标以将表情符号插入推送通知。

1. 在&#x200B;**[!UICONTROL Application variables]**&#x200B;字段中，输入每个变量的值。 例如，您可以配置在用户激活通知时显示的特定应用程序屏幕。

1. 配置通知后，单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡以预览通知。

   <!--![](assets/push-android-preview.png)-->

[!DNL :arrow_upper_right:] 有关在Android上创建和发送推送通知的所有详细步骤，请参阅 [Campaign Classicv7文档](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-android)

## 测试、发送和监视推送通知

要发送校样并发送最终投放，请使用与电子邮件投放相同的流程。 请参阅Campaign Classicv7文档，以了解更多信息：

* 验证投放并发送校样
   [!DNL :arrow_upper_right:] [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

* 确认并发送投放
   [!DNL :arrow_upper_right:] [了解发送投放的关键步骤](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en)

发送消息后，您可以监控和跟踪投放内容。 请参阅Campaign Classicv7文档，以了解更多信息：

* 推送通知隔离
   [!DNL :arrow_upper_right:] [了解有关推送通知隔离的更多信息](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines)

* 故障排除
   [!DNL :arrow_upper_right:] [了解如何排查推送通知故障](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en)