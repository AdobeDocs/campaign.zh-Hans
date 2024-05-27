---
title: 开始使用消息
description: 开始使用消息
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: fb0b7dbeae1d083935da91bbe50a711ce5f47b7e
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 29%

---

# 消息入门{#gs-ac-audiences}

借助 Adobe Campaign，您可以发送跨渠道活动内容，包括电子邮件、短信、推送通知和直邮，并使用各种专门的报告衡量其有效性。这些消息通过投放设计和发送，并且可以针对每个收件人进行个性化。

核心功能包括定位、消息定义和个性化、通信执行和相关的运营报告。主要功能接入点是投放助手。此接入点可导向 Adobe Campaign 涵盖的多种功能。

Adobe Campaign v8 附带以下投放渠道：

* **电子邮件渠道**：电子邮件投放可让您向目标群体发送个性化电子邮件。[了解更多信息](#gs-channel-email)

* **移动渠道**：移动渠道中的投放可让您在移动设备上向目标群体发送个性化消息。 [了解更多信息](#gs-channel-sms)

* **移动应用程序渠道**：移动应用程序投放可让您向iOS和Android设备发送通知。 [了解更多信息](#gs-channel-push)

* **直邮渠道**：直邮投放允许您生成包含目标群体数据的提取文件。 [了解更多信息](#gs-channel-direct)


  有关其他渠道的介绍，请参见 [本节](#other-channels).

  >[!NOTE]
  >
  >可用渠道的数量取决于您的合同。 请核实您的许可协议。

## 选择您的渠道{#gs-channel}

### 电子邮件渠道 {#gs-channel-email}

此 [电子邮件渠道](../send/direct-mail.md) 是Adobe Campaign中的核心渠道之一，允许您向特定目标计划和发送个性化电子邮件。

您可以发送不同类型的电子邮件：

* 单次发送电子邮件：可发送给已定义目标的电子邮件。 它们通常用于促销只需准备并发送一次的特定内容（新闻稿、促销电子邮件等）。
* 定期电子邮件：在营销活动中，定期发送相同的电子邮件，并定期汇总每个发送及其报告。 同一电子邮件会发送，但通常根据发送日期的符合条件目标发送给其他目标。 一个常见示例是生日电子邮件。 有关详细信息，请参见 [定期投放](../../automation/workflow/recurring-delivery.md).
* 事务性电子邮件：根据客户的行为触发的统一电子邮件。 请参阅 [事务性消息传递](../send/transactional.md).

要了解投放使用方法和建议，请参阅Adobe Campaign Classic [投放最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"}

有关不同类型投放的更多信息，请参阅 [本节](#types-of-deliveries).

### 移动渠道 {#gs-channel-sms}

Adobe Campaign允许您交付 [短信](../send/sms.md) 和 [折线图](../send/line.md) 手机上的消息。

对于短信消息，您可以仅以文本格式创建、修改和个性化消息。 您还可以在发送短信之前预览短信。

对于LINE消息，可以发送文本或图像和链接。

要将SMS或LINE消息投放到手机，您需要：

* 在上配置的外部帐户 **[!UICONTROL Mobile (SMS)]** 频道或在 **[!UICONTROL LINE]** 渠道。
* 正确链接到此外部帐户的SMS或LINE投放模板。


### 推送通知渠道 {#gs-channel-push}

您可以使用Adobe Campaign发送个性化和分段的 [推送通知](../send/push.md) 在iOS和Android移动设备上，通过专用应用程序访问。 执行配置和集成步骤后，即可通过Adobe Campaign创建和发送iOS和Android投放。 您还可以设计包含图像或视频的丰富通知并将其发送到Android设备。

### 直邮渠道 {#gs-channel-direct}

[直邮](../send/direct-mail.md) 是一个离线渠道，允许您创建、个性化和生成外部文件以与直邮提供商共享。 使用此渠道在客户历程中编排在线和离线渠道。

在准备直邮投放时，Adobe Campaign 会生成一个文件，其中包含了所有定向的用户档案和选定的联系信息（例如邮政地址）。然后，您可以将此文件发送给直邮提供商，由其负责发送纸质信函。


### 其他渠道 {#other-channels}

Adobe Campaign还附带一个电话投放模板，用于创建外部投放。 使用此渠道意味着您实施专用方法来处理输出文件。 配置步骤与相同 [直邮渠道](../send/direct-mail.md).

>[!NOTE]
>
>电话渠道不是内置渠道。 其实施需要与Adobe咨询或Adobe合作伙伴合作。 有关更多信息，请联系您的Adobe代表。

“其他”类型投放使用不会执行流程的特定技术模板：这使他们能够管理在Adobe Campaign平台外部执行的营销操作。

此渠道没有特定的机制。 该渠道与在Adobe Campaign中提供的任何其他通信渠道一样，具有自己的外部帐户路由选项、投放模板类型和活动工作流活动。 此渠道仅用于描述性目的，例如，定义要跟踪在Adobe Campaign以外的工具中执行的营销活动目标的投放。

## 选择投放类型 {#types-of-deliveries}

Campaign中有三种类型的投放对象：

### 单个投放 {#single-delivery}

A **投放** 是一个独立投放对象，只执行一次。 它可以重复，再次准备，但只要它处于最终状态（已取消、已停止、已完成），就无法重复使用。

可以从投放列表创建投放，也可以通过在工作流中创建投放 [投放](../../automation/workflow/delivery.md) 活动。

工作流还可根据要使用的渠道类型提供特定的投放活动。 有关这些活动的更多信息，请参阅 [本节](../../automation/workflow/cross-channel-deliveries.md).

### 循环投放 {#recurring-delivery}

A **循环投放** 在工作流上下文中可用。 它允许您在每次执行活动时创建新投放。 这可让您不必为周期性任务创建新投放。 例如，如果您每月运行一次此类活动，那么一年后最终将有12次投放。

定期投放是通过在工作流中创建的 [循环投放活动](../../automation/workflow/recurring-delivery.md). 此部分中介绍了正在使用的此活动的示例： [在定位工作流中创建循环投放](../../automation/workflow/send-a-birthday-email.md).

### 连续投放 {#continuous-delivery}

A **连续投放** 在工作流上下文中可用。 它可让您向现有投放添加新收件人，从而避免每次执行投放时都必须创建新投放。

如果投放中的信息发生更改（内容、名称等），则会在投放执行时创建新投放对象。 如果未更改任何信息，则将重用同一投放对象，并将投放和跟踪日志添加到同一对象中。

例如，如果您每月运行一次此类活动，那么一年后您将只运行一次投放（前提是您未对投放进行任何更改）。

连续投放是通过在工作流中创建的 [连续投放活动](../../automation/workflow/continuous-delivery.md).


## 选择发送消息的方式{#gs-send-msg}

创建消息并对其内容进行设计和测试后，您可以选择发送消息的方式。Campaign 提供了一套功能用于：

* 手动将消息发送到主目标

  ![](assets/send-email.png)

  在[此部分](../send/send.md)中了解如何发送消息

* 发送与[营销活动](campaigns.md)关联的消息

  ![](assets/deliveries-in-a-campaign.png)

  要了解如何在活动上下文中发送消息，请参阅[此部分](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=zh-Hans){target="_blank"}

* 通过[工作流](../config/workflows.md)发送消息

  ![](assets/send-in-a-wf.png)

  请参阅[此页面](../../automation/workflow/delivery.md)以了解如何自动化电子邮件投放

* 从事件[触发消息](../send/transactional.md)

  事务性消息（消息中心）是用于管理触发消息的 Campaign 模块。

  请参阅[本节](../architecture/architecture.md#transac-msg-archi)以了解关于事务性消息功能的更多信息

  有关配置和发送事务性消息的步骤详情，请参阅[此页面](../send/transactional.md)

* 计划消息发送

  ![](assets/schedule-send.png)

  了解如何在中计划发送投放 [此页面](../send/configure-and-send.md)

  另请参阅此 [用例：了解如何计划和发送生日电子邮件](../../automation/workflow/send-a-birthday-email.md)


## 添加个性化内容{#personalization}

由 Adobe Campaign 投放的消息可以通过各种方式实现个性化。[了解关于个性化功能的更多信息](../send/personalize.md)

您可以：

* 插入动态的个性化字段。[了解详情](../send/personalization-fields.md)
* 插入预定义的个性化块。[了解详情](../send/personalization-blocks.md)
* 创建条件性内容。[了解详情](../send/conditions.md)


## 投放和跟踪日志{#gs-tracking-logs}

在发送后监测投放是确保营销活动有效并接触到客户的重要步骤。您可以在发送投放后进行监测，并了解如何管理投放失败和隔离。

要了解如何监测投放，请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans#sending-messages){target="_blank"}

