---
title: 使用Adobe Campaign发送短信
description: Campaign中短信快速入门
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%

---

# 创建和发送短信

使用Adobe Campaign发送个性化的短信消息。

↗️了解如何在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}中开始使用SMS渠道

>[!NOTE]
>
>Adobe Campaign还允许您通过其&#x200B;**Adobe Campaign移动设备应用程序渠道(NMAC)**&#x200B;选项在手机上提交推送通知。 在[此部分](push.md)中了解详情。

## 配置短信渠道

要发送到移动电话，您需要：

* 指定连接器和消息类型的外部帐户。

* 在其中引用此外部帐户的投放模板。

↗️了解如何在[Campaign Classicv7文档中配置SMS渠道](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}

开始发送短信之前：

* 确保收件人的用户档案至少包含其用户档案中的移动电话。
* 查看Adobe Campaign Classic [投放最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;}，该最佳实践也适用于Campaign v8。

此外，您还需要熟悉短信协议和设置。 浏览在[本文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}中Adobe Campaign与SMPP提供程序之间设置的连接。

## 创建您的首次短信投放

1. 要创建新投放，请浏览&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL Deliveries]** ，然后单击现有投放列表上方的&#x200B;**[!UICONTROL Create]**&#x200B;按钮。

   ![](assets/delivery_step_1.png)

   ↗️有关如何创建投放的全局信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}。

1. 选择引用相关外部帐户的投放模板以发送短信投放。

   ![](assets/sms-template-list.png)

   ↗️了解如何在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}中创建SMPP外部帐户

   ↗️了解如何在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}中创建投放模板以投放到手机

1. 使用标签、代码和描述标识投放。

1. 单击&#x200B;**[!UICONTROL Continue]**&#x200B;以确认并显示消息配置窗口。

1. 在向导的&#x200B;**[!UICONTROL Text content]**&#x200B;部分中输入消息的内容，包括需要的个性化字段。

   ![](assets/sms-content.png)

1. 选择目标群体。

有关创建和设计短信的关键步骤，请参阅Campaign Classicv7文档：

* 创建短信

   ↗️ [了解如何创建短信投放](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* 设计短信内容

   ↗️ [了解如何定义短信内容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* 选择电子邮件的受众

   ↗️ [了解如何定义目标群体](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

??有关定义受众的详细步骤，请参见[本页](../start/audiences.md)。

## 测试短信

要查看消息的个性化呈现，请单击&#x200B;**[!UICONTROL Preview]**&#x200B;并选择收件人。

![](assets/sms-preview.png)

要发送校样，请参阅Campaign Classicv7文档的以下部分：

* 验证投放并发送校样
↗️ [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* 添加种子地址
↗️ [了解种子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## 发送和监控短信投放

有关发送和监控短信的关键步骤，请参阅Campaign Classicv7文档：

* 发送、监控和跟踪短信投放

   ↗️ [了解用于发送、监视和跟踪SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}的工具

* 短信投放疑难解答

   ↗️ [了解SMS疑难解答](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
