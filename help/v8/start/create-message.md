---
product: Adobe Campaign
title: 开始使用消息
description: 开始使用消息
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 72%

---

# 开始使用消息{#gs-ac-audiences}

借助Adobe Campaign，您可以发送跨渠道营销活动，包括电子邮件、短信、推送通知和直邮，并使用各种专用报告衡量其有效性。 这些消息通过投放设计和发送，并且可以针对每个收件人进行个性化。

核心功能包括定位、消息定义和个性化、通信执行和相关的运营报告。主要功能接入点是投放助手。此接入点可导向 Adobe Campaign 涵盖的多种功能。

了解在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=zh-Hans)中创建投放的关键步骤。

Adobe Campaign v8 附带以下投放渠道：

* **电子邮件渠道**：电子邮件投放可让您向目标群体发送个性化电子邮件。请参阅[此页面](../send/email.md)以了解详情。

* **直邮渠道**：直邮投放允许您生成包含目标群体数据的提取文件。请参阅[此页面](../send/direct-mail.md)以了解详情

* **移动渠道**：移动渠道中的投放可让您向目标群体发送个性化短信。请参阅[此页面](../send/sms.md)以了解详情

* **移动应用程序渠道**：移动应用程序投放可让您向 iOS 和 Android 系统发送通知。请参阅[此页面](../send/push.md)以了解详情

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## 选择发送消息的方式

创建消息并对其内容进行设计和测试后，您可以选择发送消息的方式。Campaign 提供了一套功能用于：

* 手动将消息发送到主目标
   [!DNL :arrow_upper_right:] [了解如何发送消息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=zh-Hans)
* 发送与[营销活动](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=zh-Hans)关联的消息
   [!DNL :arrow_upper_right:] [了解如何在活动上下文中发送消息](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=zh-Hans)。
* 通过[workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=zh-Hans)发送消息
   [!DNL :arrow_upper_right:] [了解如何自动发送电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=zh-Hans)
* [触发](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=zh-Hans) 来自事件的消息
   [!DNL :arrow_upper_right:] [用例：了解如何发送带有附件的事务型电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=zh-Hans)
* 计划消息发送
   [!DNL :arrow_upper_right:] [用例：了解如何安排和发送生日电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=zh-Hans)


## 添加个性化内容

由 Adobe Campaign 投放的消息可以通过各种方式实现个性化。

您可以：

* 插入动态的个性化字段。

   [!DNL :arrow_upper_right:] 了解如何在Campaign Classicv7文档中 [使用个性化字段](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=zh-Hans)
* 插入预定义的个性化块。

   [!DNL :arrow_upper_right:] 了解什么是个性化块以及如何在 [Campaign Classicv7文档中使用](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=zh-Hans)
* 创建条件内容。

   [!DNL :arrow_upper_right:] 了解如何在Campaign Classicv7文 [档中插入条件内容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=zh-Hans)

## 发送事务性消息

事务性消息（消息中心）是用于管理触发消息的 Campaign 模块。

[!DNL :bulb:] 请参阅[本节](../dev/architecture.md#transac-msg-archi)以进一步了解事务性消息功能

[!DNL :bulb:] 配置和发送事务性消息的步骤详见[此页面](../send/transactional.md)

[!DNL :arrow_upper_right:] 在Campaign Classicv7文档中的端到端用例中发现 [此功能](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=zh-Hans#transactional-messaging)

## 投放和跟踪日志

在发送后监测投放是确保营销活动有效并接触到客户的重要步骤。您可以在发送投放后进行监测，并了解如何管理投放失败和隔离。

[!DNL :arrow_upper_right:] [在此部分中了解如何监控投放](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans#sending-messages)


**相关主题**

[!DNL :arrow_upper_right:]  [投放最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=zh-Hans)

[!DNL :arrow_upper_right:]  [测试和发送电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [发送校样](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hans)
