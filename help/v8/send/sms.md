---
title: 使用Adobe Campaign发送短信
description: Campaign短信入门
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# 创建和发送短信

使用Adobe Campaign发送个性化的短信消息。

请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target="_blank"}以了解如何开始使用短信渠道

>[!NOTE]
>
>Adobe Campaign还允许您通过其&#x200B;**Adobe Campaign移动应用程序渠道(NMAC)**&#x200B;选项在手机上提交推送通知。 可在[此部分](push.md)中了解详情。

## 配置短信渠道

要发送到手机，您需要：

* 指定连接器和消息类型的外部帐户。

* 引用此外部帐户的投放模板。

请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#sending-messages){target="_blank"}以了解如何配置短信渠道

开始发送短信之前：

* 确保收件人配置文件中至少包含一部手机。
* 查看同样适用于Campaign v8的Adobe Campaign Classic [投放最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=zh-Hans#sending-messages){target="_blank"}。

此外，您需要熟悉短信协议和设置。 在[本文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html#sending-messages){target="_blank"}中浏览Adobe Campaign与SMPP提供商之间的连接设置。

## 创建您的第一个短信投放

1. 要创建新投放，请浏览到&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL Deliveries]**，然后单击现有投放列表上方的&#x200B;**[!UICONTROL Create]**&#x200B;按钮。

   ![](assets/delivery_step_1.png)

   有关如何创建投放的全局信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html#sending-messages){target="_blank"}。

1. 选择引用相关外部帐户的投放模板以发送短信投放。

   ![](assets/sms-template-list.png)

   请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#creating-an-smpp-external-account){target="_blank"}以了解如何创建SMPP外部帐户

   请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#changing-the-delivery-template){target="_blank"}以了解如何创建投放模板以投放给移动设备

1. 使用标签、代码和描述标识投放。

1. 单击&#x200B;**[!UICONTROL Continue]**&#x200B;确认并显示消息配置窗口。

1. 在向导的&#x200B;**[!UICONTROL Text content]**&#x200B;部分中输入消息的内容，包括所需的个性化字段。

   ![](assets/sms-content.png)

1. 选择目标群体。

有关创建和设计短信的关键步骤，请参阅Campaign Classicv7文档：

* 创建短信

  [了解如何创建短信投放](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#sending-messages){target="_blank"}

* 设计短信内容

  [了解如何定义短信内容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#defining-the-sms-content){target="_blank"}

* 选择电子邮件的受众

  [了解如何定义目标群体](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

定义受众的步骤详见[此页面](../start/audiences.md)。

## 测试短信

要查看个性化邮件的呈现方式，请单击&#x200B;**[!UICONTROL Preview]**&#x200B;并选择收件人。

![](assets/sms-preview.png)

要发送校样，请参阅Campaign Classicv7文档的以下部分：

* 验证投放并发送校样
  [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hans){target="_blank"}
* 添加种子地址
  [了解种子地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## 发送和监测SMS投放

有关发送和监控短信的关键步骤，请参阅Campaign Classicv7文档：

* 发送、监控和跟踪短信投放

  [了解发送、监控和跟踪SMS的工具](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html#sending-messages){target="_blank"}

* 短信投放疑难解答

  [了解短信疑难解答](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html#sending-messages){target="_blank"}
