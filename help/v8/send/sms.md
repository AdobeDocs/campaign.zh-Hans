---
product: Adobe Campaign
title: 使用Adobe Campaign发送短信
description: Campaign中短信快速入门
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: 04f9d80e26fab372a1819590f8e79298c7a69ab5
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 3%

---

# 创建和发送短信

使用Adobe Campaign发送个性化的短信消息。

[!DNL :arrow_upper_right:] 在v7文档中了解如何开始使用 [短信渠道](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html)

>[!NOTE]
>
>Adobe Campaign还允许您通过其&#x200B;**Adobe Campaign移动设备应用程序渠道(NMAC)**&#x200B;选项在手机上提交推送通知。 在[此部分](push.md)中了解详情。

## 配置短信渠道

要发送到移动电话，您需要：

* 指定连接器和消息类型的外部帐户。

* 在其中引用此外部帐户的投放模板。

[!DNL :arrow_upper_right:]  了解如何在Campaign Classicv7文档中配 [置短信渠道](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages)

开始发送短信之前：

* 确保收件人的用户档案至少包含其用户档案中的移动电话。
* 查看Adobe Campaign Classic [投放最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages)，这些最佳实践也适用于Campaign v8。

此外，您还需要熟悉短信协议和设置。 浏览[本文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages)中Adobe Campaign与SMPP提供程序之间设置的连接。

## 创建您的首次短信投放

1. 要创建新投放，请浏览&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL Deliveries]** ，然后单击现有投放列表上方的&#x200B;**[!UICONTROL Create]**&#x200B;按钮。

   ![](assets/delivery_step_1.png)

   [!DNL :arrow_upper_right:] 有关如何创建投放的全局信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages)。

1. 选择引用相关外部帐户的投放模板以发送短信投放。

   ![](assets/sms-template-list.png)

   [!DNL :arrow_upper_right:] 了解如何在Campaign Classicv7文档中创建 [SMPP外部帐户](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account)

   [!DNL :arrow_upper_right:] 在Campaign Classicv7文档中了解如何创建投放模板以投放 [到手机](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template)

1. 使用标签、代码和描述标识投放。

1. 单击&#x200B;**[!UICONTROL Continue]**&#x200B;以确认并显示消息配置窗口。

1. 在向导的&#x200B;**[!UICONTROL Text content]**&#x200B;部分中输入消息的内容，包括需要的个性化字段。

   ![](assets/sms-content.png)

1. 选择目标群体。

有关创建和设计短信的关键步骤，请参阅Campaign Classicv7文档：

* 创建短信

   [!DNL :arrow_upper_right:] [了解如何创建短信投放](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages)

* 设计短信内容

   [!DNL :arrow_upper_right:] [了解如何定义短信内容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content)

* 选择电子邮件的受众

   [!DNL :arrow_upper_right:] [了解如何定义目标群体](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)

[!DNL :bulb:] 有关定义受众的详细步骤，请参 [阅本页](../start/audiences.md)。

## 测试短信

要查看消息的个性化呈现，请单击&#x200B;**[!UICONTROL Preview]**&#x200B;并选择收件人。

![](assets/sms-preview.png)

要发送校样，请参阅Campaign Classicv7文档的以下部分：

* 验证投放并发送校样
   [!DNL :arrow_upper_right:] [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* 添加种子地址
   [!DNL :arrow_upper_right:] [了解种子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## 发送和监控短信投放

有关发送和监控短信的关键步骤，请参阅Campaign Classicv7文档：

* 发送、监控和跟踪短信投放

   [!DNL :arrow_upper_right:] [了解发送、监控和跟踪短信的工具。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages)
* 短信投放疑难解答

   [!DNL :arrow_upper_right:] [了解短信疑难解答](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages)
