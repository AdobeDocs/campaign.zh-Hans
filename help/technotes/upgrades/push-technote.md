---
product: campaign
title: 推送通知渠道即将发生的变化
description: 推送通知渠道即将发生的变化
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="也适用于Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="适用于Campaign v8"
exl-id: 45ac6f8f-eb2a-4599-a930-1c1fcaa3095b
source-git-commit: 4ef40ff971519c064b980df8235188c717855f27
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 1%

---

# 推送通知渠道更改 {#push-upgrade}

您可以使用Campaign在iOS和Android设备上发送推送通知。 为此，Campaign依赖于移动应用程序订阅服务。

Android Firebase Cloud Messaging (FCM)服务的一些重要更改将于2024年发布，可能会影响您的Adobe Campaign实施。 您可能需要更新Android推送消息的订阅服务配置才能支持此更改。

此外，Adobe强烈建议迁移到基于令牌的连接而不是APN的基于证书的连接，这种连接更加安全和可扩展。

## Google Android Firebase Cloud Messaging (FCM)服务 {#fcm-push-upgrade}

### 更改了哪些内容？ {#fcm-changes}

作为Google不断努力改进其服务的一部分，旧版FCM API将于&#x200B;**2024年7月22日**&#x200B;终止。 请参阅[Google Firebase文档](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}以了解有关Firebase Cloud Messaging HTTP协议的更多信息。

Adobe Campaign Classic v7和Adobe Campaign v8已支持用于发送推送通知消息的最新API。 但是，某些旧实施仍依赖旧版API。 必须更新这些实施。

### 您是否受影响？ {#fcm-impact}

如果您当前的实施支持使用旧版API连接到FCM的订阅服务，则您会受到影响。 必须转换为最新的API才能避免任何服务中断。 在这种情况下，Adobe团队将会与您联系。

要检查您是否受到影响，您可以按照以下筛选条件筛选您的&#x200B;**服务和订阅**：

![](assets/filter-services-fcm.png)


* 如果您的任何活动推送通知服务使用&#x200B;**HTTP （旧版）** API，则您的设置将直接受到此更改的影响。 您必须查看当前配置并迁移到如下所述的新API。

* 如果您的安装程序仅使用&#x200B;**HTTP v1** API来接收Android推送通知，则表明您已符合要求，无需执行任何进一步操作。

### 如何更新？ {#fcm-transition-procedure}

#### 先决条件 {#fcm-transition-prerequisites}

* 对于Campaign Classicv7,20.3.1版本中添加了对HTTP v1的支持。 如果您的环境运行在旧版本上，则迁移到HTTP v1的先决条件是将环境升级到[最新的Campaign Classic内部版本](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}。 对于Campaign v8，所有版本都支持HTTP v1，无需升级。

* 需要Android Firebase Admin SDK服务的帐户JSON文件才能将移动应用程序移动到HTTP v1。 请参阅[Google Firebase文档](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}以了解如何获取此文件。

* 对于混合、托管和Managed Services部署，除了下面的过渡过程之外，请联系Adobe以更新实时(RT)执行服务器。 不影响中间源服务器。

* 作为Campaign Classic v7内部部署用户，您必须同时升级营销和实时执行服务器。 不影响中间源服务器。

#### 过渡过程 {#fcm-transition-steps}

要将环境移动到HTTP v1，请执行以下步骤：

1. 浏览到您的&#x200B;**服务和订阅**&#x200B;列表。
1. 使用&#x200B;**HTTP （旧版）** API版本列出所有移动应用程序。
1. 对于每个移动设备应用程序，请将&#x200B;**API版本**&#x200B;设置为&#x200B;**HTTP v1**。
1. 单击&#x200B;**[!UICONTROL Load project json file to extract project details...]**&#x200B;链接以直接加载您的JSON密钥文件。

   您还可以手动输入以下详细信息：

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. 单击&#x200B;**[!UICONTROL Test the connection]**&#x200B;以检查您的配置是否正确，以及营销服务器是否有权访问FCM。 请注意，对于中间源部署，**[!UICONTROL Test connection]**&#x200B;按钮无法检查服务器是否有权访问Android Firebase Cloud Messaging (FCM)服务。
1. 作为一个选项，您可以根据需要使用大约&#x200B;**[!UICONTROL Application variables]**&#x200B;扩充推送消息内容。 这些都是完全可自定义的，并且是发送到移动设备的消息有效负载的一部分。
1. 单击 **[!UICONTROL Finish]**，然后单击 **[!UICONTROL Save]**。

   以下是FCM有效负荷名称，用于进一步个性化您的推送通知。 [此处](#fcm-apps)详细介绍这些选项。

   | 消息类型 | 可配置消息元素（FCM有效负荷名称） | 可配置选项（FCM有效负荷名称） |
   |:-:|:-:|:-:|
   | 数据消息 | N/A | validate_only |
   | 通知消息 | title，正文， android_channel_id，图标，声音，标记，颜色，点击操作，图像，滚动条，粘性，可见性，通知优先级，通知计数<br> | validate_only |

1. 过渡HTTP v1完成后，您必须为Android推送通知更新&#x200B;**投放模板**&#x200B;以增加批处理消息数量。 为此，请浏览到Android投放模板的属性，然后在&#x200B;**投放**&#x200B;选项卡中，将[消息批次数量](../../v8/send/configure-and-send.md#delivery-batch-quantity)设置为&#x200B;**256**。 将此更改应用于您的Android投放使用的所有投放模板，以及您所有现有的Android投放。


>[!NOTE]
>
>所有这些更改应用于您的所有服务器后，交付给Android设备的所有新推送通知都将使用HTTP v1 API。 正在重试、进行中和正在使用的现有推送投放仍使用HTTP（旧版）API。

### 这对我的Android应用程序有何影响？ {#fcm-apps}

无需对Android Mobile应用程序的代码进行特定更改，通知行为不应发生变化。

但是，使用HTTP v1，您可以使用&#x200B;**[!UICONTROL HTTPV1 additional options]**&#x200B;进一步个性化推送通知。

![](assets/android-push-additional-options.png)

您可以：

* 使用&#x200B;**[!UICONTROL Ticker]**&#x200B;字段设置通知的滚动条文本。
* 使用&#x200B;**[!UICONTROL Image]**&#x200B;字段设置要在通知中显示的图像URL。
* 使用&#x200B;**[!UICONTROL Notification Count]**&#x200B;字段设置直接显示在应用程序图标上的新未读信息数。
* 将&#x200B;**[!UICONTROL Sticky]**&#x200B;选项设置为false，以便在用户单击该通知时自动将其关闭。 如果设置为true，则即使用户单击通知，也会显示通知。
* 将通知的&#x200B;**[!UICONTROL Notification Priority]**&#x200B;级别设置为默认、最小、低或高。
* 将通知的&#x200B;**[!UICONTROL Visibility]**&#x200B;级别设置为public、private或secret。

有关&#x200B;**[!UICONTROL HTTP v1 additional options]**&#x200B;以及如何填写这些字段的更多信息，请参阅[FCM文档](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}。



## Apple iOS推送通知服务(APN) {#apns-push-upgrade}

### 更改了哪些内容？ {#ios-changes}

按照Apple的建议，您应使用无状态身份验证令牌保护与Apple推送通知服务(APN)的通信。

基于令牌的身份验证提供了与APN进行通信的无状态方式。 无状态通信比基于证书的通信速度更快，因为它不要求APN查找与您的提供商服务器相关的证书或其他信息。 使用基于令牌的身份验证还有其他优势：

* 您可以使用来自多个提供程序服务器的相同令牌。

* 您可以使用一个令牌为您的公司的所有应用程序分发通知。

在[Apple开发人员文档](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}中了解有关基于令牌的APN连接的更多信息。

Adobe Campaign Classic v7和Adobe Campaign v8支持基于令牌和基于证书的连接。 如果您的实施依赖于基于证书的连接，Adobe强烈建议您将其更新为基于令牌的连接。

### 您是否受影响？ {#ios-impact}

如果您当前的实施依赖于基于证书的请求来连接到APN，则您会受到影响。 建议转换为基于令牌的连接。

要检查您是否受到影响，您可以按照以下筛选条件筛选您的&#x200B;**服务和订阅**：

![](assets/filter-services-ios.png)


* 如果您的任何活动推送通知服务使用&#x200B;**基于证书的身份验证**&#x200B;模式(.p12)，则应审查您当前的实施并将其移动到基于&#x200B;**令牌的身份验证**&#x200B;模式(.p8)，如下所述。

* 如果您的设置仅对iOS推送通知使用&#x200B;**基于令牌的身份验证**&#x200B;模式，则表明您的实施已处于最新状态，无需您执行任何进一步操作。

### 如何更新？ {#ios-transition-procedure}

#### 先决条件 {#ios-transition-prerequisites}

* 对于Campaign Classicv7，已在20.2版本中添加了对&#x200B;**基于令牌的身份验证**&#x200B;模式的支持。 如果您的环境运行在旧版本上，则此更改的先决条件是将您的环境升级到[最新的Campaign Classic内部版本](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}。 对于Campaign v8，所有版本都支持&#x200B;**基于令牌的身份验证**&#x200B;模式，无需升级。

* 您需要APN身份验证令牌签名密钥来生成您的服务器使用的令牌。 您从Apple开发人员帐户请求此密钥，如[Apple开发人员文档](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}中所述。

* 对于混合、托管和Managed Services部署，除了下面的过渡过程之外，请联系Adobe以更新实时(RT)执行服务器。 不影响中间源服务器。

* 作为Campaign Classic v7内部部署用户，您必须同时升级营销和实时执行服务器。 不影响中间源服务器。

#### 过渡过程 {#ios-transition-steps}

要将iOS移动应用程序移动到基于令牌的身份验证模式，请执行以下步骤：

1. 浏览到您的&#x200B;**服务和订阅**&#x200B;列表。
1. 使用&#x200B;**基于证书的身份验证**&#x200B;模式(.p12)列出所有移动应用程序。
1. 编辑每个移动应用程序，并浏览到&#x200B;**证书/私钥**&#x200B;选项卡。
1. 从&#x200B;**身份验证模式**&#x200B;下拉列表中，选择&#x200B;**基于令牌的身份验证**&#x200B;模式(.p8)。
1. 填写APNs连接设置&#x200B;**[!UICONTROL Key Id]**、**[!UICONTROL Team Id]**&#x200B;和&#x200B;**[!UICONTROL Bundle Id]**，然后单击&#x200B;**[!UICONTROL Enter the private key...]**&#x200B;选择您的p8证书。

   ![](assets/token-based-certif.png)

1. 单击&#x200B;**[!UICONTROL Test the connection]**&#x200B;以检查您的配置是否正确，以及服务器是否有权访问APN。 请注意，对于中间源部署，**[!UICONTROL Test connection]**&#x200B;按钮无法检查服务器是否有权访问APN。
1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;开始配置生产应用程序，并遵循上面详述的相同步骤。
1. 单击 **[!UICONTROL Finish]**，然后单击 **[!UICONTROL Save]**。

您的iOS应用程序现在已移至基于令牌的身份验证模式。
