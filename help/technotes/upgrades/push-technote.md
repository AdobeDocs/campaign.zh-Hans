---
product: campaign
title: 推送通知渠道即将更改
description: 推送通知渠道即将更改
hide: true
hidefromtoc: true
source-git-commit: 5ed6a5c9c458381ef701428aeab146afe4788d58
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 1%

---

# 推送通知渠道即将更改 {#push-upgrade}

您可以使用Campaign在Android设备上发送推送通知。 要执行此操作，Campaign需要依赖特定的订阅服务。 Android Firebase Cloud Messaging (FCM)服务的一些重要更改将于2024年发布，可能会影响Adobe Campaign实施。 您可能需要更新Android推送消息的订阅服务配置才能支持此更改。

## 更改了哪些内容？ {#fcm-changes}

作为Google持续努力改进其服务的一部分，旧版FCM API将在以下日期停用 **2024年6月20日**. 在中了解有关Firebase云消息HTTP协议的更多信息 [Google Firebase文档](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7和Adobe Campaign v8已支持用于发送推送通知消息的最新API。 但是，某些旧实施仍依赖旧版API。 必须更新这些实施。

## 您是否受影响？ {#fcm-impact}

如果您当前的实施支持使用旧版API连接到FCM的订阅服务，则您会受到影响。 为了避免任何服务中断，必须迁移到最新API。 在这种情况下，Adobe团队将会与您联系。

要检查您是否受到影响，您可以筛选 **服务和订阅** 根据以下过滤器：

![](assets/filter-services-fcm.png)


* 如果您的任何活动推送通知服务使用 **HTTP（旧版）** API，您的设置将直接受到此更改的影响。 您必须按照以下所述查看当前配置并迁移到较新的API。

* 如果您的设置仅使用 **HTTP v1** API用于Android推送通知，则您已符合要求，无需执行进一步操作。

## 如何迁移？ {#fcm-migration-procedure}

### 先决条件 {#fcm-migration-prerequisites}

* 对于Campaign Classicv7,20.3.1版本中添加了对HTTP v1的支持。 如果您的环境运行在旧版本上，则迁移到HTTP v1的先决条件是将您的环境升级到 [最新Campaign Classic版本](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. 对于Campaign v8，所有版本都支持HTTP v1，无需升级。

* 需要Android Firebase Admin SDK服务的帐户JSON文件才能将移动应用程序移动到HTTP v1。 了解如何在中获取此文件 [Google Firebase文档](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* 对于混合、托管和Managed Services部署，除了下面的迁移过程外，请联系Adobe以更新实时(RT)执行服务器。 不影响中间源服务器。

* 作为Campaign Classic v7内部部署用户，您必须同时升级营销和实时执行服务器。 不影响中间源服务器。

### 迁移过程 {#fcm-migration-steps}

要将环境迁移到HTTP v1，请执行以下步骤：

1. 浏览到您的列表 **服务和订阅**.
1. 使用列出所有移动应用程序 **HTTP（旧版）** api版本。
1. 对于这些移动设备应用程序中的每一个，设置 **API版本** 到 **HTTP v1**.
1. 单击 **[!UICONTROL Load project json file to extract project details...]** 用于直接加载JSON密钥文件的链接。

   您还可以手动输入以下详细信息：

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. 单击 **[!UICONTROL Test the connection]** 以检查您的配置是否正确，以及营销服务器是否有权访问FCM。 请注意，对于中间源部署， **[!UICONTROL Test connection]** 按钮无法检查服务器是否有权访问Android Firebase Cloud Messaging (FCM)服务。
1. 作为一个选项，您可以使用一些来扩充推送消息内容 **[!UICONTROL Application variables]** 如果需要。 这些都是完全可自定义的，并且是发送到移动设备的消息有效负载的一部分。
1. 单击 **[!UICONTROL Finish]**，然后单击 **[!UICONTROL Save]**。

以下是FCM有效负荷名称，用于进一步个性化您的推送通知。 这些选项是详细的 [此处](#fcm-apps).

| 消息类型 | 可配置消息元素（FCM有效负荷名称） | 可配置选项（FCM有效负荷名称） |
|:-:|:-:|:-:|
| 数据消息 | N/A | validate_only |
| 通知消息 | title，标题，正文， android_channel_id，图标，声音，标记，颜色， click_action，图像，滚动条，粘性，可见性， notification_priority，通知优先级， notification_count <br> | validate_only |


>[!NOTE]
>
>一旦在所有服务器中应用了这些更改，则交付到Android设备的所有新推送通知都将使用HTTP v1 API。 正在重试、进行中和正在使用的现有推送投放仍使用HTTP（旧版）API。

### 这对我的Android应用程序有何影响？ {#fcm-apps}

无需对Android移动应用程序的代码进行特定更改，通知行为不应发生变化。

但是，使用HTTP v1，您可以通过以下方式进一步个性化推送通知 **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)

您可以：

* 使用 **[!UICONTROL Ticker]** 用于设置通知的滚动条文本的字段。
* 使用 **[!UICONTROL Image]** 用于设置要在通知中显示的图像URL的字段。
* 使用 **[!UICONTROL Notification Count]** 字段，用于设置直接在应用程序图标上显示的新未读信息的数量。
* 设置 **[!UICONTROL Sticky]** 选项设置为false，以便在用户单击通知时自动将其关闭。 如果设置为true，则即使用户单击通知，也会显示通知。
* 设置 **[!UICONTROL Notification Priority]** 通知的级别为“默认”、“最小”、“低”或“高”。
* 设置 **[!UICONTROL Visibility]** 您向公共、私人或机密发送的通知的级别。

欲知详情，请参阅 **[!UICONTROL HTTP v1 additional options]** 以及如何填写这些字段，请参阅 [FCM文档](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.

