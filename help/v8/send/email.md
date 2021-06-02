---
product: Adobe Campaign
title: 使用Adobe Campaign发送电子邮件
description: Campaign中电子邮件入门
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: 5762e58aafb11932d0e28d87df84704974c09564
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 4%

---

# 设计和发送电子邮件

电子邮件投放允许您向目标群体发送个性化电子邮件。

[!DNL :arrow_upper_right:] 请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html)以了解更多信息。

## 创建您的第一个电子邮件投放

创建与上下文相关的个性化电子邮件，使其与客户的其他体验保持一致。

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [了解如何在Campaign Classicv7文档中创建电子邮件投放](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html)


在以下示例中，您将学习在Adobe Campaign中设计电子邮件投放的步骤，该投放包含个性化数据、指向外部URL的链接、指向镜像页面的链接和指向Web窗体的链接。

1. 创建投放

   要创建新投放，请浏览&#x200B;**营销活动**&#x200B;选项卡，单击&#x200B;**投放**，然后单击现有投放列表上方的&#x200B;**创建**&#x200B;按钮。

   ![](assets/delivery_step_1.png)

1. 选择模板

   选择投放模板，然后命名投放。 此名称仅对Adobe Campaign控制台的用户可见，对收件人则不可见，但此标题将显示在投放列表中。 单击 **[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. 导入内容

   单击&#x200B;**Source**&#x200B;选项卡以粘贴HTML内容。

   ![](assets/paste-content.png)


1. 个性化您的消息


   * 显示收件人的名字和姓氏

      要将收件人的第一个和第二个名称插入到投放的文本字段中，请单击您选择的文本字段，然后将光标放在要显示它们的位置。 单击弹出工具栏中的第一个图标，然后单击&#x200B;**[!UICONTROL Personalization block]**。 选择&#x200B;**[!UICONTROL Greetings]**，然后单击&#x200B;**[!UICONTROL OK]**。

   * 在图像中插入链接

      要通过图像将投放收件人定向到外部地址，请单击相关图像以显示弹出工具栏，将光标放在第一个图标上，然后单击&#x200B;**[!UICONTROL Link to an external URL]**。

      在&#x200B;**URL**&#x200B;字段中输入链接的URL，使用以下格式&#x200B;**https://www.myURL.com**，然后进行确认。

      可以随时使用窗口右侧的部分更改链接。

   * 将链接插入文本

      要将外部链接集成到投放中的文本中，请选择一些文本或一个文本块，然后单击弹出工具栏中的第一个图标。 单击&#x200B;**[!UICONTROL Link to an external URL]**，在&#x200B;**[!UICONTROL URL]**&#x200B;字段中输入链接地址。

      可以随时使用窗口右侧的部分更改链接。

   * 添加镜像页面

      要允许收件人在Web浏览器中查看您的投放内容，您可以将指向镜像页面的链接集成到您的投放中。

      单击您希望在其中看到已发布链接的文本字段。 单击弹出工具栏中的第一个图标，选择&#x200B;**[!UICONTROL Personalization block]**，然后选择&#x200B;**[!UICONTROL Link to Mirror Page (MirrorPage)]**。 单击&#x200B;**[!UICONTROL Save]**&#x200B;确认。

   * 集成指向Web应用程序的链接

      使用数字内容编辑器，您可以从Adobe Campaign控制台中集成指向Web应用程序的链接，如登陆页面或表单页面。

      为指向Web应用程序的链接选择文本字段，然后单击第一个图标。 选择&#x200B;**[!UICONTROL Link to a Web application]**，然后单击&#x200B;**Web Application**&#x200B;字段末尾的图标以选择所需的应用程序。

1. 发送邮件

   集成内容后，单击&#x200B;**Save**&#x200B;保存投放。 现在，它将显示在投放列表中，该列表位于&#x200B;**[!UICONTROL Campaigns > Deliveries]**&#x200B;选项卡中。


## 创建内容并选择受众

您可以直接在Campaign中创建内容或导入受众以及电子邮件内容。 请使用以下链接了解如何：

* 在Campaign中设计电子邮件
   [!DNL :arrow_upper_right:] [了解如何设计电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* 导入电子邮件内容
   [!DNL :arrow_upper_right:] [用例：创建用于加载投放内容的工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* 创建和使用电子邮件模板
   [!DNL :arrow_upper_right:] [了解有关电子邮件模板的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hans)
* 选择电子邮件的受众
   [!DNL :arrow_upper_right:] [了解如何定义目标群体](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* 验证投放并发送校样
   [!DNL :arrow_upper_right:] [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* 添加[种子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## 测试和验证电子邮件

Campaign提供了多种方法，用于在向受众发送电子邮件之前测试和验证电子邮件。

[!DNL :arrow_upper_right:] [应用Campaign Classicv7文档中列出的最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

您可以：

* 检查投放分析日志
* 发送校样
* 添加种子地址
* 使用对照组
* 检查电子邮件渲染

[!DNL :arrow_upper_right:] [在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## 监控电子邮件

发送后，在投放仪表板中检查您的投放状态，并访问投放日志和报告，确认消息已正确发送。

[!DNL :arrow_upper_right:] [在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

