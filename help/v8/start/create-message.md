---
solution: Campaign v8
product: Adobe Campaign
title: 消息入门
description: 消息入门
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 4%

---

# 消息入门{#gs-ac-audiences}

借助Adobe Campaign，您可以发送跨渠道营销活动，包括电子邮件、短信、推送通知和直邮，并使用各种专用报告衡量其有效性。 这些消息通过投放进行设计和发送，并且可以针对每个收件人进行个性化设置。

核心功能包括定位、定义和个性化消息、执行通信和相关的运营报告。 主要功能接入点是投放助手。 此接入点可导致Adobe Campaign涵盖的多项功能。

了解在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html)中创建投放的关键步骤。

Adobe Campaign v8附带以下交付渠道：

* **电子邮件渠道**:电子邮件投放允许您向目标群体发送个性化电子邮件。在[此页面](../send/email.md)中了解详情。

* **直邮渠道**:通过直邮投放，可生成包含目标群体数据的提取文件。在[此页面](../send/direct-mail.md)中了解详情

* **移动渠道**:通过移动渠道投放，您可以向目标群体发送个性化短信。在[此页面](../send/sms.md)中了解详情

* **移动应用程序渠道**:通过移动设备应用程序投放，您可以向iOS和Android系统发送通知。在[此页面](../send/push.md)中了解详情

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## 选择如何发送邮件

创建消息并设计和测试其内容后，您可以选择发送方式。 Campaign提供一组功能，用于：

* 手动将消息发送到主目标
   [!DNL :arrow_upper_right:] [了解如何发送消息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* 发送与[营销活动](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)关联的消息
   [!DNL :arrow_upper_right:] [了解如何在活动上下文中发送消息](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html)。
* 通过[workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)发送消息
   [!DNL :arrow_upper_right:] [了解如何自动发送电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [触发](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) 来自事件的消息
   [!DNL :arrow_upper_right:] [用例：了解如何发送带有附件的事务型电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* 计划消息发送
   [!DNL :arrow_upper_right:] [用例：了解如何安排和发送生日电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## 添加个性化

由Adobe Campaign投放的消息可以通过各种方式进行个性化。

您可以：

* 插入动态的个性化字段。
   [!DNL :arrow_upper_right:] 了解如何在Campaign Classicv7文档中 [使用个性化字段](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* 插入预定义的个性化块.
   [!DNL :arrow_upper_right:] 了解什么是个性化块以及如何在 [Campaign Classicv7文档中使用](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)
* 创建条件性内容。
   [!DNL :arrow_upper_right:] 了解如何在Campaign Classicv7文 [档中插入条件内容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)

## 发送事务型消息

事务型消息传递（消息中心）是用于管理触发器消息的Campaign模块。

[!DNL :bulb:] 在此部分中了解有关事务型消息功能的 [更多信息](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] 有关配置和发送事务型消息的详细步骤，请参 [阅本页](../send/transactional.md)

[!DNL :arrow_upper_right:] 在Campaign Classicv7文档中的端到端用例中发现 [此功能](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)

## 投放和跟踪日志

监控投放发送后的投放是确保营销活动高效且能够与客户联系的关键步骤。 您可以在发送投放后进行监控，并了解投放失败和隔离的管理方式。

[!DNL :arrow_upper_right:] [在此部分中了解如何监控投放](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**相关主题**

[!DNL :arrow_upper_right:]  [投放最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

[!DNL :arrow_upper_right:]  [测试和发送电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [发送校样](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
