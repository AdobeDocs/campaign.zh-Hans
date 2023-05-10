---
title: 集成AEP SDK和Campaign
description: 了解如何将Adobe Experience Platform Mobile SDK与您的应用程序集成
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: 3bef6d2544a86bf1d5efa4868b82ec59c7e36484
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 2%

---


# AEP SDK + Campaign:配置推送通知渠道 {#push-notification-configuration}

开始使用Adobe Campaign发送推送通知之前，您需要确保移动设备应用程序和Adobe Experience Platform中标记上已设置配置和集成。

Adobe Experience Platform Mobile SDK通过与Android和iOS兼容的SDK为您的手机提供客户端集成API。

要使用Adobe Experience Platform Mobile SDK设置您的应用程序，请执行以下步骤：

1. 检查 [先决条件](#before-starting).
1. 设置 [移动标记属性](#launch-property) 在Adobe Experience Platform数据收集中。
1. 详细获取Adobe Experience Platform Mobile SDK [本页](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. （可选）启用日志记录和生命周期量度，如详细说明 [本页](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. （可选）添加 [Adobe Experience Platform为您的应用程序提供保证](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. 关注 [Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} 以在您的应用程序中使用Adobe Experience Platform Mobile SDK进行设置。
1. 安装和配置 [Adobe Campaign扩展](#configure-extension) 中。
1. 在Adobe Campaign中配置iOS和Android Mobile Services，如下所述 [本页](../send/push.md#push-config).


## 先决条件 {#before-starting}

### 设置权限 {#setup-permissions}

在创建移动应用程序之前，您首先需要确保在Adobe Experience Platform中拥有或分配正确的标记用户权限。 Adobe Experience Platform中标记的用户权限通过Adobe Admin Console分配给用户。 在 [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>推送配置必须由专家用户执行。 根据您的实施模型和此实施中涉及的角色，您可能需要将整套权限分配给单个产品配置文件或在应用程序开发人员与 **Adobe Campaign** 管理员。

要分配 **属性** 和 **公司** 权限，请执行以下步骤：

1. 访问 **[!DNL Admin Console]**.
1. 从 **[!UICONTROL Products]** 选项卡，选择 **[!UICONTROL Adobe Experience Platform Data Collection]** 卡。
1. 选择现有 **[!UICONTROL Product Profile]** 或使用 **[!UICONTROL New profile]** 按钮。 了解如何创建新 **[!UICONTROL New profile]** 在 [管理控制台文档](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. 在 **[!UICONTROL Permissions]** 选项卡中，选择 **[!UICONTROL Property Rights]**。
1. 单击 **[!UICONTROL Add all]**。这会将以下权限添加到您的产品用户档案：
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   安装和发布Adobe Campaign扩展以及在中发布应用程序资产时需要这些权限 **Adobe Experience Platform Mobile SDK**.

1. 然后，选择 **[!UICONTROL Company rights]** 菜单中。
1. 添加以下权限：

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   移动设备应用程序开发人员需要这些权限才能在中设置推送凭据 **Adobe Experience Platform数据收集**.

1. 单击 **[!UICONTROL Save]**。

要分配此 **[!UICONTROL Product profile]** 对于用户，请执行以下步骤：

1. 访问 **[!DNL Admin Console]**.
1. 从 **[!UICONTROL Products]** 选项卡，选择 **[!UICONTROL Adobe Experience Platform Data Collection]** 卡。
1. 选择您之前配置的 **[!UICONTROL Product profile]**。
1. 在选项卡 **[!UICONTROL Users]** 中，单击 **[!UICONTROL Add user]**。
1. 键入您的用户名或电子邮件地址，然后选择用户。 然后，单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果用户之前未在Admin Console中创建，请参阅 [添加用户文档](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### 配置您的应用程序 {#configure-app}

技术设置涉及应用程序开发人员与业务管理员之间的密切协作。 开始发送推送通知之前 [!DNL Adobe Campaign]，您需要在 [!DNL Adobe Experience Platform Data Collection] 并将您的移动设备应用程序与Adobe Experience Platform Mobile SDK集成。

按照以下链接中详细描述的实施步骤操作：

* 对于 **AppleiOS**:了解如何在 [Apple文档](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* 对于 **Google Android**:了解如何在Android中设置Firebase Cloud Messaging客户端应用程序 [Google文档](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

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

设置移动资产后，移动设备应用程序开发人员或营销人员便可以配置移动SDK。 通常，您会为要管理的每个移动应用程序创建一个移动资产。 了解如何在 [Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

要获取推送通知工作所需的SDK，您将需要以下SDK扩展(适用于Android和iOS):

* **[!UICONTROL Mobile Core]** （自动安装）
* **[!UICONTROL Profile]** （自动安装）
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**，可选，但建议调试移动设备实施。

详细了解 [!DNL Adobe Experience Platform Data Collection] 标记 [Adobe Experience Platform文档](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

创建后，打开新的标记属性并创建库。 操作步骤：

1. 浏览到 **发布流程** 在左侧导航中，然后选择 **添加库**.
1. 输入库的名称并选择环境。
1. 选择 **Add All Changed Resources**&#x200B;和 **保存并构建到开发环境**.
1. 最后，将此库设置为 **选择工作库** 按钮。


## 在移动资产中配置Adobe Campaign扩展 {#configure-extension}

的 **Adobe Campaign Classic扩展** for Adobe Experience Platform Mobile SDK可为移动设备应用程序的推送通知提供支持，并帮助您收集用户推送令牌并管理与Adobe Experience Platform服务的交互测量。

此扩展已预安装在您的环境中，必须对其进行配置。 要为移动标记资产配置扩展，请执行以下步骤：

1. 打开之前创建的标记属性。
1. 从左侧导航中，浏览到 **扩展**，然后打开 **目录** 选项卡。 使用搜索字段查找 **Adobe Campaign Classic** 扩展。
1. 在Campaign Classic卡中，单击 **安装** 按钮。
1. 按照 [Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

您现在可以将Campaign添加到应用程序，详情请参阅  [Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## 在Campaign中配置移动服务{#push-service}

在 [!DNL Adobe Experience Platform Data Collection]，您需要创建两项服务(一项用于iOS设备，一项用于Android设备)，才能从发送推送通知 **[!DNL Adobe Campaign]**.

了解如何在中为iOS和Android推送通知创建和配置服务 [此部分](../send/push.md#push-config).
