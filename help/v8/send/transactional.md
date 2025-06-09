---
title: Campaign事务性消息传递
description: 事务性消息传递入门
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 253f3be945cbfa304fa7342c68f0c73b079e2870
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# 事务性消息传递入门{#send-transactional-messages}

事务性消息（消息中心）是用于管理触发消息的Campaign模块。 这些通知是从信息系统触发的事件生成的，可以是：发票、订单确认、发运确认、密码更改、产品不可用通知、帐户对帐单、网站帐户创建等。

>[!NOTE]
>
>作为托管云服务用户，[联系Adobe](../start/campaign-faq.md#support){target="_blank"}以在您的环境中配置Campaign事务性消息传递。

事务型消息用于发送：

* 通知，例如订单确认或密码重置
* 对客户操作的单个实时响应
* 非促销内容

[此部分](../config/transactional-msg-settings.md)中详细介绍了事务性消息设置。

了解[此页面](../architecture/architecture.md#transac-msg-archi)上的事务性消息传递架构。

## 事务型消息传递工作原理 {#transactional-messaging-operating-principle}

Adobe Campaign事务性消息传递模块集成到一个信息系统中，该信息系统返回要更改为个性化事务性消息的事件。 这些消息可以通过电子邮件、短信或推送通知单独或批量发送。

例如，假设您是一家设有网站的公司，您的客户可以在其中购买产品。

Adobe Campaign允许您向将产品添加到购物车的客户发送通知电子邮件。 当其中某个访客离开您的网站而未完成购买（触发营销活动事件的外部事件）时，会自动向他们发送购物车放弃电子邮件（事务性消息投放）。

要实现该目标，主要步骤详述如下：

1. [创建事件类型](#create-event-types)。
1. [创建并设计消息模板](transactional-template.md#create-message-template)。 在此步骤中，必须将事件链接到消息。
1. [测试邮件](transactional-template.md#test-message-template)。
1. [发布消息模板](transactional-template.md#publish-message-template)。

设计和发布事务性消息模板后，如果触发了相应的事件，则会通过PushEvent和PushEvents [SOAP方法](../send/event-description.md)将相关数据发送到Campaign，并将投放发送到目标收件人。

## 创建事件类型 {#create-event-types}

为确保每个事件都可以更改为个性化消息，您首先需要创建&#x200B;**事件类型**。

在[创建消息模板](#create-message-template)时，您将选择与要发送的消息匹配的事件类型。

>[!CAUTION]
>
>必须先创建事件类型，然后才能在消息模板中使用它们。

要创建将由Adobe Campaign处理的事件类型，请执行以下步骤：

1. 浏览到Campaign资源管理器的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;文件夹。
1. 从列表中选择&#x200B;**[!UICONTROL Event type]**&#x200B;枚举。
1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;创建枚举值。 这可以是订单确认、密码更改、订单交付更改等。

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >每个事件类型必须匹配&#x200B;**[!UICONTROL Event type]**&#x200B;枚举中的一个值。

1. 创建明细列表值后，注销并重新登录到实例以使创建生效。

>[!NOTE]
>
>在[此页面](../../v8/config/ui-settings.md#enumerations)中了解有关枚举的更多信息。

在下一步中，了解如何[创建和发布事务性消息传递模板](transactional-template.md)。
