---
product: campaign
title: 循环投放
description: 了解有关定期投放工作流活动的更多信息
feature: Workflows
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 15%

---

# 循环投放{#recurring-delivery}



A **[!UICONTROL Recurring delivery]** 活动，可配置特定于营销策划的投放模板实例。

![](assets/do-not-localize/how-to-video.png) [在视频中发现此功能](#recurring-delivery-video)

此活动仅在 **[!UICONTROL Targeting and workflows]** 选项卡。

操作步骤：

1. 选择活动所基于的投放模板。

   ![](assets/recurring_delivery_001.png)

1. 配置投放模板。

就可用选项而言，此活动的配置过程与创建投放模板的过程类似。

有关此活动的示例，请参阅此 [部分](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## 如何设置循环投放

A **循环投放** 将在每次执行时创建一个新投放实例。 例如，如果工作流计划每周运行一次，那么一年后将产生 52 次投放。这也意味着广泛的日志和跟踪日志将由每个投放实例分隔。

![循环投放](assets/delivery_recurring.jpg)

如果要停止定期投放运行，应完全取消营销活动或停止执行该活动的工作流。 从Campaign仪表板停止投放将只停止投放发生：每次执行工作流时，将继续创建循环投放的下一个实例。

>[!NOTE]
>
>无法从 **[!UICONTROL Recurring delivery]** 键入活动。
> 
>要通过营销活动工作流直接创建投放，请使用预先配置的渠道特定活动(例如， **[!UICONTROL Email delivery]**)。

## 教程视频(#recurring-delivery-video)

此视频介绍如何配置定期投放和调度程序活动。

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

提供了其他Campaign Classic操作方法视频 [此处](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=zh-Hans).
