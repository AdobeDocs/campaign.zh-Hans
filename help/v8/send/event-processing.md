---
title: 收集和处理事件
description: 了解Campaign事务型消息如何收集和处理事件
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---


# 事件处理 {#event-processing}

在事务型消息传递的上下文中，事件由外部信息系统生成，并通过 **[!UICONTROL PushEvent]** 和 **[!UICONTROL PushEvents]** 方法。 这些方法在 [此部分](event-description.md).

此事件包含链接到事件的数据，例如：

* it [type](transactional.md#create-event-types):订单确认、在网站上创建帐户等，
* 电子邮件地址或电话号码，
* 要在投放之前扩充和个性化事务型消息的任何其他信息：客户联系信息、消息语言、电子邮件格式等。

事件数据示例：

![](assets/mc-event-request.png)

要处理事务型消息传递事件，请对执行实例应用以下步骤：

1. [事件集合](#event-collection)
1. [事件传输到消息模板](#routing-towards-a-template)
1. 使用个性化数据扩充事件
1. [投放执行](delivery-execution.md)
1. [事件的回收](#event-recycling) 链接投放失败(通过Adobe Campaign工作流)

完成所有步骤后，每个目标收件人都会收到个性化消息。

## 收集事件 {#event-collection}

可以使用两种模式收集由信息系统生成的事件：

* 通过调用SOAP方法，您可以在Adobe Campaign中推送事件：pushEvent方法允许您一次发送一个事件，而pushEvents方法允许您一次发送多个事件。 [了解详情](event-description.md)。

* 通过创建工作流，您可以通过导入文件或通过SQL网关(使用 [联合数据访问](../connect/fda.md) 模块。

收集事件后，会按照执行实例的实时队列和批处理队列之间的技术工作流对事件进行划分，同时等待链接到 [消息模板](transactional-template.md).

![](assets/mc-event-queues.png)

>[!NOTE]
>
>在执行实例中， **[!UICONTROL Real time events]** 或 **[!UICONTROL Batch events]** 文件夹不能设置为视图，因为这可能会导致访问权限问题。 有关将文件夹设置为视图的更多信息，请参阅 [此部分](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## 将事件传输到模板 {#event-to-template}

在执行实例上发布消息模板后，将自动生成两个模板：一个要链接到实时事件，另一个要链接到批处理事件。

路由步骤包括：将事件关联到相应的消息模板；

* 在事件本身的属性中指定的事件类型：

   ![](assets/event-type-sample.png)

* 在消息模板属性中指定的事件类型：

   ![](assets/event-type-select.png)

默认情况下，路由取决于以下信息：

* 事件类型
* 要使用的渠道(默认情况下：email)
* 基于发布日期的最近投放模板

## 检查事件状态 {#event-statuses}

在 **事件历史记录** 文件夹或资源管理器。 它们可以按事件类型或按 **状态**.

可能的状态包括：

* **待定**

   * 待定事件可以是刚刚收集且尚未处理的事件。 的 **[!UICONTROL Number of errors]** 列显示值0。 电子邮件模板尚未关联。
   * 待定事件也可以是已处理的事件，但其确认错误。 的 **[!UICONTROL Number of errors]** 列显示的值不为0。 要了解此事件何时将再次处理，请查阅 **[!UICONTROL Process requested on]** 列。

* **待定投放**
已处理事件并关联投放模板。 电子邮件处于待投放状态，且已应用经典投放流程。 有关更多信息，您可以打开投放。
* **已发送**, **已忽略** 和 **投放错误**
这些投放状态可通过 
**updateEventsStatus** 工作流。 有关更多信息，您可以打开相关投放。
* **未涵盖的事件**
事务型消息传递路由阶段失败。 例如，Adobe Campaign未找到充当事件模板的电子邮件。
* **事件过期**
已达到最大发送尝试次数。 该事件被视为null。

## 回收事件 {#event-recycling}

如果在特定渠道上投放消息失败，Adobe Campaign可以使用其他渠道重新发送消息。 例如，如果短信渠道上的投放失败，则会使用电子邮件渠道重新发送消息。

为此，您需要配置一个工作流，该工作流使用 **投放错误** 状态，并为其分配不同的渠道。

>[!CAUTION]
>
>此步骤只能使用工作流执行，因此保留给专家用户。 有关更多信息，请联系您的Adobe客户经理。



