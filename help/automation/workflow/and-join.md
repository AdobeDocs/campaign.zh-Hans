---
product: campaign
title: AND-连接
description: AND-连接
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
TQID: https://experienceleague.adobe.com/1ChXl3Rlm93ftFFaD7Z-PcoO7CwUcxRHm2JdCFzIOZs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 193
ht-degree: 22%

---

# AND-连接{#and-join}



只有激活所有集客过渡时，即之前的所有活动都已完成时，联接才会触发其叫客过渡。 这使您可以在继续执行工作流之前确保某些活动已完成。

例如，您可以在内容创建和投放发送自动化的上下文中使用AND-join活动，以确保仅在完成目标查询和内容更新步骤后开始投放。 中提供了专用用例

![](assets/and-join-usage.png)

>[!NOTE]
>
>请注意，使用不同定向维度配置的集客过渡不能使用&#x200B;**[!UICONTROL AND-join]**&#x200B;活动连接在一起。

活动的叫客已发送群体是通过在活动的集客过渡中选择主集来确定的。

叫客过渡只能包含集客过渡群体之一。 如果未配置活动，则叫客过渡将随机选择一个集客群体。

>[!CAUTION]
>
>对于&#x200B;**AND-join**&#x200B;类型的活动，将合并事件变量，但是如果同一变量定义了两次，则会发生冲突，且值仍未确定。 如需详细信息，请参阅[此小节](javascript-scripts-and-templates.md#event-variables)。
