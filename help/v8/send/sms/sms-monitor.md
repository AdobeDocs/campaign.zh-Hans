---
title: 监控和跟踪短信
description: 关于短信投放的监控和跟踪
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 42be45db-3a90-4ad0-896d-f082afff1f8e
TQID: 'https://experienceleague.adobe.com/wETwv6lIEctnfT54WQjulzGxeCPo6lZDF-rxlwBtF4I'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# 监控和跟踪短信

务必监测短信投放，以确保营销活动有效。

以下是您需要了解发送投放后发生情况的可能性

## 了解短信投放仪表板

投放仪表板为您提供关于短信的很多信息。

要访问仪表板，请在投放列表中双击您的投放。

在&#x200B;**[!UICONTROL Summary]**&#x200B;选项卡中，您拥有主要数据，如已处理的消息数和成功数。

![SMS投放仪表板摘要选项卡，其中包含要发送的消息、已处理的消息和成功率，以及投放状态](assets/sms_summary.png){zoomable="yes"}

发送短信后，无法再访问与投放内容相关的&#x200B;**[!UICONTROL SMS]**&#x200B;选项卡以进行更改。

在&#x200B;**[!UICONTROL Delivery]**&#x200B;选项卡中，您了解有关投放日志的信息。 对于每个联系的地址，您可以查看该短信是否已发送

![投放选项卡日志列表显示对于每个联系的地址，是否发送了短信，以及状态和原因](assets/sms_deliverylogs.png){zoomable="yes"}

您可以在&#x200B;**[!UICONTROL Exclusions]**&#x200B;选项卡中查看有关为什么从目标中排除某些地址的详细信息。

![“传递”选项卡的“排除项”选项卡列出了原因已被忽略的地址，例如地址或Double](assets/sms_exclusions.png){zoomable="yes"}

**[!UICONTROL Tracking]**&#x200B;选项卡与跟踪有关。 以下是短信内容中跟踪的URL示例。

![跟踪选项卡URL列表，显示来自SMS内容的跟踪URL及其标签、类型和源URL](assets/sms_trackinglogs.png){zoomable="yes"}

最后，**[!UICONTROL Audit]**&#x200B;选项卡包含投放启动期间的所有详细信息：

![审核选项卡日志列出了投放启动期间记录的消息，包含日期和消息列](assets/sms_audit.png){zoomable="yes"}

## 了解短信故障

SMS的失败类型和失败原因与电子邮件相同。

详细了解[投放失败](../delivery-failures.md)，特别是有关[SMS隔离](../delivery-failures.md#sms-quarantines)。
