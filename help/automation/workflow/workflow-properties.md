---
product: campaign
title: 工作流属性
description: 了解有关Campaign工作流属性的更多信息
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 39%

---

# 工作流属性{#workflow-properties}



## “执行”选项卡 {#execution-tab}

此 **[!UICONTROL Execution]** 的选项卡 **[!UICONTROL Properties]** 工作流中的窗口分为3个部分：

![](assets/wf_execution_tab.png)

### 调度程序 {#scheduler}

此部分仅显示在营销活动工作流中。

* **[!UICONTROL Priority]**

   工作流引擎根据此字段中定义的优先级条件处理要执行的工作流。 例如，所有具有 **[!UICONTROL Average]** 优先级将先于具有 **[!UICONTROL Low]** 优先级。

* **[!UICONTROL Schedule execution for a time of low activity]**

   此选项会将工作流启动延迟到一个不太繁忙的时间段。 某些工作流在数据库引擎的资源方面成本高昂。 我们建议将执行安排在活动较少的时间执行（例如，在晚上）。 在中定义低活动时段 **[!UICONTROL Processes on campaigns]** 技术工作流。

### 执行 {#execution}

* **[!UICONTROL Default affinity]**

   如果您的安装包括多个工作流服务器，请使用此字段选择将要执行工作流的计算机。如果此字段中定义的值在任何服务器上都不存在，则工作流将保持待处理状态。

* **[!UICONTROL History in days]**

   数据库的工作表保存执行项目的历史记录（任务、事件、日志）。 您可以在此处定义此工作流的存档天数：清理过程将每天删除一次最旧的存档。如果此字段中的值为零，则绝不会删除存档。

* **[!UICONTROL Log SQL queries in the journal]**

   此功能是为高级用户保留的。它涉及包含定位活动（查询、并集、交集等）的工作流。选中此选项后，在工作流执行期间发送到数据库的 SQL 查询将显示在 Adobe Campaign 中：这意味着您可以分析它们以优化查询或诊断问题。

   查询会显示在 **[!UICONTROL SQL logs]** 选项卡，添加到工作流（营销活动工作流除外）和 **[!UICONTROL Properties]** 活动。 此 **[!UICONTROL Audit]** 选项卡还包括SQL查询。

   ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL Execute in the engine]**

   此选项只能用于调试，不能用于生产。 启用后，该工作流将具有优先权，并且所有其他工作流将停止，直到此工作流完成。

### 错误管理 {#error-management}

* **[!UICONTROL Troubleshooting]**

   此字段可让您定义在工作流任务出错时要执行的操作。提供了两个可能的选项：

   * **[!UICONTROL Stop the process]**：工作流自动暂停。 工作流状态更改为 **[!UICONTROL Failed]**. 问题解决后，请使用重新启动工作流 **[!UICONTROL Start]** 或 **[!UICONTROL Restart]** 按钮。
   * **[!UICONTROL Ignore]**：触发错误的任务的状态更改为 **[!UICONTROL Failed]**，但工作流会保留 **[!UICONTROL Started]** 状态。 此配置与定期任务相关：如果分支包含调度程序，它将在下次执行工作流时正常启动。

* **[!UICONTROL Consecutive errors]**

   在以下情况下，此字段将变为可用： **[!UICONTROL Ignore]** 值在 **[!UICONTROL In case of errors]** 字段。 您可以指定在流程停止前可忽略的错误的数量。一旦达到此数量，工作流状态将更改为 **[!UICONTROL Failed]**. 如果此字段的值为 0，则无论错误数量是多少，工作流都绝不会停止。

* **[!UICONTROL Template]**

   此字段允许您选择通知模板，当其状态更改为时，将其发送给工作流主管 **[!UICONTROL Failed]**.

   如果相关操作员的配置文件中包含电子邮件地址，则会通过电子邮件通知他们。 要定义工作流主管，请转到 **[!UICONTROL Supervisor(s)]** 属性字段(**[!UICONTROL General]** 选项卡)。

   ![](assets/wf-properties_select-supervisors.png)

   此 **[!UICONTROL Notification to a workflow supervisor]** 默认模板包含一个链接，用于通过Web访问Adobe Campaign客户端控制台，以便收件人可以在登录后处理问题。

   要创建个性化模板，请转到 **[!UICONTROL Administration>Campaign management>Technical deliveries and templates]**.
