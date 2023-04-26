---
title: 开始使用消息
description: 开始使用消息
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 100%

---

# 消息入门{#gs-ac-audiences}

借助 Adobe Campaign，您可以发送跨渠道活动内容，包括电子邮件、短信、推送通知和直邮，并使用各种专门的报告衡量其有效性。这些消息通过投放设计和发送，并且可以针对每个收件人进行个性化。

核心功能包括定位、消息定义和个性化、通信执行和相关的运营报告。主要功能接入点是投放助手。此接入点可导向 Adobe Campaign 涵盖的多种功能。

Adobe Campaign v8 附带以下投放渠道：

* **电子邮件渠道**：电子邮件投放可让您向目标群体发送个性化电子邮件。请参阅[此页面](../send/email.md)以了解详情。

* **直邮渠道**：直邮投放允许您生成包含目标群体数据的提取文件。请参阅[此页面](../send/direct-mail.md)以了解详情

* **移动渠道**：移动渠道中的投放可让您向目标群体发送个性化短信。请参阅[此页面](../send/sms.md)以了解详情

* **移动应用程序渠道**：移动应用程序投放可让您向 iOS 和 Android 系统发送通知。请参阅[此页面](../send/push.md)以了解详情

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## 选择发送消息的方式{#gs-send-msg}

创建消息并对其内容进行设计和测试后，您可以选择发送消息的方式。Campaign 提供了一套功能用于：

* 手动将消息发送到主目标

   ![](assets/send-email.png)

   在[此部分](../send/send.md)中了解如何发送消息

* 发送与[营销活动](campaigns.md)关联的消息

   ![](assets/deliveries-in-a-campaign.png)

   在[此部分](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=zh-Hans)中了解如何在营销活动上下文中发送消息

* 通过[工作流](../config/workflows.md)发送消息

   ![](assets/send-in-a-wf.png)

   请参阅[此页面](../../automation/workflow/delivery.md)以了解如何自动化电子邮件投放

* 从事件[触发消息](../send/transactional.md)

* 计划消息发送

   ![](assets/schedule-send.png)

[用例：了解如何计划和发送生日电子邮件](../../automation/workflow/send-a-birthday-email.md)


## 添加个性化内容{#personalization}

由 Adobe Campaign 投放的消息可以通过各种方式实现个性化。[了解关于个性化功能的更多信息](../send/personalize.md)

您可以：

* 插入动态的个性化字段。[了解详情](../send/personalization-fields.md)
* 插入预定义的个性化块。[了解详情](../send/personalization-blocks.md)
* 创建条件性内容。[了解详情](../send/conditions.md)

## 发送事务性消息{#gs-transac-messages}

事务性消息（消息中心）是用于管理触发消息的 Campaign 模块。

请参阅[本节](../architecture/architecture.md#transac-msg-archi)以了解关于事务性消息功能的更多信息

有关配置和发送事务性消息的步骤详情，请参阅[此页面](../send/transactional.md)


## 投放和跟踪日志{#gs-tracking-logs}

在发送后监测投放是确保营销活动有效并接触到客户的重要步骤。您可以在发送投放后进行监测，并了解如何管理投放失败和隔离。

![](../assets/do-not-localize/book.png)在 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans#sending-messages){target="_blank"}中了解如何监测投放

