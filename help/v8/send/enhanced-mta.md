---
title: 在Adobe Campaign中使用Enhanced MTA发送
description: 了解使用Adobe Campaign Enhanced MTA发送电子邮件的范围和特性
feature: Email
role: Data Engineer
level: Beginner
source-git-commit: 448436d56d14dca2d18088ebfc94f9e21ebb58c4
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 4%

---

# 使用增强 MTA 发送 {#sending-with-enhanced-mta}

的 **Adobe Campaign增强MTA** （邮件传输代理）提供了升级的发送基础结构，以实现最佳投放能力、信誉、吞吐量、报告、退件处理、IP升级和连接设置管理。

它的实施旨在提高可扩展性、提高投放吞吐量并帮助更快地发送更多电子邮件。 这是通过新的自适应投放技术实现的，这种技术可以根据互联网服务提供商的反馈实时更改电子邮件发送设置。

## 使用和好处

**什么是Enhanced MTA?**

Adobe Campaign使用邮件传输代理(MTA)，该代理运行SparkPost的商业电子邮件MTA，名为 **动量**.

Mommentum代表了创新的高性能MTA技术，该技术包括更智能的跳出处理和自动投放能力优化功能，可帮助发件人实现并保持最佳收件箱投放率。

**有什么好处？**

* Enhanced MTA可大幅提升整体吞吐量速度并显着降低软退回。
* 它使用最新的MTA技术为您的电子邮件投放提供最佳吞吐量速度。
* 通过即时且自动地适应收到的反馈，它还可确保利用实时投放数据进行更准确、更智能的电子邮件投放。

## 增强的MTA特性 {#enhanced-mta-impacts}

### 退回鉴别

对于 **同步** 投放失败错误消息时，Enhanced MTA会确定退回类型并进行鉴别，然后将该信息发送回Campaign。

Enhanced MTA符合SMTP退回的条件，并以映射到促销活动退回原因和鉴别的退回代码的形式，将该鉴别发送回Campaign。

>[!NOTE]
>
>当前 **异步** 退回由inMail流程通过 **[!UICONTROL Inbound email]** 规则。 有关更多信息，请参阅 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}。 <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

了解有关投放失败的更多信息，请参阅 [此部分](delivery-failures.md).

### 有效期

仅当将设置为 **3.5天或以下**. 如果您在Campaign中定义的值超过3.5天，则不会将其考虑在内。

例如，如果在Campaign中将有效期设置为默认值5天，则软跳出消息将进入Enhanced MTA重试队列，并在消息到达Enhanced MTA后仅重试3.5天。 在这种情况下，将不使用Campaign中设置的值。

消息在 Enhanced MTA 队列中停留 3.5 天且投放失败后，该消息将超时，在投放日志中的状态将从 **[!UICONTROL Sent]** 更新为 **[!UICONTROL Failed]**。

有关有效期的更多信息，请参阅 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}。

### 重试

软退件重试次数及其间隔时间，由Enhanced MTA根据从消息电子邮件域返回的退回响应的类型和严重性确定。

>[!NOTE]
>
>Campaign不使用投放属性中的重试设置。

了解有关重试的更多信息(位于 [此部分](delivery-failures.md#retries).

### 特定MX规则

MX规则（邮件eXchanger）是管理发送服务器与接收服务器之间通信的规则。

Enhanced MTA有其自己的MX规则，允许根据您自己的历史电子邮件信誉以及来自您发送电子邮件的域的实时反馈，按域自定义您的吞吐量。

### DKIM签名

域名密钥标识邮件(DKIM)是一种身份验证方法，用于检测伪造的发件人地址（通常称为欺骗）。

在Adobe Campaign中，DKIM电子邮件身份验证签名由增强的MTA执行。

了解有关DKIM的更多信息，请参阅 [Adobe投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target=&quot;_blank&quot;}。

## 电子邮件反馈服务 {#email-feedback-service}

利用电子邮件反馈服务(EFS)功能，可以准确报告每封电子邮件的状态，因为反馈是直接从增强型MTA（邮件传输代理）中捕获的。

投放开始后， **[!UICONTROL Success]** 成功从Campaign中继到增强型MTA时的百分比。

投放日志显示 **[!UICONTROL Taken into account by the service provider]** 每个目标地址的状态。

当消息实际被投放到目标用户档案，并且从Enhanced MTA实时报告此信息后，投放日志会显示 **[!UICONTROL Sent]** 成功接收消息的每个地址的状态。 的 **[!UICONTROL Success]** 百分比随每次成功交付而相应增加。

当硬弹回消息从增强型MTA返回报告时，其日志状态会从 **[!UICONTROL Taken into account by the service provider]** to **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

当从Enhanced MTA报告软弹回消息时，其日志状态保持不变(**[!UICONTROL Taken into account by the service provider]**):只有 [错误原因](delivery-failures.md#delivery-failure-reasons) 已更新<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. 的 **[!UICONTROL Success]** 百分比保持不变。 然后，在整个投放中重试软弹回消息 [有效期](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

* 如果在有效期结束前重试成功，则消息状态将更改为 **[!UICONTROL Sent]** 和 **[!UICONTROL Success]** 百分比也相应地增加。

* 否则，状态将更改为 **[!UICONTROL Failed]**. 的 **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->百分比保持不变。

>[!NOTE]
>
>有关硬退回和软退回的更多信息，请参阅 [此部分](delivery-failures.md#delivery-failure-reasons).
>
>有关投放临时失败后重试的更多信息，请参阅 [此部分](delivery-failures.md#retries).

下表显示了在发送流程的每个步骤中如何使用EFS功能更新KPI和发送日志状态。

| 发送流程中的步骤 | KPI摘要 | 发送日志状态 |
|--- |--- |--- |
| 已成功将消息从Campaign中继到增强MTA | **[!UICONTROL Success]** 百分比未显示（从0%开始） | 服务提供商考虑 |
| 硬弹回消息从增强的MTA中报回 | 中未更改 **[!UICONTROL Success]** 百分比 | 失败 |
| 从Enhanced MTA报告软弹回消息 | 中未更改 **[!UICONTROL Success]** 百分比 | 服务提供商考虑 |
| 软弹回消息重试成功 | **[!UICONTROL Success]** 百分比相应地增加 | 已发送 |
| 软弹回消息重试失败 | 中未更改 **[!UICONTROL Success]** 百分比 | 失败 |

