---
product: campaign
title: 调度程序
description: 了解有关调度程序工作流活动的更多信息
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 8%

---

# 调度程序 {#scheduler}



**计划程序**&#x200B;是一个永久性任务，它会在计划指定的时间激活其转换。

**[!UICONTROL Scheduler]** 活动应视为排程开始的时间。图表中的活动定向规则与 **[!UICONTROL Start]** 活动相同。此活动不得包含集客过渡。

## 最佳实践 {#best-practices}

**更改计划程序时间后重新启动工作流** — 更改&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动的计划时间时，请务必重新启动工作流。 这可确保在更新的时间执行工作流。 如果不重新启动，工作流将根据旧计划继续执行。

**限制计划程序频率** — 避免计划工作流的运行频率超过每15分钟一次。 频繁地运行这些数据库会降低系统性能，并导致数据库拥塞。

**每个分支使用一个调度程序** — 工作流的每个分支应仅有一个&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动。 有关在工作流中使用活动的最佳实践的更多信息，请参阅[工作流最佳实践页面](workflow-best-practices.md#using-activities)。

**阻止工作流并发执行** — 如果工作流是由调度程序触发的，请注意该工作流的多个实例可能同时运行。 例如，如果调度程序每小时触发一次工作流，但工作流执行需要一个小时以上，则您最终可能会遇到重复执行的情况。要避免这种情况，请考虑设置检查以防止多个同时执行。 [了解如何防止同时执行多个工作流](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions)。

**解决延迟的过渡问题** — 如果工作流正在执行长时间运行的任务（如导入），或者wfserver模块已暂时停止，则计划程序触发的过渡可能会延迟。 要缓解此问题，请限制调度程序的激活时间，以确保任务在定义的时间范围内运行。

## 配置调度程序活动 {#configuring-scheduler-activity}

调度程序定义转换的激活调度。 要配置它，请双击图形对象，然后单击&#x200B;**[!UICONTROL Change...]**

![](assets/s_user_segmentation_scheduler.png)

通过向导，可定义活动的频率和有效期。 配置步骤如下：

1. 选择激活频率，然后单击&#x200B;**[!UICONTROL Next]**。

   ![](assets/s_user_segmentation_scheduler2.png)

1. 给出激活时间和日期。 此步骤的参数取决于上一步骤中选择的频率。 如果选择每天启动活动多次，则配置选项将如下所示：

   ![](assets/s_user_segmentation_scheduler3.png)

1. 定义计划的有效期，或指定执行计划的次数。

   ![](assets/s_user_segmentation_scheduler4.png)

1. 检查配置并单击&#x200B;**[!UICONTROL Finish]**&#x200B;进行保存。

   ![](assets/s_user_segmentation_scheduler5.png)
