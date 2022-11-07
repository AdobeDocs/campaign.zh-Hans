---
product: campaign
title: 向列表发送报告
description: 了解如何使用工作流将报表发送到列表
feature: Workflows
source-git-commit: 4c3caa8e31c2076d32a03a8778a28edce50cde63
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 3%

---


# 向列表发送报告{#send-a-report-to-a-list}

此用例详细说明了如何生成每月即装即用 **[!UICONTROL Tracking indicators]** 报表格式，以及如何将其发送到收件人列表。

![](assets/use_case_report_intro.png)

此用例的主要实施步骤是：

* 为此报表创建收件人列表。 [了解详情](#step-1--create-the-recipient-list)。
* 创建投放模板，每次执行工作流时都会创建新投放。 [了解详情](#step-2--create-the-delivery-template)。
* 创建一个工作流，以PDF格式生成报表并将其发送到收件人列表。 [了解详情](#step-3--create-the-workflow)).

## 步骤1:创建收件人列表 {#step-1--create-the-recipient-list}

要创建目标收件人列表，请执行以下步骤：

1. 浏览到 **[!UICONTROL Profiles and targets]** ，单击 **[!UICONTROL Lists]** 链接。
1. 单击 **[!UICONTROL Create]** 按钮。
1. 选择 **[!UICONTROL New list]** 并为要发送到的报表创建新收件人列表。

有关创建列表的更多信息，请参阅 [此部分](../../v8/audiences/create-audiences.md).

## 步骤2:创建投放模板 {#step-2--create-the-delivery-template}

要创建投放模板，请执行以下步骤：

1. 浏览到 **[!UICONTROL Resources > Templates > Delivery templates]** 节点，并复制 **[!UICONTROL Email delivery]** 内置模板。

   有关创建投放模板的更多信息，请参阅 [此部分](../../v8/send/create-templates.md).

1. 输入模板参数：标签、目标（之前创建的收件人列表）、主题和内容。

   每次执行工作流时， **[!UICONTROL Tracking indicators]** 报表已更新，如 [步骤3:创建工作流](#step-3--creating-the-workflow))。

1. 要在投放中包含最新版本的报表，您需要添加 **[!UICONTROL Calculated attachment]**:

   * 单击 **[!UICONTROL Attachments]** 链接，然后单击 **[!UICONTROL Add]** 按钮。 选择 **[!UICONTROL Calculated attachment...]**。

      ![](assets/use_case_report_4.png)

   * 在 **[!UICONTROL Type]** 下拉列表中，选择最新选项： **[!UICONTROL File name is computed during delivery of each message (it may then depend on the recipient profile)]**.

      ![](assets/use_case_report_5.png)

      在 **[!UICONTROL Label]** 字段中，不会显示在最终投放中。

   * 在文本区域中，输入文件的访问路径和名称。

      ![](assets/use_case_report_6.png)

      >[!CAUTION]
      >
      >路径和名称必须与 **[!UICONTROL JavaScript code]** 工作流的活动类型，如 [步骤3:创建工作流](#step-3--creating-the-workflow).

   * 选择 **[!UICONTROL Advanced]** 选项卡和检查 **[!UICONTROL Script the name of the file name displayed in the mails sent]**. 在文本区域中，在最终投放中输入附件的名称。

      ![](assets/use_case_report_6b.png)

## 步骤3:创建工作流 {#step-3--creating-the-workflow}

为此用例创建以下工作流。

![](assets/use_case_report_8.png)

它使用三个活动：

* A **[!UICONTROL Scheduler]** 活动，每月执行一次工作流，
* A **[!UICONTROL JavaScript code]** 活动，以PDF格式生成报表，
* A **[!UICONTROL Delivery]** 活动，其中引用了之前创建的投放模板。

要构建此工作流，请执行以下步骤：

1. 浏览到 **[!UICONTROL Administration > Production > Technical workflows]** 节点，并创建一个新文件夹来存储您的工作流。
1. 创建新工作流。

   ![](assets/use_case_report_7.png)

1. 首先，添加 **[!UICONTROL Scheduler]** 键入活动并对其进行配置，以便工作流在当月的第一个星期一执行。

   ![](assets/use_case_report_9.png)

   有关配置调度程序的更多信息，请参阅 [调度程序](scheduler.md).

1. 然后，添加 **[!UICONTROL JavaScript code]** 键入活动。

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


   ，并使用以下变量：

   * **var reportName**:在报表的内部名称中输入双引号。 在这种情况下， **跟踪指示器** 报表为“deliveryFeedback”。
   * **var路径**:输入文件的保存路径(“tmp”)、要为文件提供的名称(“deliveryFeedback”)和文件扩展名(“.pdf”)。 在本例中，我们使用内部名称作为文件名。 值必须介于双引号之间，并由“+”字符分隔。

      >[!CAUTION]
      >
      >文件必须保存在服务器上。 必须输入与中相同的路径和相同的名称 **[!UICONTROL General]** （详细） [此处](#step-2--create-the-delivery-template))。

   * **var exportFormat**:输入文件的导出格式(“PDF”)。
   * **var_ctx** （上下文）：在本例中，我们使用 **[!UICONTROL Tracking indicators]** 报告。

1. 通过添加 **[!UICONTROL Delivery]** 活动，其中包含以下选项：

   ![](assets/use_case_report_11.png)

   * **[!UICONTROL Delivery]**:选择 **[!UICONTROL New, created from a template]**，然后选择之前创建的投放模板。
   * 对于 **[!UICONTROL Recipients]** 和 **[!UICONTROL Content]** 字段，选择 **[!UICONTROL Specified in the delivery]**.
   * **[!UICONTROL Action to perform]**:选择 **[!UICONTROL Prepare and start]**.
   * 取消选中 **[!UICONTROL Generate an outbound transition]** 和 **[!UICONTROL Process errors]** 选项。

1. 保存更改并启动工作流。 该消息会在每月的第一个星期一发送到收件人列表，并附带报表。