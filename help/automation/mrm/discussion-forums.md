---
product: campaign
title: 论坛
description: 了解如何使用Campaign论坛
feature: Campaigns, Resource Management
role: User
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 论坛{#discussion-forums}

Adobe Campaign操作员可以使用论坛来共享信息。 以下元素每个都有自己的论坛：计划、项目、促销活动、营销资源、模拟、库存。 每个操作员也有一个个人论坛。 所有讨论都是公开的，甚至在个人论坛上也是如此。

操作员可以订阅论坛，以便在每次发布消息时接收通知电子邮件。

## 访问论坛 {#accessing-a-forum}

要访问论坛，请浏览到功能板并单击 **[!UICONTROL Forum]** 右上角的链接。

![](assets/mrm-forum-icon.png)

消息及其响应按从最新到最旧的顺序显示。

要启动新线程，请单击 **[!UICONTROL Add a discussion]** 按钮进行标记。 此 **[!UICONTROL Discussion forum]** 框（见下文）。

![](assets/mrm-forum-new-thread.png)


在 **[!UICONTROL Message]** 字段和讨论标题 **[!UICONTROL Subject]** 字段。

默认情况下，已在此论坛中发布消息的操作员会收到通知。 您可以另选一个要通知的运算符。 要通知多个操作员，请选择一组操作员。

您可以使用以下方法向邮件添加附件  **[!UICONTROL Browse...]** 按钮。 附件也将包含在通知电子邮件中。 附件只能单独发送：要发送多个文件，您需要将它们压缩为.zip文件。

>[!CAUTION]
>
>消息发布到论坛后，无法再更改或删除。

## 发布到操作员的个人论坛 {#posting-to-the-personal-forum-of-an-operator}

您可以向操作员的论坛发布消息。 个人论坛是公开的，所有操作员都可以看到您的消息。 每次有人发帖到其个人论坛时，操作员都会收到电子邮件通知。

要访问操作员的论坛，您可以：

* 浏览至 **[!UICONTROL Administration > Access management > Operators]** 文件夹，选择运算符以打开其功能板，然后单击 **[!UICONTROL Forum]** 右上角的链接。
* 在Adobe Campaign UI中查找操作员的姓名（通过操作员在论坛中发布的消息、分配给他们的任务），然后单击该消息以访问操作员仪表板。

## 订阅论坛 {#subscribing-to-a-forum}

通过订阅论坛，可关注所有讨论。 订阅后，每次在论坛中发布消息时，您都会收到电子邮件通知。

要回复消息，请单击电子邮件正文，然后登录到Adobe Campaign Web界面。

* 要订阅论坛，请单击 **[!UICONTROL Follow discussions]** 按钮进行标记。

  部分变为蓝色，并显示您订阅了论坛。

* 要取消订阅论坛，请单击 **[!UICONTROL Unsubscribe]** 按钮。

* 您的个人信息板列出了您订阅的论坛。 单击 **[!UICONTROL Subscription to discussion forums]** 链接以显示列表，然后单击感兴趣的项目以访问其论坛。

  ![](assets/forum-subscribed.png)


## 通知投放疑难解答 {#checking-notification-delivery}

如果订阅论坛的操作员未按预期收到通知：

* 检查操作员的配置文件中是否输入了电子邮件地址。
* 浏览至 **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** Campaign资源管理器的文件夹并检查 **[!UICONTROL Jobs in discussion forums]** 启动工作流时没有出现错误。
* 检查投放日志：

   * 在Adobe Campaign主页上，浏览 **[!UICONTROL Campaigns > Navigation > Deliveries]**，然后打开 **[!UICONTROL Discussion forum notification]** 投放。
   * 在Campaign资源管理器中，浏览至 **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**，然后单击 **[!UICONTROL Discussion forum notifications]**.

  在 **[!UICONTROL Discussion forum notifications]** 框中，投放日志位于 **[!UICONTROL Edit > Delivery]** 选项卡。 您还可以查看 **[!UICONTROL Tracking > Log]** 和 **[!UICONTROL Exclusion causes]** 选项卡。
