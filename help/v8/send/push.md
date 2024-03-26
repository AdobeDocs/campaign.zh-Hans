---
title: 使用Adobe Campaign发送推送通知
description: Campaign中的推送通知入门
feature: Push
role: User
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 6d54f072ad0e67b435cd6e03433fa9ddd0794dea
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 10%

---

# 创建和发送推送通知{#push-notifications-create}

移动应用程序投放可让您向iOS和Android设备发送通知。

在开始使用Adobe Campaign发送推送通知之前，您需要确保移动应用程序和Adobe Experience Platform中的标记已具有配置和集成。 [了解有关推送配置的更多信息。](push-settings.md)

>[!CAUTION]
>
>Android Firebase Cloud Messaging (FCM) 服务的一些重要更改将于 2024 年发布，并将影响您的 Adobe Campaign 实施。您可能需要更新 Android 推送消息的订阅服务配置，才能支持此更改。您已经可以检查并执行操作。 [了解详情](../../technotes/upgrades/push-technote.md)。


## 创建您的第一个推送通知{#push-create}

此部分详细介绍特定于iOS和Android通知投放的元素。

>[!IMPORTANT]
>
>在上下文中 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，移动注册现在为 **异步**. [了解详情](../architecture/staging.md)

要创建新投放，请浏览至 **[!UICONTROL Campaigns]** 选项卡，单击 **[!UICONTROL Deliveries]** 然后单击 **[!UICONTROL Create]** 按钮来指定现有投放列表的上方。

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

要在iOS设备上发送通知，请执行以下步骤：

1. 选择 **[!UICONTROL Deliver on iOS]** 投放模板。

   ![](assets/push_ios_1.png)

1. 要定义通知的目标，请单击 **[!UICONTROL To]** 链接，然后单击 **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. 选择 **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**，选择与您的移动应用程序相关的服务，然后选择应用程序的iOS版本。

   ![](assets/push_ios_3.png)

1. 选择您的 **[!UICONTROL Notification type]** 介于 **[!UICONTROL General notification (Alert, Sound, Badge)]** 或 **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >此 **静默推送** 模式允许向移动应用程序发送“静默”通知。 其中并不通知用户已送达通知。而是直接将通知传送到应用程序。

1. 在 **[!UICONTROL Title]** 字段，输入要显示在通知中心可用通知列表中的标题标签。

   此字段允许您定义 **标题** iOS通知有效负载的参数。

1. 您可以添加 **[!UICONTROL Subtitle]**，的值 **子标题** iOS通知有效负载的参数。

1. 在中输入消息的内容 **[!UICONTROL Message content]** 部分。

1. 从 **[!UICONTROL Sound and Badge]** 选项卡，可以编辑以下选项：

   * **[!UICONTROL Clean Badge]**：启用此选项以刷新标记值。

   * **[!UICONTROL Value]**：设置一个数字，该数字将用于直接在应用程序图标上显示新的未读信息数。

   * **[!UICONTROL Critical alert mode]**：启用此选项，以便在用户的手机设置为焦点模式或iPhone处于静音状态时向通知中添加声音。

   * **[!UICONTROL Name]**：选择在收到通知时移动终端要播放的声音。

   * **[!UICONTROL Volume]**：音量从0到100。

     >[!NOTE]
     > 
     >声音必须包含在应用程序中，并在创建服务时定义。
     >

   ![](assets/push_ios_5.png)

1. 从 **[!UICONTROL Application variables]** 选项卡，您的 **[!UICONTROL Application variables]** 都会自动添加。 它们允许您定义通知行为，例如，您可以配置在用户激活通知时显示的特定应用程序屏幕。

1. 从 **[!UICONTROL Advanced]** 选项卡，可以编辑以下常规选项：

   * **[!UICONTROL Mutable content]**：启用此选项可允许移动设备应用程序下载媒体内容。

   * **[!UICONTROL Thread-id]**：用于将相关通知分组的标识符。

   * **[!UICONTROL Category]**：将显示操作按钮的类别ID的名称。 这些通知为用户提供了一种更快的方式，无需在应用程序中打开或导航即可响应通知执行不同任务。

   ![](assets/push_ios_6.png)

1. 对于时效性通知，可以指定以下选项：

   * **[!UICONTROL Target content ID]**：用于在打开通知时定位要转发的应用程序窗口的标识符。

   * **[!UICONTROL Launch image]**：要显示的启动图像文件的名称。 如果用户选择启动您的应用程序，则会显示选定的图像而不是应用程序的启动屏幕。

   * **[!UICONTROL Interruption level]**：

      * **[!UICONTROL Active]**：默认情况下，系统会立即显示通知，打开屏幕并播放声音。 通知不会突破焦点模式。

      * **[!UICONTROL Passive]**：系统将通知添加到通知列表，而不打开屏幕或播放声音。 通知不会突破焦点模式。

      * **[!UICONTROL Time sensitive]** 系统立即显示通知，打开屏幕，可以播放声音并突破焦点模式。 此级别不需要Apple的特殊权限。

      * **[!UICONTROL Critical]** 系统立即显示通知，打开屏幕，并绕过静音开关或聚焦模式。 请注意，此级别需要Apple的特殊权限。

   * **[!UICONTROL Relevance score]**：将相关性得分从0设置为100。 系统使用此选项对通知摘要中的通知进行排序。

   ![](assets/push_ios_7.png)

1. 配置通知后，单击 **[!UICONTROL Preview]** 选项卡以预览通知。

   ![](assets/push-ios-preview.png)


>[!TAB Android]

要在Android设备上发送通知，请执行以下步骤：

1. 选择 **[!UICONTROL Deliver on Android (android)]** 投放模板。

   ![](assets/push-template-android.png)

1. 要定义通知的目标，请单击 **[!UICONTROL To]** 链接，然后单击 **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. 选择 **[!UICONTROL Subscribers of an Android mobile application]**，选择与您的移动应用程序相关的服务（在本例中为Neotrips），然后选择应用程序的Android版本。

   ![](assets/push-android-subscribers.png)

1. 然后，输入通知的内容。

   ![](assets/push-android-content.png)

1. 单击 **[!UICONTROL Insert emoticon]** 图标，用于将表情符号插入到您的推送通知中。

1. 在 **[!UICONTROL Application variables]** 字段中，输入每个变量的值。 例如，您可以配置在用户激活通知时显示的特定应用程序屏幕。

1. 配置通知后，单击 **[!UICONTROL Preview]** 选项卡以预览通知。

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]

## 测试、发送和监控推送通知

要发送验证并发送最终投放，请按照与其他投放相同的流程操作。

了解如何在中验证投放 [此页面](preview-and-proof.md).

了解如何确认并发送投放 [此页面](send.md)

发送消息后，您可以监控和跟踪投放。 要了解有关推送通知投放失败原因的更多信息，请参阅 [此页面](delivery-failures.md#push-error-types).

