---
product: campaign
title: 论坛
description: 了解如何使用Campaign论坛
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 72fc29c49fca5767133be4a9927b57b3cfb51a14
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 论坛{#discussion-forums}

Adobe Campaign运营商可以使用论坛来共享信息。 以下元素各自具有自己的论坛：计划、项目、促销活动、营销资源、模拟、库存。 每位运营商还设有个人论坛。 所有讨论都是公开的，甚至在个人论坛上。

操作员可以订阅论坛，以便在每次发布消息时接收通知电子邮件。

## 访问论坛 {#accessing-a-forum}

要访问论坛，请浏览到功能板，然后单击 **[!UICONTROL Forum]** 链接。

![](assets/mrm-forum-icon.png)

消息及其响应从最新到最旧显示。

要启动新线程，请单击 **[!UICONTROL Add a discussion]** 按钮。 的 **[!UICONTROL Discussion forum]** 框（请参阅下文）。

![](assets/mrm-forum-new-thread.png)


在 **[!UICONTROL Message]** 字段和讨论标题 **[!UICONTROL Subject]** 字段。

默认情况下，已在此论坛中发布消息的操作员会收到通知。 您可以选择其他运算符来通知。 要通知多个运算符，请选择一组运算符。

您可以使用  **[!UICONTROL Browse...]** 按钮。 附件也将包含在通知电子邮件中。 附件只能单独发送：要发送多个文件，您需要将它们压缩为.zip文件。

>[!CAUTION]
>
>将消息发布到论坛后，便无法再更改或删除该消息。

## 帖子到操作员的个人论坛 {#posting-to-the-personal-forum-of-an-operator}

您可以向操作员的论坛发送消息。 个人论坛是公开的，所有运营者都可以看到您的消息。 每次有人向其个人论坛发帖时，操作员都会收到一封电子邮件通知。

要访问操作员论坛，您可以：

* 浏览到 **[!UICONTROL Administration > Access management > Operators]** Campaign explorer文件夹中，选择运算符以打开其功能板，然后单击 **[!UICONTROL Forum]** 链接。
* 在Adobe Campaign UI中查找操作员的名称（通过此操作员发布到论坛的消息，该消息为他们分配了任务），然后单击该名称以访问操作员仪表板。

## 订阅论坛 {#subscribing-to-a-forum}

订阅论坛可让您关注所有讨论。 订阅后，您每次向论坛发送消息时都会收到一封电子邮件通知。

要回答消息，请单击电子邮件正文中的，然后登录Adobe Campaign Web界面。

* 要订阅论坛，请单击 **[!UICONTROL Follow discussions]** 按钮。

   部分显示为蓝色，表示您已订阅论坛。

* 要取消订阅论坛，请单击 **[!UICONTROL Unsubscribe]** 按钮。

* 您的个人仪表板列出了您订阅的论坛。 单击 **[!UICONTROL Subscription to discussion forums]** 链接以显示列表，然后单击您感兴趣的项目以访问其论坛。

   ![](assets/forum-subscribed.png)


## 通知提交疑难解答 {#checking-notification-delivery}

如果订阅论坛的运营商未按预期收到通知：

* 检查是否在操作员的用户档案中输入了电子邮件地址。
* 浏览到 **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** Campaign资源管理器文件夹中，并检查 **[!UICONTROL Jobs in discussion forums]** 工作流已启动，且未出现错误。
* 检查投放日志：

   * 在Adobe Campaign主页上，浏览 **[!UICONTROL Campaigns > Navigation > Deliveries]**，然后打开 **[!UICONTROL Discussion forum notification]** 投放。
   * 在Campaign资源管理器中，浏览 **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**，然后单击 **[!UICONTROL Discussion forum notifications]**.
   在 **[!UICONTROL Discussion forum notifications]** 框中，可在 **[!UICONTROL Edit > Delivery]** 选项卡。 您还可以查看 **[!UICONTROL Tracking > Log]** 和 **[!UICONTROL Exclusion causes]** 选项卡。
