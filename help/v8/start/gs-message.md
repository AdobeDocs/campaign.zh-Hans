---
title: 开始使用消息
description: 开始使用消息
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a523e76d-776c-47d3-9c15-34241cee1092
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 73%

---

# 消息入门 {#gs-ac-msg}

借助 Adobe Campaign，您可以发送跨渠道活动内容，包括电子邮件、短信、推送通知和直邮，并使用各种专门的报告衡量其有效性。这些消息通过投放设计和发送，并且可以针对每个收件人进行个性化。

核心功能包括定向、消息定义和个性化、通信执行和相关的运营报告。

## 用例 {#gs-ac-delivery}

要发送消息，您必须创建投放。 投放创建模式取决于您的用例。

>[!NOTE]
>
>创建投放时，必须选择模板。 每个渠道都有默认模板可用。 在[此页面](../send/create-templates.md)中了解有关投放模板的更多信息。

1. **一次性消息** — 您可以向受众发送一次性消息。 在[本节](create-message.md)中了解如何发送您的第一条消息。

   ![](assets/send-email.png)

1. **营销活动中的消息** — 您可以在[营销活动](campaigns.md)的上下文中发送消息、定义审批流程、在合并的仪表板中发送和跟踪消息。 在[本节](../../automation/campaigns/marketing-campaign-deliveries.md)中了解详情。

   ![](assets/deliveries-in-a-campaign.png)

1. 工作流中的&#x200B;**消息** — 您可以通过[工作流](../config/workflows.md)发送消息，并自动完成投放。 在[此页面](../../automation/workflow/delivery.md)中了解详情。

   ![](assets/send-in-a-wf.png)

1. **触发的消息** — 您可从事件[触发消息](../send/transactional.md)。 事务性消息（消息中心）是用于管理触发消息的Campaign模块。 有关配置和发送事务性消息的步骤详情，请参阅[此页面](../send/transactional.md)

## 通信渠道 {#gs-channel}

Adobe Campaign v8附带如下交付渠道。 环境中可用的渠道取决于您的合同。 请核实您的许可协议。

* **电子邮件渠道**：电子邮件投放可让您向目标群体发送个性化电子邮件。[了解更多信息](../send/email.md)

* **移动渠道**：移动渠道投放可让您向目标群体的移动设备发送个性化消息。您可以在手机上发送[短信](../send/sms/sms.md)和[LINE](../send/line/line.md)消息。

* **移动应用程序渠道**：您可以使用Adobe Campaign通过专用应用程序在iOS和Android移动设备上发送个性化的分段[推送通知](../send/push.md)。 完成配置和集成步骤后，即可通过 Adobe Campaign 创建和发送 iOS 和 Android 投放。您还可以设计包含图像或视频的丰富通知并将其发送到 Android 设备。

* **直邮渠道**： [直邮](../send/direct-mail.md)是一个脱机渠道，允许您创建、个性化和生成外部文件以与直邮提供商共享。 使用此渠道可在客户历程中编排在线和离线渠道。

  在准备直邮投放时，Adobe Campaign 会生成一个文件，其中包含了所有定向的轮廓和选定的联系信息（例如邮政地址）。然后，您可以将此文件发送给直邮提供商，由其负责发送纸质信函。


* **其他渠道**： Adobe Campaign还随附用于创建外部投放的电话投放模板。 使用此渠道意味着您实施专用方法来处理输出文件。配置步骤与[直邮渠道](../send/direct-mail.md)相同。

  >[!NOTE]
  >
  >电话渠道不是内置渠道。实施时需要咨询 Adobe Consulting 或 Adobe 合作伙伴。有关更多信息，请联系您的 Adobe 代表。

  “其他”类型投放使用特定技术模板，不会执行流程：这使其能够管理在 Adobe Campaign 平台外部执行的营销操作。

  此渠道没有特定的机制。该渠道是一般渠道，与在 Adobe Campaign 中提供的任何其他通信渠道一样，具有自己的外部帐户路由选项、投放模板类型和营销活动工作流活动。 此渠道仅用于描述性目的，例如定义要跟踪在 Adobe Campaign 以外的工具中执行的营销活动的目标投放。

## 投放类型 {#types-of-deliveries}

Campaign 中有三种类型的投放对象：

### 单个投放 {#single-delivery}

**投放**&#x200B;是一个独立投放对象，只执行一次。可以重复再次准备投放，但如果投放处于最终状态（取消、停止、完成），就无法再重复使用。

可以从投放列表创建投放，也可以通过[投放](../../automation/workflow/delivery.md)活动在工作流中创建投放。

工作流还可根据要使用的渠道类型提供特定的投放活动。有关这些活动的详细信息，请参阅[此部分](../../automation/workflow/cross-channel-deliveries.md)。

### 定期投放 {#recurring-delivery}

**定期投放**&#x200B;位于工作流上下文中。它允许您在每次执行活动时创建新投放。这可让您不必为周期性任务创建新投放。例如，如果您每月运行一次此类活动，那么一年后最终将有 12 次投放。

定期投放是通过[定期投放活动](../../automation/workflow/recurring-delivery.md)在工作流中创建的。这一部分中介绍了使用此活动的示例：[在目标选择工作流中创建定期投放](../../automation/workflow/send-a-birthday-email.md)。

### 持续投放 {#continuous-delivery}

**持续投放**&#x200B;位于工作流上下文中。它可让您向现有投放添加新收件人，从而避免每次执行活动时都必须创建新投放。

如果投放中的信息发生更改（内容、名称等），则会在投放执行时创建新投放对象。如果未更改任何信息，则将重用同一投放对象，并将投放和跟踪日志添加到同一对象中。

例如，如果您每月运行一次此类活动，那么一年后您将只运行一次投放（如果您未对投放进行任何更改）。

持续投放是通过[持续投放活动](../../automation/workflow/continuous-delivery.md)在工作流中创建的。

## Personalization功能 {#personalization}

由 Adobe Campaign 投放的消息可以通过各种方式实现个性化。[了解关于个性化功能的更多信息](../send/personalize.md)

您可以：

* 插入动态的个性化字段。[了解详情](../send/personalization-fields.md)
* 插入预定义的个性化块。[了解详情](../send/personalization-blocks.md)
* 创建条件性内容。[了解详情](../send/conditions.md)


## 跟踪和监控 {#gs-tracking-logs}

在发送后监测投放是确保营销活动有效并接触到客户的重要步骤。您可以在发送投放后进行监测，并了解如何管理投放失败和隔离。

请参阅[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans#sending-messages){target="_blank"}以了解如何监测投放
