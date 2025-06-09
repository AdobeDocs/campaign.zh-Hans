---
title: 发送和监控电子邮件
description: 了解使用Adobe Campaign发送电子邮件的范围和特性
feature: Email
role: Data Engineer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 2%

---


# 发送和监控电子邮件  {#send-and-monitor-emails}

当投放已配置并准备好发送时，请确保已运行投放分析。 [了解详情](delivery-analysis.md)

完成后，确认投放以启动消息投放。

从&#x200B;**投放**&#x200B;选项卡跟踪投放的执行情况，可通过此投放的详细信息或投放列表进行访问。

## 监测电子邮件 {#email-monitoring}

发送后，在&#x200B;**投放仪表板**&#x200B;中检查您的投放状态，并访问投放日志和报告以确认消息已正确发送。

在投放仪表板中，您可以检查已处理的消息和投放审核日志。 您还可以控制投放日志中消息的状态。

>[!NOTE]
>
>投放状态不会实时显示。 在此部分](#email-feedback-service)中了解有关电子邮件反馈服务[的更多信息。


[请参阅Campaign Classic v7文档以了解有关投放监视的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}

## Campaign MTA {#mta}

Campaign v8邮件传输代理(MTA)提供了一流的发送基础架构，可实现最佳可投放性、信誉、吞吐量、报告、退回处理、IP提升和连接设置管理。

它适用于所有Campaign v8客户，可保证可扩展性和高投放吞吐量，并帮助更快地发送更多电子邮件。 这是通过新的自适应投放技术实现的，该技术根据来自互联网服务提供商的反馈实时更改电子邮件发送设置。

### 好处

Adobe Campaign使用邮件传输代理(MTA)，该代理运行SparkPost的商业电子邮件MTA，名为&#x200B;**Momentum**。

Momentum代表创新的高性能MTA技术，其中包括更智能的退回处理和自动化可投放性优化功能，可帮助发件人实现并保持最佳收件箱投放率。

* MTA允许整体吞吐量速度的大幅提高和软退回的显着减少。
* 它使用最新的MTA技术为您的电子邮件投放提供最佳吞吐速度。
* 通过即时且自动地适应其收到的反馈，它还可以确保利用实时投放数据更准确、更智能地投放电子邮件。

### 退回鉴别

对于&#x200B;**同步**&#x200B;投放失败错误消息，MTA将确定退回类型和鉴别，并将该信息发回至Campaign。

MTA鉴定SMTP退回资格，并以映射到Campaign退回原因和资格的退回代码的形式将该鉴定发送回Campaign。

>[!NOTE]
>
>当前&#x200B;**异步**&#x200B;退回由inMail进程通过&#x200B;**[!UICONTROL Inbound email]**&#x200B;规则进行鉴别。

在[本节](delivery-failures.md)中了解有关投放失败的更多信息。


### 特定的MX规则

MX规则（邮件交换器）是管理发送服务器和接收服务器之间通信的规则。

MTA有自己的MX规则，根据您自己的历史电子邮件信誉以及来自您发送电子邮件之域名的实时反馈，按域自定义您的吞吐量。

### DKIM-signing

Domain Keys Identified Mail (DKIM)是一种用于检测伪造发件人地址（通常称为欺骗）的身份验证方法。

在Adobe Campaign中，DKIM电子邮件身份验证签名由MTA执行。

在[DKIM可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}中了解有关Adobe的更多信息。

## 电子邮件反馈服务 {#email-feedback-service}

Campaign电子邮件反馈服务(EFS)报告使用Adobe Campaign发送的每个电子邮件投放的状态。

投放开始后，当消息成功从Campaign中继到MTA时，**[!UICONTROL Success]**&#x200B;百分比没有变化。 投放日志显示每个目标地址的&#x200B;**[!UICONTROL Taken into account by the service provider]**&#x200B;状态。

当消息实际传送到目标用户档案并从MTA实时报告此信息后，投放日志显示成功收到消息的每个地址的&#x200B;**[!UICONTROL Sent]**&#x200B;状态。 每次成功投放后，**[!UICONTROL Success]**&#x200B;百分比都会相应增加。

从MTA报告硬退回邮件时，其日志状态将从&#x200B;**[!UICONTROL Taken into account by the service provider]**&#x200B;更改为&#x200B;**[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->。

从MTA报告软退回消息时，其日志状态保持不变(**[!UICONTROL Taken into account by the service provider]**)：仅更新[错误原因](delivery-failures.md#delivery-failure-reasons)<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->。 **[!UICONTROL Success]**&#x200B;百分比保持不变。 然后，在投放[有效期](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}内重试软退回邮件：

* 如果在有效期结束前重试成功，则消息状态将更改为&#x200B;**[!UICONTROL Sent]**，并相应地增加&#x200B;**[!UICONTROL Success]**&#x200B;百分比。

* 否则，状态将更改为&#x200B;**[!UICONTROL Failed]**。 **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->百分比保持不变。

>[!NOTE]
>
>有关硬退信和软退信的详细信息，请参阅[此部分](delivery-failures.md#delivery-failure-reasons)。
>
>有关投放临时失败后重试的详细信息，请参阅[此部分](delivery-failures.md#retries)。

下表显示在发送过程的每个步骤如何更新KPI和发送日志状态。

| 发送过程中的步骤 | KPI摘要 | 发送日志状态 |
|--- |--- |--- |
| 消息已成功从Campaign中继到MTA | 不显示&#x200B;**[!UICONTROL Success]**&#x200B;百分比（从0%开始） | 由服务提供商考虑 |
| 从MTA返回硬退回消息 | **[!UICONTROL Success]**&#x200B;百分比无变化 | 失败 |
| 从MTA返回软退回消息 | **[!UICONTROL Success]**&#x200B;百分比无变化 | 由服务提供商考虑 |
| 软退回消息重试成功 | **[!UICONTROL Success]**&#x200B;百分比将相应增加 | 已发送 |
| 软退回消息重试失败 | **[!UICONTROL Success]**&#x200B;百分比无变化 | 失败 |
