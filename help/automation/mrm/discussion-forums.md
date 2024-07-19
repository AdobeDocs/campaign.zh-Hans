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

要访问论坛，请浏览到仪表板并单击右上角的&#x200B;**[!UICONTROL Forum]**&#x200B;链接。

![](assets/mrm-forum-icon.png)

消息及其响应按从最新到最旧的顺序显示。

要启动新线程，请单击右上角的&#x200B;**[!UICONTROL Add a discussion]**&#x200B;按钮。 出现&#x200B;**[!UICONTROL Discussion forum]**&#x200B;框（见下文）。

![](assets/mrm-forum-new-thread.png)


在&#x200B;**[!UICONTROL Message]**&#x200B;字段中输入您的文本，在&#x200B;**[!UICONTROL Subject]**&#x200B;字段中输入讨论标题。

默认情况下，已在此论坛中发布消息的操作员会收到通知。 您可以另选一个要通知的运算符。 要通知多个操作员，请选择一组操作员。

您可以使用&#x200B;**[!UICONTROL Browse...]**&#x200B;按钮向邮件添加附件。 附件也将包含在通知电子邮件中。 附件只能单独发送：要发送多个文件，您需要将它们压缩为.zip文件。

>[!CAUTION]
>
>消息发布到论坛后，无法再更改或删除。

## 发布到操作员的个人论坛 {#posting-to-the-personal-forum-of-an-operator}

您可以向操作员的论坛发布消息。 个人论坛是公开的，所有操作员都可以看到您的消息。 每次有人发帖到其个人论坛时，操作员都会收到电子邮件通知。

要访问操作员的论坛，您可以：

* 浏览至Campaign资源管理器的&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;文件夹，选择运算符以打开其仪表板，然后单击右上角的&#x200B;**[!UICONTROL Forum]**&#x200B;链接。
* 在Adobe Campaign UI中查找操作员的姓名（通过操作员在论坛中发布的消息、分配给他们的任务），然后单击该消息以访问操作员仪表板。

## 订阅论坛 {#subscribing-to-a-forum}

通过订阅论坛，可关注所有讨论。 订阅后，每次在论坛中发布消息时，您都会收到电子邮件通知。

要回复消息，请单击电子邮件正文，然后登录到Adobe Campaign Web界面。

* 要订阅论坛，请单击消息列表上方右上角的&#x200B;**[!UICONTROL Follow discussions]**&#x200B;按钮。

  部分变为蓝色，并显示您订阅了论坛。

* 要取消订阅论坛，请单击&#x200B;**[!UICONTROL Unsubscribe]**&#x200B;按钮。

* 您的个人信息板列出了您订阅的论坛。 单击&#x200B;**[!UICONTROL Subscription to discussion forums]**&#x200B;链接以显示列表，然后单击您感兴趣的项目以访问其论坛。

  ![](assets/forum-subscribed.png)


## 通知投放疑难解答 {#checking-notification-delivery}

如果订阅论坛的操作员未按预期收到通知：

* 检查操作员的配置文件中是否输入了电子邮件地址。
* 浏览到Campaign资源管理器的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Campaign processes]**&#x200B;文件夹，并检查是否启动了&#x200B;**[!UICONTROL Jobs in discussion forums]**&#x200B;工作流且没有错误。
* 检查投放日志：

   * 在Adobe Campaign主页上，浏览到&#x200B;**[!UICONTROL Campaigns > Navigation > Deliveries]**，然后打开&#x200B;**[!UICONTROL Discussion forum notification]**&#x200B;投放。
   * 在Campaign资源管理器中，浏览到&#x200B;**[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**，然后单击&#x200B;**[!UICONTROL Discussion forum notifications]**。

  在&#x200B;**[!UICONTROL Discussion forum notifications]**&#x200B;框中，在&#x200B;**[!UICONTROL Edit > Delivery]**&#x200B;选项卡中找到投放日志。 您还可以查看&#x200B;**[!UICONTROL Tracking > Log]**&#x200B;和&#x200B;**[!UICONTROL Exclusion causes]**&#x200B;选项卡。
