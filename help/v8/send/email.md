---
title: 使用Adobe Campaign发送电子邮件
description: 在 Campaign 中开始使用电子邮件
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 9%

---

# 设计和发送电子邮件

电子邮件投放允许您向目标群体发送个性化电子邮件。

![](../assets/do-not-localize/book.png) 在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html){target=&quot;_blank&quot;}

## 创建您的第一个电子邮件投放

创建与上下文相关的个性化电子邮件，使其与客户的其他体验保持一致。

![](assets/new-email-content.png)


在以下示例中，您将学习在Adobe Campaign中设计电子邮件投放的步骤，该投放包含个性化数据、指向外部URL的链接以及指向镜像页面的链接。

1. **创建投放**

   要创建新投放，请浏览 **促销活动** ，单击 **投放** ，然后单击 **创建** 按钮。

   ![](assets/delivery_step_1.png)

1. **选择模板**

   选择投放模板，然后命名投放。 此名称仅对Adobe Campaign控制台的用户可见，对收件人则不可见，但此标题将显示在投放列表中。 单击 **[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. **导入内容**

   单击 **来源** 选项卡来粘贴HTML内容。

   ![](assets/paste-content.png)


1. **个性化您的消息**


   * 添加收件人的名字和姓氏

      要在消息内容中插入目标用户档案的名字和姓氏，请将光标放在要插入它们的位置，然后单击工具栏中的最后一个图标，然后单击 **[!UICONTROL Include]** 选择 **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      浏览到“预览”选项卡，以通过选择收件人检查个性化。

      ![](assets/perso-check.png)

   * 插入跟踪链接

      要通过图像或文本将投放收件人接收到外部地址，请选择该地址并单击 **[!UICONTROL Add a link]** 图标。

      在 **URL** 字段 **https://www.myURL.com**，然后确认。

      ![](assets/add-a-link.png)

   * 添加镜像页面

      要允许收件人在Web浏览器中查看您的投放内容，请添加指向消息镜像页面的链接。

      将光标放在要插入此链接的位置，单击工具栏中的最后一个图标，然后单击 **[!UICONTROL Include]** 选择 **[!UICONTROL link to mirror page]**.
   内容准备就绪后，单击 **保存**:现在，它将显示在您的投放列表、 **[!UICONTROL Campaigns > Deliveries]** 选项卡。 您的第一封电子邮件投放已准备就绪。 您现在需要定义受众、验证投放并发送它。


请参阅Campaign Classicv7文档的以下部分，了解更多信息：

* 在Campaign中设计电子邮件
   ![](../assets/do-not-localize/book.png) [了解如何设计电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html){target=&quot;_blank&quot;}
* 导入电子邮件内容
   ![](../assets/do-not-localize/book.png) [用例：创建用于加载投放内容的工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html){target=&quot;_blank&quot;}
* 创建和使用电子邮件模板
   ![](../assets/do-not-localize/book.png) [了解有关电子邮件模板的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hans){target=&quot;_blank&quot;}
* 选择电子邮件的受众
   ![](../assets/do-not-localize/book.png) [了解如何定义目标群体](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}
* 验证投放并发送校样
   ![](../assets/do-not-localize/book.png) [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* 添加 [种子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## 测试和验证电子邮件

Campaign提供了多种方法，用于在向受众发送电子邮件之前测试和验证电子邮件。

![](../assets/do-not-localize/book.png) [应用Campaign Classicv7文档中列出的最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html){target=&quot;_blank&quot;}

您可以：

* 检查投放分析日志
*   发送验证
* 添加种子地址
* 使用对照组
* 检查电子邮件渲染

![](../assets/do-not-localize/book.png) [在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
