---
title: 集成AEP SDK和Campaign
description: 了解如何将Adobe Experience Platform移动SDK与您的应用程序集成
feature: Push
role: Admin, Developer
level: Intermediate
exl-id: 1a75f411-3f71-4114-b738-277820dc6138
source-git-commit: a288845e1f092d293d679fa9aaaf6d609de85230
workflow-type: tm+mt
source-wordcount: '1681'
ht-degree: 4%

---

# 配置推送通知渠道 {#push-notification-configuration}

要使用Adobe Campaign发送推送通知，您必须首先配置环境和应用程序，如本页所述。 在Adobe Campaign中，发送推送通知的渠道是移动设备应用程序渠道。

>[!CAUTION]
>
>Android Firebase Cloud Messaging (FCM) 服务的一些重要更改将于 2024 年发布，并将影响您的 Adobe Campaign 实施。您可能需要更新 Android 推送消息的订阅服务配置，才能支持此更改。您已经可以检查并执行操作。 [了解详情](../../technotes/upgrades/push-technote.md)。

在开始使用Adobe Campaign发送推送通知之前，您需要确保移动应用程序和Adobe Experience Platform中的标记已具有配置和集成。 Adobe Experience Platform Mobile SDK通过与Android和iOS兼容的SDK，为您的移动设备提供客户端集成API。

要使用Adobe Experience Platform Mobile SDK设置应用程序，请执行以下步骤：

1. 检查[先决条件](#before-starting)。
1. 在Adobe Experience Platform数据收集中设置[移动标记属性](#launch-property)。
1. 在此页面[&#128279;](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}中获取详细的Adobe Experience Platform Mobile SDK 。
1. （可选）启用日志记录和生命周期量度，如本页[&#128279;](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}中的详细所示。
1. （可选）将[Adobe Experience Platform Assurance添加到您的应用程序](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"}以验证您的实施。 在此页面[&#128279;](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}中了解如何实施Adobe Experience Platform Assurance扩展。
1. 在Adobe Campaign中配置iOS和Android Mobile Services，如本页[所述。](#push-service)
1. 在移动资产中安装和配置[Adobe Campaign扩展](#configure-extension)。
1. 请按照[Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"}中的说明，在您的应用程序中设置Adobe Experience Platform Mobile SDK。

## 先决条件 {#before-starting}

### 设置权限 {#setup-permissions}

在创建移动应用程序之前，您首先需要确保拥有或分配适用于Adobe Experience Platform中的标记的正确用户权限。 Adobe Experience Platform中标记的用户权限通过Adobe Admin Console分配给用户。 请参阅[标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}以了解详情。

>[!CAUTION]
>
>推送配置必须由专家用户执行。 根据您的实施模型和此实施中涉及的角色，您可能需要将整套权限分配给单个产品配置文件，或在应用程序开发人员和&#x200B;**Adobe Campaign**&#x200B;管理员之间共享权限。

要分配&#x200B;**属性**&#x200B;和&#x200B;**公司**&#x200B;权限，请执行以下步骤：

1. 访问&#x200B;**[!DNL Admin Console]**。
1. 从&#x200B;**[!UICONTROL Products]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Adobe Experience Platform Data Collection]**&#x200B;卡片。
1. 选择现有&#x200B;**[!UICONTROL Product Profile]**&#x200B;或使用&#x200B;**[!UICONTROL New profile]**&#x200B;按钮创建新按钮。 在[Admin Console文档](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}中了解如何创建新的&#x200B;**[!UICONTROL New profile]**。
1. 在 **[!UICONTROL Permissions]** 选项卡中，选择 **[!UICONTROL Property Rights]**。
1. 单击 **[!UICONTROL Add all]**。这会将以下权限添加到您的产品配置文件：
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   在&#x200B;**Adobe Experience Platform Mobile SDK**&#x200B;中安装和发布Adobe Campaign扩展以及发布应用程序属性时需要这些权限。

1. 然后，在左侧菜单中选择&#x200B;**[!UICONTROL Company rights]**。
1. 添加以下权限：

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   移动设备应用程序开发人员需要这些权限才能在&#x200B;**Adobe Experience Platform数据收集**&#x200B;中设置推送凭据。

1. 单击 **[!UICONTROL Save]**。

要将此&#x200B;**[!UICONTROL Product profile]**&#x200B;分配给用户，请执行以下步骤：

1. 访问&#x200B;**[!DNL Admin Console]**。
1. 从&#x200B;**[!UICONTROL Products]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Adobe Experience Platform Data Collection]**&#x200B;卡片。
1. 选择您之前配置的 **[!UICONTROL Product profile]**。
1. 在选项卡 **[!UICONTROL Users]** 中，单击 **[!UICONTROL Add user]**。
1. 键入用户名或电子邮件地址，然后选择用户。 然后，单击&#x200B;**[!UICONTROL Save]**。

   >[!NOTE]
   >
   >如果以前未在Admin Console中创建过该用户，请参阅[添加用户文档](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}。

### 配置您的应用程序 {#configure-app}

技术设置涉及应用程序开发人员和业务管理员之间的密切合作。 在使用[!DNL Adobe Campaign]开始发送推送通知之前，您需要在[!DNL Adobe Experience Platform Data Collection]中定义设置，并将移动应用程序与Adobe Experience Platform Mobile SDK集成。

请按照以下链接中详述的实施步骤操作：

* 对于&#x200B;**Apple iOS**：请参阅[Apple文档](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}以了解如何使用APN注册您的应用程序
* 对于&#x200B;**Google Android**：请参阅[Google文档](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}以了解如何在Android上设置Firebase Cloud Messaging客户端应用程序

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## 在Adobe Experience Platform数据收集中设置移动标记属性 {#launch-property}

设置移动资产可允许移动应用程序开发人员或营销人员配置移动SDK。 通常，您将为要管理的每个移动应用程序创建一个移动资产。 请参阅[Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}以了解如何创建和配置移动资产。
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

在[Adobe Experience Platform文档](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}中了解有关[!DNL Adobe Experience Platform Data Collection]标记的更多信息。

创建后，打开新的标记属性并创建库。 操作步骤：

1. 在左侧导航中浏览到&#x200B;**发布流**&#x200B;并选择&#x200B;**添加库**。
1. 输入库名称并选择环境。
1. 选择&#x200B;**添加所有更改的资源**&#x200B;和&#x200B;**保存并生成到开发**。
1. 最后，通过&#x200B;**选择工作库**&#x200B;按钮将此库设置为工作库。

## 在Campaign中配置移动服务 {#push-service}

在[!DNL Adobe Experience Platform Data Collection]中设置您的移动应用后，您需要创建两个服务(一个用于iOS设备，一个用于Android设备)才能从&#x200B;**[!DNL Adobe Campaign]**&#x200B;发送推送通知。

推送通知通过专用服务发送给您的应用程序用户。 用户安装您的应用程序后，会订阅此服务：Adobe Campaign依赖此服务仅定向应用程序的订阅者。 在此服务中，您需要添加要在iOS和Android设备上发送的iOS和Android应用程序。

要创建服务以发送推送通知，请执行以下步骤：

1. 浏览到&#x200B;**[!UICONTROL Profiles and Targets > Services and Subscriptions]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Create]**。

   ![](assets/new-service-push.png){width="800" align="left"}

1. 输入&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Internal name]**，然后选择&#x200B;**[!UICONTROL Mobile application]**&#x200B;类型。

   >[!NOTE]
   >
   >默认&#x200B;**[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]**&#x200B;目标映射已链接到收件人表。 如果要使用其他目标映射，则需要创建一个新的目标映射，并在服务的&#x200B;**[!UICONTROL Target mapping]**&#x200B;字段中输入该映射。 在[此页面](../audiences/target-mappings.md)中了解有关目标映射的详细信息。

1. 然后，使用右侧的&#x200B;**[!UICONTROL Add]**&#x200B;图标定义使用此服务的移动应用程序。

>[!BEGINTABS]

>[!TAB iOS]

要为iOS设备创建应用程序，请执行以下步骤：

1. 选择 **[!UICONTROL Create an iOS application]** 并单击 **[!UICONTROL Next]**。

   ![](assets/new-ios-app.png){width="600" align="left"}

1. 在&#x200B;**[!UICONTROL Label]**&#x200B;字段中输入应用程序的名称。
1. （可选）您可以使用大约&#x200B;**[!UICONTROL Application variables]**&#x200B;扩充推送消息内容。 这些都是完全可自定义的，并且是发送到移动设备的消息有效负载的一部分。

   在以下示例中，添加&#x200B;**mediaURl**&#x200B;和&#x200B;**mediaExt**&#x200B;变量以创建富推送通知，然后为应用程序提供要在通知中显示的图像。

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. 浏览到&#x200B;**[!UICONTROL Subscription parameters]**&#x200B;选项卡以定义扩展为&#x200B;**[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]**&#x200B;架构的映射。

1. 浏览到&#x200B;**[!UICONTROL Sounds]**&#x200B;选项卡以定义要播放的声音。 单击&#x200B;**[!UICONTROL Add]**&#x200B;并填写&#x200B;**[!UICONTROL Internal name]**&#x200B;字段，该字段必须包含嵌入在应用程序中的文件的名称或系统声音的名称。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;开始配置开发应用程序。

1. 集成键特定于每个应用程序。 它将移动应用程序链接到Adobe Campaign。

   确保通过SDK在Adobe Campaign和应用程序代码中定义相同的&#x200B;**[!UICONTROL Integration key]**。

   请参阅[开发人员文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}以了解详情


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]**&#x200B;可使用字符串值完全自定义，但需要与SDK中指定的值完全相同。
   >
   > 您不能对应用程序的开发版本（沙盒）和生产版本使用相同的证书。

1. 从&#x200B;**[!UICONTROL Application icon]**&#x200B;字段中选择图标以个性化服务中的移动应用程序。

1. 选择 **[!UICONTROL Authentication mode]**。提供了两种模式：

   * （推荐） **[!UICONTROL Token-based authentication]**：填写APNs连接设置&#x200B;**[!UICONTROL Key Id]**、**[!UICONTROL Team Id]**&#x200B;和&#x200B;**[!UICONTROL Bundle Id]**，然后单击&#x200B;**[!UICONTROL Enter the private key...]**&#x200B;选择您的p8证书。 有关&#x200B;**[!UICONTROL Token-based authentication]**&#x200B;的详细信息，请参阅[Apple文档](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}。

   * **[!UICONTROL Certificate-based authentication]**：单击&#x200B;**[!UICONTROL Enter the certificate...]**，然后选择p12密钥并输入移动应用程序开发人员提供的密码。 请注意，此证书附带到期日期，必须每年续订。 为避免用户的服务中断，请在证书过期前更新证书。 证书的有效期为一年，您必须对其进行更新才能继续与APN进行通信。

1. 使用&#x200B;**[!UICONTROL Test the connection]**&#x200B;按钮验证您的配置。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;开始配置生产应用程序，并遵循上面详述的相同步骤。

1. 单击 **[!UICONTROL Finish]**。

您的iOS应用程序现在已准备好在Campaign中使用。

>[!TAB Android]

要为Android设备创建应用程序，请执行以下步骤：

1. 选择 **[!UICONTROL Create an Android application]** 并单击 **[!UICONTROL Next]**。

   ![](assets/new-android-app.png){width="600" align="left"}

1. 在&#x200B;**[!UICONTROL Label]**&#x200B;字段中输入应用程序的名称。
1. 集成键特定于每个应用程序。 它将移动应用程序链接到Adobe Campaign。

   确保通过SDK在Adobe Campaign和应用程序代码中定义相同的&#x200B;**[!UICONTROL Integration key]**。

   请参阅[开发人员文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}以了解详情


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]**&#x200B;可使用字符串值完全自定义，但需要与SDK中指定的值完全相同。
   >

1. 从&#x200B;**[!UICONTROL Application icon]**&#x200B;字段中选择图标以个性化服务中的移动应用程序。
1. 在&#x200B;**[!UICONTROL API version]**&#x200B;下拉列表中选择&#x200B;**HTTP v1**。
1. 单击&#x200B;**[!UICONTROL Load project json file to extract project details...]**&#x200B;链接以加载您的JSON密钥文件。 有关如何提取JSON文件的更多信息，请参阅[Google Firebase文档](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}。

   您还可以手动输入以下详细信息：
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. 使用&#x200B;**[!UICONTROL Test the connection]**&#x200B;按钮验证您的配置。

   >[!CAUTION]
   >
   >**[!UICONTROL Test connection]**&#x200B;按钮不检查中间源(MID)服务器是否有权访问FCM服务器。

1. （可选）如果需要，您可以使用大约&#x200B;**[!UICONTROL Application variables]**&#x200B;扩充推送消息内容。 这些都是完全可自定义的，并且是发送到移动设备的消息有效负载的一部分。

1. 单击&#x200B;**[!UICONTROL Finish]**，然后单击&#x200B;**[!UICONTROL Save]**。 您的Android应用程序现在已准备好在Campaign中使用。

以下是FCM有效负荷名称，用于进一步个性化您的推送通知：

| 消息类型 | 可配置消息元素（FCM有效负荷名称） | 可配置选项（FCM有效负荷名称） |
|:-:|:-:|:-:|
| 数据消息 | N/A | validate_only |
| 通知消息 | title，正文， android_channel_id，图标，声音，标记，颜色，点击操作，图像，滚动条，粘性，可见性，通知优先级，通知计数<br> | validate_only |


>[!ENDTABS]

## 在移动资产中配置Adobe Campaign扩展 {#configure-extension}

适用于Adobe Experience Platform Mobile SDK的&#x200B;**Adobe Campaign Classic扩展**&#x200B;可为您的移动应用程序提供推送通知，并帮助您收集用户推送令牌和管理与Adobe Experience Platform服务的交互测量。

此扩展同时适用于Campaign Classic v7和Campaign v8，已在您的环境中预安装，必须进行配置。 要为移动标记资产配置扩展，请执行以下步骤：

1. 打开您之前创建的标记属性。
1. 从左侧导航中，浏览到&#x200B;**扩展**，然后打开&#x200B;**目录**&#x200B;选项卡。 使用搜索字段查找&#x200B;**Adobe Campaign Classic**&#x200B;扩展。
1. 从Campaign Classic卡中，单击&#x200B;**安装**&#x200B;按钮。
1. 按照[Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}中的说明输入设置。

您现在可以将Campaign添加到您的应用程序，如[Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}中所述。
