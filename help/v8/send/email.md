---
title: 使用Adobe Campaign发送电子邮件
description: 在 Adobe Campaign 中开始使用电子邮件。将个性化的电子邮件发给目标人群。
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 16%

---

# 设计和发送电子邮件

电子邮件投放允许您向目标群体发送个性化电子邮件。

![](../assets/do-not-localize/book.png) 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html)以了解详情{target="_blank"}

## 创建您的第一个电子邮件投放

创建上下文相关的个性化电子邮件，使它们提供的体验与客户的其他体验保持一致。

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

      在中了解有关个性化选项的更多信息 [此部分](personalize.md).

   * 插入跟踪链接

      要通过图像或文本将投放收件人接收到外部地址，请选择该地址并单击 **[!UICONTROL Add a link]** 图标。

      在 **URL** 字段 **https://www.myURL.com**，然后确认。

      ![](assets/add-a-link.png)

   * 添加镜像页面

      要允许收件人在Web浏览器中查看您的投放内容，请添加指向 [镜像页面](../send/mirror-page.md) 你的留言。

      将光标放在要插入此链接的位置，单击工具栏中的最后一个图标，然后单击 **[!UICONTROL Include]** 选择 **[!UICONTROL link to mirror page]**.
   内容准备就绪后，单击 **保存**:现在，它将显示在您的投放列表、 **[!UICONTROL Campaigns > Deliveries]** 选项卡。 您的第一封电子邮件投放已准备就绪。 您现在需要定义受众、验证投放并发送它。


了解如何在 [用例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

在 **Campaign Classicv7文档**:

* 在Campaign中设计电子邮件
   ![](../assets/do-not-localize/book.png) [了解如何设计电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html?lang=zh-Hans){target="_blank"}
* 创建和使用电子邮件模板
   ![](../assets/do-not-localize/book.png) [了解有关电子邮件模板的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hans){target="_blank"}
* 选择电子邮件的受众
   ![](../assets/do-not-localize/book.png) [了解如何定义目标群体](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}
* 验证投放并发送校样
   ![](../assets/do-not-localize/book.png) [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hans){target="_blank"}
* 添加 [种子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## 测试和验证电子邮件

Campaign提供了多种方法，用于在向受众发送电子邮件之前测试和验证电子邮件。 了解如何在 [本页](../send/preview-and-proof.md).

您可以：

* 检查投放分析日志
*   发送验证
* 添加种子地址
* 使用对照组

![](../assets/do-not-localize/book.png) [请参阅 Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hans)以了解详情{target="_blank"}
