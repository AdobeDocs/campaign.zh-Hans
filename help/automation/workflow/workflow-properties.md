---
product: campaign
title: 工作流属性
description: 進一步瞭解Campaign工作流程屬性
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 39%

---

# 工作流属性{#workflow-properties}



## 執行標籤 {#execution-tab}

此 **[!UICONTROL Execution]** 的標籤 **[!UICONTROL Properties]** 工作流程中的視窗分為3個區段：

![](assets/wf_execution_tab.png)

### 调度程序 {#scheduler}

此區段只會顯示在行銷活動工作流程中。

* **[!UICONTROL Priority]**

   工作流程引擎會根據此欄位中定義的優先順序條件，處理要執行的工作流程。 例如，所有工作流程具有 **[!UICONTROL Average]** 優先順序會先於具有 **[!UICONTROL Low]** 優先順序。

* **[!UICONTROL Schedule execution for a time of low activity]**

   此選項會將工作流程開始時間延後至較不忙碌的期間。 某些工作流程可能需要耗費大量資料庫引擎資源。 我們建議將執行排程為活動較少的時間（例如，在晚上）。 低活動期間定義於 **[!UICONTROL Processes on campaigns]** 技術工作流程。

### 执行 {#execution}

* **[!UICONTROL Default affinity]**

   如果您的安装包括多个工作流服务器，请使用此字段选择将要执行工作流的计算机。如果此字段中定义的值在任何服务器上都不存在，则工作流将保持待处理状态。

* **[!UICONTROL History in days]**

   資料庫的工作表會保留執行（任務、事件、記錄）的歷史記錄。 您可以在此处定义此工作流的存档天数：清理过程将每天删除一次最旧的存档。如果此字段中的值为零，则绝不会删除存档。

* **[!UICONTROL Log SQL queries in the journal]**

   此功能是为高级用户保留的。它涉及包含定位活动（查询、并集、交集等）的工作流。选中此选项后，在工作流执行期间发送到数据库的 SQL 查询将显示在 Adobe Campaign 中：这意味着您可以分析它们以优化查询或诊断问题。

   查詢會顯示在 **[!UICONTROL SQL logs]** 標籤，新增至工作流程（行銷活動工作流程除外）和 **[!UICONTROL Properties]** 活動。 此 **[!UICONTROL Audit]** 索引標籤也包含SQL查詢。

   ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL Execute in the engine]**

   此選項僅能用於偵錯，絕不能用於生產。 啟用時，工作流程會獲得優先順序，而所有其他工作流程會一直停止，直到此工作流程完成。

### 错误管理 {#error-management}

* **[!UICONTROL Troubleshooting]**

   此字段可让您定义在工作流任务出错时要执行的操作。提供了两个可能的选项：

   * **[!UICONTROL Stop the process]**：工作流程會自動暫停。 工作流程狀態變更為 **[!UICONTROL Failed]**. 問題解決後，請使用重新啟動工作流程 **[!UICONTROL Start]** 或 **[!UICONTROL Restart]** 按鈕。
   * **[!UICONTROL Ignore]**：觸發錯誤的工作狀態會變更為 **[!UICONTROL Failed]**，但工作流程會保留 **[!UICONTROL Started]** 狀態。 此配置与定期任务相关：如果分支包含调度程序，它将在下次执行工作流时正常启动。

* **[!UICONTROL Consecutive errors]**

   此欄位在下列情況中變得可用： **[!UICONTROL Ignore]** 值已選取於 **[!UICONTROL In case of errors]** 欄位。 您可以指定在流程停止前可忽略的错误的数量。達到此數目後，工作流程狀態會變更為 **[!UICONTROL Failed]**. 如果此字段的值为 0，则无论错误数量是多少，工作流都绝不会停止。

* **[!UICONTROL Template]**

   此欄位可讓您選取當工作流程監督員的狀態變更為時，要傳送給其工作流程監督員的通知範本 **[!UICONTROL Failed]**.

   如果相關操作員的設定檔中有電子郵件地址，則會以電子郵件通知相關操作員。 若要定義工作流程主管，請前往 **[!UICONTROL Supervisor(s)]** 屬性欄位(**[!UICONTROL General]** 標籤)。

   ![](assets/wf-properties_select-supervisors.png)

   此 **[!UICONTROL Notification to a workflow supervisor]** 預設範本包含一個連結，可透過網頁存取Adobe Campaign主控台，這樣收件者就可以在登入後處理問題。

   若要建立個人化範本，請前往 **[!UICONTROL Administration>Campaign management>Technical deliveries and templates]**.
