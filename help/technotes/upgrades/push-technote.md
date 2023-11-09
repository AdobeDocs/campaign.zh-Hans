---
product: campaign
title: 推送通知渠道即将更改
description: 推送通知渠道即将更改
hide: true
hidefromtoc: true
source-git-commit: 70d1e7336cce7660890b13def5efcb614c0dc12e
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 推送通知渠道即将更改 {#push-upgrade}

Firebase Cloud Messaging (FCM)服务存在重要更改，这些更改可能会影响您的Adobe Campaign Classic实施。

作为Google不断努力改进其服务的一部分，旧版FCM API将于2024年6月停用([Firebase Cloud Messaging HTTP协议](https://firebase.google.com/docs/cloud-messaging/http-server-ref))

这些API当前与Adobe Campaign Classic集成以发送推送通知消息。 我们了解到，像您这样的许多客户都依赖这些服务来满足您的营销活动和通信需求，尤其是对于Android设备而言。

## 您是否受影响？

* **HTTP（旧版）API用户**：如果您的任何活动推送通知营销活动使用HTTP（旧版） API，则您的设置将直接受到此更改的影响。 我们强烈建议您查看当前配置，并为迁移到较新API做准备。

* **HTTP v1 API用户的好消息**：如果您的设置专门将HTTP v1 API用于Android推送通知，则表明您已经符合要求，无需执行进一步操作。

## 我们在做什么？

* **过渡计划**：我们的团队正在积极制定全面的过渡计划。 这将确保您可以根据需要将实施更新到Adobe Campaign最新版本中已提供的新FCM API，并且将对营销活动造成的中断降至最低。

* **详细说明**：我们将提供分步指南和其他资源，以促进顺利过渡过程。

* **支持**：我们的客户支持团队将在整个过渡过程中协助您。 我们还可能主办网络研讨会和支持会议，以涵盖过渡的技术方面和最佳实践。

## 我们期望你做什么？

* **随时了解最新信息**：密切关注您的收件箱，以便我们进一步通信，包括详细的过渡计划。

* **查看当前设置**：利用此时间来查看Adobe Campaign Classic中的当前配置和自定义，以便根据需要做好进行任何必要更改的准备。

* **联系我们**：如果您有任何紧迫的疑虑或问题，请随时联系我们的支持团队。

## 实施步骤

在接下来的几周内，我们将分享有关旧版FCM API过渡计划的更多详细信息，包括时间表和操作项。 放心，我们的主要目标是让您和您的团队尽可能顺利地进行此过渡。

我们感谢您的合作，并感谢您对我们适应这些变化的理解。 您的成功是我们的首要任务，我们致力于支持您工作的每一步骤。

为了让您能够预见更改，以下是将推送配置从HTTP（旧版）迁移到FCM HTTPv1 API所需的一般步骤。

### 内部版本升级

* Campaign Classic： 20.3.1版本中添加了对HTTPv1的支持。 如果您使用的是以前的版本，则必须首先升级到最新的Campaign Classic内部版本。

* Campaign v8：所有Campaign v8版本都支持HTTPv1。 无需升级。

### 营销服务器

配置更改可由客户/合作伙伴执行。

1. 首先，您需要提取JSON文件。 需要Firebase Admin SDK服务的帐户JSON文件才能将移动应用程序移动到HTTPv1。 请参阅此 [页面](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. 导航到您的列表 **服务和订阅**.

1. 使用HTTP（旧版）API版本找到所有移动应用程序。

1. 对于这些移动设备应用程序中的每一个，设置 **API版本** 到HTTPv1 ，并按照 [文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

>[!NOTE]
>
>新投放将考虑切换到HTTPv1 API。 正在重试、进行中和正在使用的投放仍将使用HTTP（旧版）API。

### 中间源服务器

无需进行更改。

### 实时执行服务器

您需要就此联系Adobe Campaign支持。 迁移过程与营销服务器的迁移过程相同。

### Android OS和Android移动应用程序

无需对Android移动应用程序的代码进行特定更改，通知行为不应发生变化。

尽管如此，HTTPv1仍引入了三个新的有效负载元素：

| 名称 | 默认值 |
|---|---|
| 粘性 | 假 |
| 优先级 | 默认 |
| 可见性 | 假 |
| 粘性 | 私人 |
