---
product: campaign
title: 开始工作流
description: 了解如何启动工作流并发现工作流操作工具栏和右键单击菜单
feature: Workflows
exl-id: 6d9789e3-d721-4ffd-b3fb-a0c522ab1c0a
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 1%

---

# 开始工作流 {#starting-a-workflow}

工作流始终手动启动。 但是，启动时，它可以保持不活动状态，具体取决于通过调度程序指定的信息(请参阅 [调度程序](scheduler.md))或活动计划。

与定位工作流执行（启动、停止、暂停等）相关的操作 are **异步** 流程：订单将被记录，并在服务器可用以应用时生效。

利用工具栏，可启动和跟踪工作流的执行情况。

中可用的选项列表 **[!UICONTROL Actions]** 菜单和右键单击菜单的详细信息。

>[!IMPORTANT]
>
>请记住，当操作员对工作流执行操作（开始、停止、暂停等）时，该操作不会立即执行，而是被置于队列中，以便工作流模块进行处理。

## “操作”工具栏 {#actions-toolbar}

此中详细介绍了工具栏按钮。 的 **[!UICONTROL Actions]** 按钮，您可以访问用于对选定工作流执行操作的其他执行选项。 您还可以使用 **[!UICONTROL File > Actions]** ，或右键单击某个工作流并选择 **[!UICONTROL Actions]**.

![](assets/purge_historique.png)

* **[!UICONTROL Start]**

   此操作允许您开始执行工作流：工作流 **已完成**, **正在编辑** 或 **已暂停** 更改状态 **开始**. 然后，工作流引擎将处理此工作流的执行。 如果暂停了工作流，则会恢复该工作流，否则将从开始启动工作流，并激活初始活动。

   启动是一个异步过程：工作流服务器会尽快保存并处理该请求。

* **[!UICONTROL Pause]**

   此操作会将工作流的状态设置为 **已暂停**. 在恢复工作流之前，不会激活任何活动；但是，不会暂停正在进行的操作。

* **[!UICONTROL Stop]**

   此操作会停止当前正在执行的工作流。 实例的状态设置为 **已完成**. 如果可能，将停止正在进行的操作。 导入和SQL查询将立即取消。

   >[!IMPORTANT]
   >
   >停止工作流是一个异步过程：注册请求，然后工作流服务器或服务器取消正在进行的操作。 因此，停止工作流实例可能需要时间，尤其是当工作流在多个服务器上运行时，每个服务器都必须控制以取消正在进行的任务。 要避免出现任何问题，请等待停止操作完成，并且不要在同一工作流中执行多个停止请求。

* **[!UICONTROL Restart]**

   此操作停止，然后重新启动工作流。 在大多数情况下，可以更快地重新启动。 在停止需要一定时间时自动重新启动也非常有用：这是因为在工作流停止时“停止”命令不可用。

   此 ** .

* **[!UICONTROL Purge history]**

   此操作允许您清除工作流历史记录。 有关更多信息，请参阅 [清除日志](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Start in simulation mode]**

   此选项允许您在模拟模式下启动工作流，而不是在实际模式下启动。 这意味着在启用此模式时，只会执行不影响数据库或文件系统的活动(例如， **[!UICONTROL Query]**, **[!UICONTROL Union]**, **[!UICONTROL Intersection]**&#x200B;等)。 具有影响的活动(例如 **[!UICONTROL Export]**, **[!UICONTROL Import]**&#x200B;等) 以及之后（在同一分支中）的URL不会执行。

* **[!UICONTROL Execute pending tasks now]**

   此操作允许您尽快启动所有待定任务。 要启动特定任务，请右键单击其活动并选择 **[!UICONTROL Execute pending task(s) now]**.

* **[!UICONTROL Unconditional stop]**

   此选项会将工作流状态更改为 **[!UICONTROL Finished]**. 仅当正常停止过程在几分钟后失败时，此操作才应用为最后手段。 仅当您确定没有实际的工作流作业正在进行时，才使用无条件停止。

   >[!CAUTION]
   >
   >此选项专家用户可使用。

* **[!UICONTROL Save as template]**

   此操作将基于所选工作流创建新的工作流模板。 您需要指定保存该文件夹的文件夹(位于 **[!UICONTROL Folder]** 字段。

   此 ** .

## 右键单击菜单 {#right-click-menu}

选择一个或多个工作流活动后，您可以右键单击以根据您的选择执行操作。

![](assets/contextual_menu.png)

右键单击菜单中提供了以下选项：

**[!UICONTROL Open]**:利用此选项，可访问活动属性。

**[!UICONTROL Display logs:]** 此选项允许您查看所选活动的任务执行日志。 请参阅 [显示日志](monitor-workflow-execution.md#displaying-logs).

**[!UICONTROL Execute pending task(s) now:]** 此操作允许您尽快启动待决任务。

**[!UICONTROL Workflow restart from a task:]** 利用此选项，可使用之前为此活动存储的结果重新启动工作流。

**[!UICONTROL Cut/Copy/Paste/Delete:]** 利用这些选项，可剪切、复制、粘贴和删除活动。

**[!UICONTROL Copy as bitmap:]** 利用此选项，可拍摄所有活动的屏幕截图。

**[!UICONTROL Normal execution / Enable but do not execute / Do not enable:]** 这些选项也可在 **[!UICONTROL Advanced]** 选项卡。 详见 [执行](advanced-parameters.md#execution).

**[!UICONTROL Save / Cancel:]** 允许您保存或取消对工作流所做的更改。

>[!NOTE]
>
>您可以选择一组活动，并将其中一个命令应用到这些活动。

右键单击菜单的详情也请参见。
