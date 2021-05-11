---
solution: Campaign
product: Adobe Campaign
title: 消息入门
description: 消息入门
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
translation-type: tm+mt
source-git-commit: 3fe4156149e9ff8724dd1ff5fc17b538e6055ef8
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 3%

---

# 消息{#gs-ac-audiences}入门

借助Adobe Campaign，您可以发送跨渠道活动，包括电子邮件、短信、LINE消息、推送通知和直接邮件，并使用各种专用报告衡量其有效性。 这些消息是通过投放设计和发送的，并且可以针对每个收件人进行个性化。

核心功能包括定位、消息的定义和个性化、通信的执行和相关的运营报告。 主要功能接入点是投放助理。 此接入点可实现Adobe Campaign覆盖的多种功能。

了解在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html)中创建投放的关键步骤。

Adobe Campaign v8附带以下投放渠道:

* **电子邮件渠道**:电子邮件投放可让您向目标群发送个性化电子邮件。请阅读[本页](../send/email.md)了解更多信息。

* **直邮渠道**:直接邮件投放允许您生成包含目标填充数据的提取文件。了解有关[此页面](../send/direct-mail.md)的详细信息

* **移动渠道**:移动渠道上的投放可让您向目标群发送个性化短信。了解有关[此页面](../send/sms.md)的详细信息

* **移动应用程序渠道**:移动应用程序投放可让您向iOS和Android系统发送通知。了解有关[此页面](../send/push.md)的详细信息

* **行渠道**:LINE投放允许您在LINE上发送消息，LINE是所有智能手机上都可用的即时消息应用程序。了解有关[此页面](../send/line.md)的详细信息

## 选择发送消息的方式

创建消息并对其内容进行设计和测试后，您可以选择发送消息的方式。 活动优惠一组功能可以：

* 手动将消息发送到主目标
:arrow_upper_right:[了解如何发送消息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* 发送与[营销活动](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)关联的消息
:arrow_upper_right:[了解如何在活动](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html)的上下文中发送消息。
* 通过[工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)发送消息
:arrow_upper_right:[了解如何自动化电子邮件投放](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [触发](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) 来自事件的消息：arrow_upper_right: [用例：了解如何发送包含附件的交易电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* 计划您的消息
:arrow_upper_right:[用例：了解如何计划和发送生日电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## 添加个性化

通过Adobe Campaign传递的信息可以通过各种方式实现个性化。

您可以：

* 插入动态的个性化字段。:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)中使用个性化字段
* 插入预定义的个性化块.
:arrow_upper_right:了解什么是个性化基块以及如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)中使用它
* 创建条件性内容。:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)中插入条件内容

## 发送事务性消息

事务消息（消息中心）是用于管理触发消息的活动模块。

：灯泡：了解有关[本节](../dev/architecture.md#transac-msg-archi)中事务性消息功能的更多信息

：灯泡：配置和发送事务性消息的步骤详见[此页](../send/transactional.md)

:arrow_upper_right:在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)中的端到端使用案例中发现此功能

## 投放和跟踪日志

在发送投放后监控活动是确保营销高效并与客户沟通的关键步骤。 您可以在发送投放后进行监控，并了解如何管理投放故障和隔离。

:arrow_upper_right:[了解如何在本节](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)中监控投放


**相关主题**

:arrow_upper_right: [投放最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:arrow_upper_right: [测试并发送电子邮件](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:arrow_upper_right: [发送验证](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
