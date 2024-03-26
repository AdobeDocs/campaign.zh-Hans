---
product: campaign
title: 向列表发送报告
description: 了解如何使用工作流将报告发送到列表
feature: Workflows
exl-id: 5bc576d0-cab7-4d26-a3a5-91982a00e356
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 3%

---

# 向列表发送报告{#send-a-report-to-a-list}

此用例详细说明了如何生成每月开箱即用的报表 **[!UICONTROL Tracking indicators]** PDF格式的报告以及如何将其发送给收件人列表。

![](assets/use_case_report_intro.png)

此用例的主要实施步骤包括：

* 为此报告创建收件人列表。 [了解详情](#step-1--create-the-recipient-list)。
* 创建一个投放模板，每次执行工作流时都会创建一个新投放。 [了解详情](#step-2--create-the-delivery-template)。
* 创建一个工作流，以生成PDF格式的报告，并将其发送到收件人列表。 [了解详情](#step-3--create-the-workflow))。

## 步骤1：创建收件人列表 {#step-1--create-the-recipient-list}

要创建目标收件人列表，请执行以下步骤：

1. 浏览至 **[!UICONTROL Profiles and targets]** 选项卡，单击 **[!UICONTROL Lists]** 链接。
1. 单击 **[!UICONTROL Create]** 按钮。
1. 选择 **[!UICONTROL New list]** 并为要发送到的报告创建新的收件人列表。

有关创建列表的详细信息，请参阅 [本节](../../v8/audiences/create-audiences.md).

## 第2步：创建投放模板 {#step-2--create-the-delivery-template}

要创建投放模板，请执行以下步骤：

1. 浏览至 **[!UICONTROL Resources > Templates > Delivery templates]** Adobe Campaign节点并复制 **[!UICONTROL Email delivery]** 内置模板。

   有关创建投放模板的更多信息，请参阅 [本节](../../v8/send/create-templates.md).

1. 输入模板参数：标签、目标（以前创建的收件人列表）、主题和内容。

   每次执行工作流时， **[!UICONTROL Tracking indicators]** 报告已更新，如中所述 [第3步：创建工作流](#step-3--creating-the-workflow))。

1. 要在投放中包含最新版本的报表，您需要添加 **[!UICONTROL Calculated attachment]**：

   * 单击 **[!UICONTROL Attachments]** 链接，然后单击 **[!UICONTROL Add]** 按钮。 选择 **[!UICONTROL Calculated attachment...]**。

     ![](assets/use_case_report_4.png)

   * 在 **[!UICONTROL Type]** 从下拉列表中，选择最新的选项： **[!UICONTROL File name is computed during delivery of each message (it may then depend on the recipient profile)]**.

     ![](assets/use_case_report_5.png)

     在中输入的值 **[!UICONTROL Label]** 字段不会显示在最终投放中。

   * 在文本区域中，输入文件的访问路径和名称。

     ![](assets/use_case_report_6.png)

     >[!CAUTION]
     >
     >路径和名称必须与 **[!UICONTROL JavaScript code]** 键入工作流的活动，如中所述 [第3步：创建工作流](#step-3--creating-the-workflow).

   * 选择 **[!UICONTROL Advanced]** 制表符和勾选 **[!UICONTROL Script the name of the file name displayed in the mails sent]**. 在文本区域中，在最终投放中输入附件的名称。

     ![](assets/use_case_report_6b.png)

## 第3步：创建工作流 {#step-3--creating-the-workflow}

为此用例创建以下工作流。

![](assets/use_case_report_8.png)

它使用三个活动：

* A **[!UICONTROL Scheduler]** 每月执行一次工作流的活动，
* A **[!UICONTROL JavaScript code]** 活动生成PDF格式的报告，
* A **[!UICONTROL Delivery]** 活动，引用之前创建的投放模板。

要构建此工作流，请执行以下步骤：

1. 浏览至 **[!UICONTROL Administration > Production > Technical workflows]** 节点，并创建新文件夹以存储工作流。
1. 创建新工作流。

   ![](assets/use_case_report_7.png)

1. 首先添加 **[!UICONTROL Scheduler]** 键入并配置活动，以便工作流在每月第一个星期一执行。

   ![](assets/use_case_report_9.png)

   有关配置调度程序的详细信息，请参阅 [计划程序](scheduler.md).

1. 然后添加 **[!UICONTROL JavaScript code]** 键入activity。

   ![](assets/use_case_report_10.png)

   在编辑区域中输入以下代码：

   ```sql
   var reportName = "indicators";
   var path = "/tmp/indicators.pdf";
   var exportFormat = "PDF";
   var reportURL = "<PUT THE URL OF THE REPORT HERE>";
   var _ctx = <ctx _context="global" _reportContext="deliveryFeedback" />
   var isAdhoc = 0;
   
   xtk.report.export(reportName, _ctx, exportFormat, path, isAdhoc);
   ```


   变量一起使用：

   * **var reportName**：用双引号输入报表的内部名称。 在本例中，的 **跟踪指示器** 报告为“deliveryFeedback”。
   * **变量路径**：输入文件的保存路径(“tmp”)、要为文件指定的名称(“deliveryFeedback”)以及文件扩展名(“.pdf”)。 在本例中，我们使用内部名称作为文件名。 值需要位于双引号之间并以“+”字符分隔。

     >[!CAUTION]
     >
     >文件必须保存在服务器上。 您必须输入与中相同的路径和名称 **[!UICONTROL General]** 已计算附件的“编辑”窗口的选项卡（详见） [此处](#step-2--create-the-delivery-template))。

   * **var exportFormat**：输入文件的导出格式(“PDF”)。
   * **var _ctx** （上下文）：在本例中，我们使用 **[!UICONTROL Tracking indicators]** 在其全局上下文中报告。

1. 通过添加 **[!UICONTROL Delivery]** 活动：

   ![](assets/use_case_report_11.png)

   * **[!UICONTROL Delivery]**：选择 **[!UICONTROL New, created from a template]**，然后选择之前创建的投放模板。
   * 对于 **[!UICONTROL Recipients]** 和 **[!UICONTROL Content]** 字段，选择 **[!UICONTROL Specified in the delivery]**.
   * **[!UICONTROL Action to perform]**：选择 **[!UICONTROL Prepare and start]**.
   * 取消选中 **[!UICONTROL Generate an outbound transition]** 和 **[!UICONTROL Process errors]** 选项。

1. 保存更改并启动工作流。 该消息将于当月第一个星期一发送到收件人列表，并随附报告。
