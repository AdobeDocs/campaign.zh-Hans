---
title: 使用Adobe Campaign发送短信
description: Campaign中短信快速入门
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%

---

# 创建和发送短信

使用Adobe Campaign发送个性化的短信消息。

![](../assets/do-not-localize/book.png) 了解如何在中开始使用短信渠道 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}

>[!NOTE]
>
>Adobe Campaign还允许您通过 **Adobe Campaign移动设备应用程序渠道(NMAC)** 选项。 在 [此部分](push.md).

## 配置短信渠道

要发送到移动电话，您需要：

* 指定连接器和消息类型的外部帐户。

* 在其中引用此外部帐户的投放模板。

![](../assets/do-not-localize/book.png)  了解如何在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}

开始发送短信之前：

* 确保收件人的用户档案至少包含其用户档案中的移动电话。
* 查看Adobe Campaign Classic [投放最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;}，该值也适用于Campaign v8。

此外，您还需要熟悉短信协议和设置。 逐步了解Adobe Campaign与SMPP提供商之间在 [本文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}。

## 创建您的首次短信投放

1. 要创建新投放，请浏览 **[!UICONTROL Campaigns]** ，单击 **[!UICONTROL Deliveries]** ，然后单击 **[!UICONTROL Create]** 按钮。

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) 有关如何创建投放的全局信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}。

1. 选择引用相关外部帐户的投放模板以发送短信投放。

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) 了解如何在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png) 了解如何创建投放模板以在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}

1. 使用标签、代码和描述标识投放。

1. 单击 **[!UICONTROL Continue]** 确认并显示消息配置窗口。

1. 在 **[!UICONTROL Text content]** 部分，包括根据需要的个性化字段。

   ![](assets/sms-content.png)

1. 选择目标群体。

有关创建和设计短信的关键步骤，请参阅Campaign Classicv7文档：

* 创建短信

   ![](../assets/do-not-localize/book.png) [了解如何创建短信投放](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* 设计短信内容

   ![](../assets/do-not-localize/book.png) [了解如何定义短信内容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* 选择电子邮件的受众

   ![](../assets/do-not-localize/book.png) [了解如何定义目标群体](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) 有关定义受众的详细步骤，请参阅 [本页](../start/audiences.md).

## 测试短信

要查看消息的个性化呈现，请单击 **[!UICONTROL Preview]** 并选择收件人。

![](assets/sms-preview.png)

要发送校样，请参阅Campaign Classicv7文档的以下部分：

* 验证投放并发送校样
   ![](../assets/do-not-localize/book.png) [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* 添加种子地址
   ![](../assets/do-not-localize/book.png) [了解种子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## 发送和监控短信投放

有关发送和监控短信的关键步骤，请参阅Campaign Classicv7文档：

* 发送、监控和跟踪短信投放

   ![](../assets/do-not-localize/book.png) [了解发送、监控和跟踪短信的工具。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* 短信投放疑难解答

   ![](../assets/do-not-localize/book.png) [了解短信疑难解答](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
