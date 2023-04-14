---
title: 事务型消息投放执行
description: 了解有关事务型消息投放执行和监控的更多信息
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 1%

---


# 投放执行 {#delivery-execution}

扩充完成并将投放模板链接到事件后，将从执行实例发送投放。

>[!NOTE]
>
>事务型消息比任何其他投放具有优先级。

所有投放都分组在 **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** 文件夹。

默认情况下，这些文件夹会按提交月分类为子文件夹。 可以在消息模板属性中更改此排序。

## 事务型消息监控 {#transactional-message-monitoring}

要监视事务型消息，请检查 [投放日志](send.md).

从执行实例发送的事务性投放通过技术工作流(**[!UICONTROL Message Center execution instance]**)每小时运行一次。

>[!NOTE]
>
>投放每周会根据最新事件更新而不是事件创建日期来累计事件。 因此，在从控制实例提取事务性消息传递投放日志时，与每个投放日志ID关联的投放ID可能会随着日志更新而随时间而改变（例如，当收到事件的入站退件时）。

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
