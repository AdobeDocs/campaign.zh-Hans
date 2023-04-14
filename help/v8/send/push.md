---
title: 使用Adobe Campaign发送推送通知
description: Campaign中推送通知入门
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: e7c255d30e38c4e17779ef820e8984668ac5d48b
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%

---

# 创建和发送推送通知{#push-notifications-create}

移动设备应用程序投放允许您向iOS和Android设备发送通知。

要在Adobe Campaign中发送推送通知，您需要：

1. 将SDK与您的应用程序集成。 [了解详情](#push-sdk)
1. 为移动设备应用程序创建移动设备应用程序类型信息服务，并将应用程序的iOS和Android版本添加到该服务。 [了解详情](#push-config)
1. 为iOS和Android创建投放。 [了解详情](#push-create)

## 集成SDK {#push-sdk}

要通过Adobe Campaign发送推送通知，您必须在Adobe Experience Platform Mobile SDK的数据收集UI中配置Adobe Campaign扩展。

Adobe Experience Platform Mobile SDK可帮助在您的移动设备应用程序中为Adobe的Experience Cloud解决方案和服务提供支持。 SDK配置通过数据收集UI进行管理，以实现灵活配置和基于规则的可扩展集成。

[在Adobe Developer文档中了解详情](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.


## 在Campaign中配置应用程序设置{#push-config}

在发送推送通知之前，您必须在Adobe Campaign中定义iOS和Android应用程序设置。

推送通知通过专用服务发送给您的应用程序用户。 用户安装您的应用程序时，会订阅此服务：Adobe Campaign依赖此服务来仅定位应用程序的订阅者。 在此服务中，您需要添加iOS和Android应用程序，才能在iOS和Android设备上发送。

要创建发送推送通知的服务，请执行以下步骤：

1. 浏览到 **[!UICONTROL Profiles and Targets > Services and Subscriptions]** ，然后单击 **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. 输入 **[!UICONTROL Label]** 和 **[!UICONTROL Internal name]**，然后选择 **[!UICONTROL Mobile application]** 类型。

   >[!NOTE]
   >
   >默认 **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** 目标映射已链接到收件人表。 如果要使用其他目标映射，则需要创建新的目标映射，并在 **[!UICONTROL Target mapping]** 字段。 了解有关 [本页](../audiences/target-mappings.md).

1. 然后，使用 **[!UICONTROL Add]** 图标来定义使用此服务的移动设备应用程序。

>[!BEGINTABS]

>[!TAB iOS]

要为iOS设备创建应用程序，请执行以下步骤：

1. 选择 **[!UICONTROL Create an iOS application]** 并单击 **[!UICONTROL Next]**。

   ![](assets/new-ios-app.png){width="600" align="left"}

1. 在 **[!UICONTROL Label]** 字段。
1. （可选）您可以使用 **[!UICONTROL Application variables]**. 这些任务是完全可自定义的，并且是发送到移动设备的消息有效负荷的一部分。

   在以下示例中， **mediaURL** 和 **mediaExt** 变量会被添加以创建富推送通知，然后向应用程序提供要在通知中显示的图像。

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. 浏览到 **[!UICONTROL Subscription parameters]** 选项卡，以定义具有 **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** 架构。

1. 浏览到 **[!UICONTROL Sounds]** 选项卡来定义要播放的声音。 单击 **[!UICONTROL Add]** 填充 **[!UICONTROL Internal name]** 字段，其中必须包含应用程序中嵌入的文件名称或系统声音的名称。

1. 单击 **[!UICONTROL Next]** 以开始配置开发应用程序。

1. 集成密钥特定于每个应用程序。 它将移动应用程序链接到Adobe Campaign。

   确保相同 **[!UICONTROL Integration key]** 在Adobe Campaign中和通过SDK在应用程序代码中定义。

   在 [开发人员文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 的 **[!UICONTROL Integration key]** 可通过字符串值完全自定义，但必须与SDK中指定的值完全相同。
   >
   > 不能将相同的证书用于应用程序的开发版本（沙盒）和生产版本。

1. 从 **[!UICONTROL Application icon]** 字段来个性化服务中的移动应用程序。

1. 选择 **[!UICONTROL Authentication mode]**。有两种模式可用：

   * （推荐） **[!UICONTROL Token-based authentication]**:填写APNs连接设置 **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** 和 **[!UICONTROL Bundle Id]** 然后，单击 **[!UICONTROL Enter the private key...]**. 更多信息 **[!UICONTROL Token-based authentication]**，请参阅 [Apple文档](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**:单击 **[!UICONTROL Enter the certificate...]**  然后，选择p12密钥并输入由移动应用程序开发人员提供的密码。
   您稍后可以在 **[!UICONTROL Certificate]** 选项卡。

1. 使用 **[!UICONTROL Test the connection]** 按钮以验证您的配置。

1. 单击 **[!UICONTROL Next]** 要开始配置生产应用程序，请按照与上面所述相同的步骤操作。

1. 单击 **[!UICONTROL Finish]**。

您的iOS应用程序现已准备就绪，可在Campaign中使用。

>[!TAB Android]

要为Android设备创建应用程序，请执行以下步骤：

1. 选择 **[!UICONTROL Create an Android application]** 并单击 **[!UICONTROL Next]**。

   ![](assets/new-android-app.png){width="600" align="left"}

1. 在 **[!UICONTROL Label]** 字段。
1. 集成密钥特定于每个应用程序。 它将移动应用程序链接到Adobe Campaign。

   确保相同 **[!UICONTROL Integration key]** 在Adobe Campaign中和通过SDK在应用程序代码中定义。

   在 [开发人员文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > 的 **[!UICONTROL Integration key]** 可通过字符串值完全自定义，但必须与SDK中指定的值完全相同。

1. 从 **[!UICONTROL Application icon]** 字段来个性化服务中的移动应用程序。
1. 选择 **HTTP v1** in  **[!UICONTROL API version]** 下拉列表。
1. 单击 **[!UICONTROL Load project json file to extract project details...]** 链接以加载JSON密钥文件。 有关如何提取JSON文件的更多信息，请参阅 [Google Firebase文档](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   您还可以手动输入以下详细信息：
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. 使用 **[!UICONTROL Test the connection]** 按钮以验证您的配置。

   >[!CAUTION]
   >
   >的 **[!UICONTROL Test connection]** 按钮不会检查MID服务器是否有权访问FCM服务器。

1. （可选）您可以使用 **[!UICONTROL Application variables]** （如果需要）。 这些任务是完全可自定义的，并且是发送到移动设备的消息有效负荷的一部分。

1. 单击 **[!UICONTROL Finish]**，然后单击 **[!UICONTROL Save]**。您的Android应用程序现已准备就绪，可在Campaign中使用。

以下是用于进一步个性化推送通知的FCM有效负载名称：

| 消息类型 | 可配置消息元素（FCM有效负载名称） | 可配置选项（FCM有效负载名称） |
|:-:|:-:|:-:|
| 数据消息 | N/A | validate_only |
| 通知消息 | 标题， body， android_channel_id，图标，声音，标记，颜色， click_action，图像， ticker，置顶，可见性， notification_priority， notification_count <br> | validate_only |


>[!ENDTABS]


## 创建您的第一个推送通知{#push-create}

本节详细介绍特定于iOS和Android通知交付的元素。

>[!CAUTION]
>
>在 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，则移动注册现在为 **异步**. [了解详情](../architecture/staging.md)

要创建新投放，请浏览 **[!UICONTROL Campaigns]** ，单击 **[!UICONTROL Deliveries]** ，然后单击 **[!UICONTROL Create]** 按钮。

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

要在iOS设备上发送通知，请执行以下步骤：

1. 选择 **[!UICONTROL Deliver on iOS]** 投放模板。

   ![](assets/push_ios_1.png)

1. 要定义通知的目标，请单击 **[!UICONTROL To]** 链接，然后单击 **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. 选择 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，选择与移动应用程序相关的服务，然后选择应用程序的iOS版本。

   ![](assets/push_ios_3.png)

1. 选择 **[!UICONTROL Notification type]** 介于 **[!UICONTROL General notification (Alert, Sound, Badge)]** 或 **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >的 **静默推送** 模式允许向移动应用程序发送“静默”通知。 用户未知晓通知的到达。 它将直接转给应用程序。

1. 在 **[!UICONTROL Title]** 字段，输入要在通知中心提供的通知列表中显示的标题标签。

   利用此字段，可定义 **标题** iOS通知有效负载的参数。

1. 您可以添加 **[!UICONTROL Subtitle]**，值 **字幕** iOS通知有效负载的参数。

1. 在 **[!UICONTROL Message content]** 的子菜单。

1. 从 **[!UICONTROL Sound and Badge]** 选项卡，您可以编辑以下选项：

   * **[!UICONTROL Clean Badge]**:启用此选项可刷新标记值。

   * **[!UICONTROL Value]**:设置一个数字，该数字将用于直接在应用程序图标上显示新的未读信息数。

   * **[!UICONTROL Critical alert mode]**:启用此选项，即使用户的手机设置为焦点模式或iPhone静音，也可向通知添加声音。

   * **[!UICONTROL Name]**:选择在收到通知时移动终端要播放的声音。

   * **[!UICONTROL Volume]**:音量从0到100。

      >[!NOTE]
      > 
      >必须在应用程序中包含声音，并在创建服务时定义声音。
   ![](assets/push_ios_5.png)

1. 从 **[!UICONTROL Application variables]** 选项卡， **[!UICONTROL Application variables]** 会自动添加。 例如，通过它们可定义通知行为，您可以将特定应用程序屏幕配置为在用户激活通知时显示。

1. 从 **[!UICONTROL Advanced]** 选项卡，您可以编辑以下常规选项：

   * **[!UICONTROL Mutable content]**:启用此选项，以允许移动应用程序下载媒体内容。

   * **[!UICONTROL Thread-id]**:用于将相关通知分组在一起的标识符。

   * **[!UICONTROL Category]**:将显示操作按钮的类别ID的名称。 这些通知为用户提供了一种更快的方式，无需在应用程序中打开或导航即可响应通知执行不同任务。

   ![](assets/push_ios_6.png)

1. 对于时间敏感通知，您可以指定以下选项：

   * **[!UICONTROL Target content ID]**:标识符，用于定位在打开通知时要转发的应用程序窗口。

   * **[!UICONTROL Launch image]**:要显示的launch图像文件的名称。 如果用户选择启动您的应用程序，则将显示选定的图像，而不是应用程序的启动屏幕。

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**:默认情况下，系统会立即显示通知、点亮屏幕并播放声音。 通知不会突破“焦点”模式。

      * **[!UICONTROL Passive]**:系统将通知添加到通知列表，而不会点亮屏幕或播放声音。 通知不会突破“焦点”模式。

      * **[!UICONTROL Time sensitive]** 系统会立即显示通知、点亮屏幕、播放声音并打破“聚焦”模式。 此级别不需要Apple的特殊许可。

      * **[!UICONTROL Critical]** 系统立即显示通知，将屏幕点亮，并绕过静音开关或聚焦模式。 请注意，此级别需要获得Apple的特殊许可。
   * **[!UICONTROL Relevance score]**:将相关性得分设置为0到100。 系统将使用它对通知摘要中的通知进行排序。

   ![](assets/push_ios_7.png)

1. 配置通知后，单击 **[!UICONTROL Preview]** 选项卡来预览通知。

   ![](assets/push-ios-preview.png)


>[!TAB Android]

要在Android设备上发送通知，请执行以下步骤：

1. 选择 **[!UICONTROL Deliver on Android (android)]** 投放模板。

   ![](assets/push-template-android.png)

1. 要定义通知的目标，请单击 **[!UICONTROL To]** 链接，然后单击 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 选择 **[!UICONTROL Subscribers of an Android mobile application]**，选择与移动应用程序相关的服务（在本例中为Neotrips），然后选择应用程序的Android版本。

   ![](assets/push-android-subscribers.png)

1. 然后输入通知的内容。

   ![](assets/push-android-content.png)

1. 单击 **[!UICONTROL Insert emoticon]** 图标将表情符号插入推送通知。

1. 在 **[!UICONTROL Application variables]** 字段，输入每个变量的值。 例如，您可以配置在用户激活通知时显示的特定应用程序屏幕。

1. 配置通知后，单击 **[!UICONTROL Preview]** 选项卡来预览通知。

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## 测试、发送和监视推送通知

要发送校样并发送最终投放，请使用与其他投放相同的流程。

了解如何在中验证投放 [本页](preview-and-proof.md).

了解如何确认和发送投放 [本页](send.md)

发送消息后，您可以监控和跟踪投放内容。 详细了解 [本页](delivery-failures.md#push-error-types).

