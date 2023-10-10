---
product: campaign
title: AND-连接
description: AND-连接
feature: Workflows
role: User
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 21%

---

# AND-连接{#and-join}



只有激活所有集客过渡时，即之前的所有活动都已完成时，联接才会触发其叫客过渡。 这使您可以在继续执行工作流之前确保某些活动已完成。

例如，您可以在内容创建和投放发送自动化的上下文中使用AND-join活动，以确保仅在完成目标查询和内容更新步骤后开始投放。 中提供了专用用例

![](assets/and-join-usage.png)

>[!NOTE]
>
>请注意，使用不同定向维度配置的集客过渡不能使用 **[!UICONTROL AND-join]** 活动。

活动的叫客已发送群体是通过在活动的集客过渡中选择主集来确定的。

叫客过渡只能包含集客过渡群体之一。如果未配置活动，则叫客过渡将随机选择一个集客群体。

>[!CAUTION]
>
>在 **AND — 连接** 类型活动时，将合并事件变量，但是如果同一变量定义了两次，则会发生冲突，并且值保持不变。 如需详细信息，请参阅[此部分](javascript-scripts-and-templates.md#event-variables)。
