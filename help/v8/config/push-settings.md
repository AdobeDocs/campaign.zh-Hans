---
title: 集成AEP SDK和Campaign
description: 了解如何将Adobe Experience Platform Mobile SDK与您的应用程序集成
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: ff6990f3db1122670bff4919f417b9f9f04d3183
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 2%

---


# AEP SDK + Campaign：配置推送通知渠道 {#push-notification-configuration}

在开始使用Adobe Campaign发送推送通知之前，您需要确保为移动应用程序和Adobe Experience Platform中的标记配置并集成到位。

Adobe Experience Platform Mobile SDK通过与Android和iOS兼容的SDK，为您的移动设备提供客户端集成API。

要使用Adobe Experience Platform Mobile SDK设置应用程序，请执行以下步骤：

1. Check [先决条件](#before-starting).
1. 设置 [移动标记属性](#launch-property) 在Adobe Experience Platform数据收集中。
1. 获取详细的Adobe Experience Platform Mobile SDK [本页内容](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. （可选）启用日志记录和生命周期量度（如详细内容所示） [本页内容](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. （可选）添加 [应用程序的Adobe Experience Platform保证](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. 关注 [Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} ，以在您的应用程序中使用Adobe Experience Platform Mobile SDK进行设置。
1. 安装和配置 [Adobe Campaign扩展](#configure-extension) 在移动资产中。
1. 在Adobe Campaign中配置iOS和Android Mobile Services（详细信息请参阅） [本页内容](../send/push.md#push-config).


## 先决条件 {#before-starting}

### 设置权限 {#setup-permissions}

在创建移动应用程序之前，您首先需要确保您拥有或分配了适用于Adobe Experience Platform中的标记的正确用户权限。 Adobe Experience Platform中标记的用户权限通过Adobe Admin Console分配给用户。 了解详情，请参阅 [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>推送配置必须由专家用户执行。 根据您的实施模型和此实施中涉及的角色，您可能需要将完整权限集分配给单个产品配置文件，或在应用程序开发人员和 **Adobe Campaign** 管理员。

要分配 **属性** 和 **公司** 权限，请执行以下步骤：

1. 访问 **[!DNL Admin Console]**.
1. 从 **[!UICONTROL Products]** 选项卡，选择 **[!UICONTROL Adobe Experience Platform Data Collection]** 信息卡。
1. 选择现有 **[!UICONTROL Product Profile]** 或使用 **[!UICONTROL New profile]** 按钮。 了解如何新建 **[!UICONTROL New profile]** 在 [Admin console文档](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. 在 **[!UICONTROL Permissions]** 选项卡中，选择 **[!UICONTROL Property Rights]**。
1. 单击 **[!UICONTROL Add all]**。这会将以下权限添加到您的产品配置文件：
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   安装和发布Adobe Campaign扩展，以及在中发布应用程序属性时，需要这些权限 **Adobe Experience Platform Mobile SDK**.

1. 然后，选择 **[!UICONTROL Company rights]** 在左侧菜单中。
1. 添加以下权限：

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   移动设备应用程序开发人员需要这些权限才能在中设置推送凭据 **Adobe Experience Platform数据收集**.

1. 单击 **[!UICONTROL Save]**。

要分配此 **[!UICONTROL Product profile]** 对于用户，请执行以下步骤：

1. 访问 **[!DNL Admin Console]**.
1. 从 **[!UICONTROL Products]** 选项卡，选择 **[!UICONTROL Adobe Experience Platform Data Collection]** 信息卡。
1. 选择您之前配置的 **[!UICONTROL Product profile]**。
1. 在选项卡 **[!UICONTROL Users]** 中，单击 **[!UICONTROL Add user]**。
1. 键入用户名或电子邮件地址，然后选择用户。 然后，单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果之前未在Admin Console中创建用户，请参阅 [添加用户文档](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### 配置您的应用程序 {#configure-app}

技术设置涉及应用程序开发人员与业务管理员之间的紧密协作。 开始发送推送通知之前 [!DNL Adobe Campaign]，您需要定义中的设置 [!DNL Adobe Experience Platform Data Collection] 并将您的移动应用程序与Adobe Experience Platform Mobile SDK集成。

请按照以下链接中详述的实施步骤进行操作：

* 对象 **Apple iOS**：了解如何在中使用APN注册应用程序 [Apple文档](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* 对象 **Google Android**：了解如何在Android上设置Firebase Cloud Messaging客户端应用程序 [Google文档](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

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

设置移动资产可允许移动应用程序开发人员或营销人员配置Mobile SDK。 通常，您将为要管理的每个移动应用程序创建一个移动资产。 了解如何在中创建和配置移动资产 [Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

详细了解 [!DNL Adobe Experience Platform Data Collection] 中的标记 [Adobe Experience Platform文档](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

创建后，打开新标记属性并创建库。 操作步骤：

1. 浏览到 **发布流** 在左侧导航栏中选择 **添加库**.
1. 输入库名称并选择环境。
1. 选择 **添加所有更改的资源**、和 **保存并生成以进行开发**.
1. 最后，从以下位置将此库设置为工作库： **选择工作库** 按钮。


## 在移动资产中配置Adobe Campaign扩展 {#configure-extension}

此 **Adobe Campaign Classic扩展** for Adobe Experience Platform Mobile SDK可为您的移动应用程序提供推送通知，并帮助您收集用户推送令牌和管理与Adobe Experience Platform服务的交互测量。

此扩展适用于Campaign Classicv7和Campaign v8，已预安装到您的环境中，必须对其进行配置。 要为移动标记资产配置扩展，请执行以下步骤：

1. 打开您之前创建的标记属性。
1. 从左侧导航中，浏览到 **扩展**，然后打开 **目录** 选项卡。 使用搜索字段查找 **Adobe Campaign Classic** 扩展。
1. 在Campaign Classic卡中，单击 **安装** 按钮。
1. 按照中的说明输入设置 [Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

您现在可以将Campaign添加到您的应用程序，如中所述  [Adobe Experience Platform Mobile SDK文档](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## 在Campaign中配置移动服务{#push-service}

在中设置您的移动设备应用程序后 [!DNL Adobe Experience Platform Data Collection]，您需要创建两个服务(一个用于iOS设备，一个用于Android设备)才能从中发送推送通知 **[!DNL Adobe Campaign]**.

了解如何在中为iOS和Android推送通知创建和配置服务 [本节](../send/push.md#push-config).
