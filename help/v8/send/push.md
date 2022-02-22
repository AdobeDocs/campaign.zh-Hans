---
title: 使用Adobe Campaign发送推送通知
description: Campaign中推送通知入门
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 6fc085d59c75399b08be44cc1647083677ed337e
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 3%

---

# 创建和发送推送通知

移动设备应用程序投放允许您向iOS和Android系统发送通知。

要在Adobe Campaign中发送推送通知，您需要：

1. 配置Campaign环境
1. 为移动应用程序创建移动应用程序类型信息服务。
1. 将应用程序的iOS和Android版本添加到此服务。
1. 为iOS和Android创建投放。

![](../assets/do-not-localize/book.png) 了解如何开始使用 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target=&quot;_blank&quot;}

## 与AdobeSDK集成

### 集成Campaign SDK

Campaign SDK可帮助您将移动应用程序集成到Adobe Campaign平台。

中列出了兼容的SDK版本 [Campaign兼容性矩阵](../start/compatibility-matrix.md#MobileSDK).

![](../assets/do-not-localize/glass.png) 了解如何在 [此部分](../config/push-config.md)

<!--
### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

![](../assets/do-not-localize/book.png) Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target="_blank"}

-->

## 在Campaign中配置应用程序设置

您必须在Adobe Campaign中定义iOS和Android应用程序设置。

![](../assets/do-not-localize/book.png) 有关iOS的配置准则，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages){target=&quot;_blank&quot;}

![](../assets/do-not-localize/book.png) Android的配置准则详见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target=&quot;_blank&quot;}

## 创建您的第一个推送通知

本节详细介绍特定于iOS和Android通知交付的元素。

>[!CAUTION]
>
>现在，使用Campaign v8进行移动注册 **异步**. [了解详情](../dev/staging.md)

要创建新投放，请浏览 **[!UICONTROL Campaigns]** ，单击 **[!UICONTROL Deliveries]** ，然后单击 **[!UICONTROL Create]** 按钮。

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) 有关如何创建投放的全局信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### 在iOS上发送通知 {#send-notifications-on-ios}

1. 选择 **[!UICONTROL Deliver on iOS]** 投放模板并单击 **[!UICONTROL Continue]**.

   ![](assets/push-template-ios.png)

1. 要定义通知的目标，请单击 **[!UICONTROL To]** 链接，然后单击 **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. 选择 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，选择与移动应用程序相关的服务，然后选择应用程序的iOS版本。

   ![](assets/push-ios-subscribers.png)

1. 选择通知类型： **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** 或 **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. 在 **[!UICONTROL Title]** 字段，输入要在通知中显示的标题标签。

1. 输入 **[!UICONTROL Message]** 和 **[!UICONTROL Value of the badge]** 基于所选通知类型。

1. 您还可以定义以下元素：

   * 的 **[!UICONTROL Action button]** 用于为警报通知中显示的操作按钮定义标签(**action_loc_key** 字段)。

   * 在 **[!UICONTROL Play a sound]** 字段中，选择要在收到通知时由移动终端播放的声音。

   * 在 **[!UICONTROL Application variables]** 字段，输入每个变量的值。 例如，您可以配置在用户激活通知时显示的特定应用程序屏幕。

1. 配置通知后，单击 **[!UICONTROL Preview]** 选项卡来预览通知。

   ![](assets/push-ios-preview.png)


### 在Android上发送通知 {#send-notifications-on-android}

1. 选择 **[!UICONTROL Deliver on Android (android)]** 投放模板。

   ![](assets/push-template-android.png)

1. 要定义通知的目标，请单击 **[!UICONTROL To]** 链接，然后单击 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 选择 **[!UICONTROL Subscribers of an Android mobile application]**，选择与移动应用程序相关的服务（在本例中为Neotrips），然后选择应用程序的Android版本。

   ![](assets/push-ios-subscribers.png)

1. 然后输入通知的内容。

   ![](assets/push-android-content.png)

1. 单击 **[!UICONTROL Insert emoticon]** 图标将表情符号插入推送通知。

1. 在 **[!UICONTROL Application variables]** 字段，输入每个变量的值。 例如，您可以配置在用户激活通知时显示的特定应用程序屏幕。

1. 配置通知后，单击 **[!UICONTROL Preview]** 选项卡来预览通知。

   <!--![](assets/push-android-preview.png)-->

## 测试、发送和监视推送通知

要发送校样并发送最终投放，请使用与电子邮件投放相同的流程。 请参阅 Campaign Classic v7 文档以了解详情：

* 验证投放并发送校样
   ![](../assets/do-not-localize/book.png) [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}

* 确认并发送投放
   ![](../assets/do-not-localize/book.png) [了解发送投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en){target=&quot;_blank&quot;}

发送消息后，您可以监控和跟踪投放内容。 请参阅 Campaign Classic v7 文档以了解详情：

* 推送通知隔离
   ![](../assets/do-not-localize/book.png) [了解有关推送通知隔离的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines){target=&quot;_blank&quot;}

* 故障排除
   ![](../assets/do-not-localize/book.png) [了解如何排查推送通知故障](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en){target=&quot;_blank&quot;}
