---
product: campaign
title: 管理时区
description: 管理时区
feature: Workflows
exl-id: 04b7638d-55dd-4317-b605-5d618ef014ba
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 4%

---

# 管理时区{#managing-time-zones}

Adobe Campaign允许您管理同一实例所涉及的不同国家/地区之间的时间差。 在实例创建期间配置应用的配置。

在工作流中，您可以调整活动执行计划，并将特定时区链接到活动或整个工作流。 在导入文件时或在投放计划框架内，此配置非常有用。

## 执行计划 {#execution-scheduling}

您可以使用调度程序计划任务的执行(请参阅 [调度程序](scheduler.md))。 您还可以使用提供此功能的活动中提供的计划选项。 这些活动提供 **[!UICONTROL Schedule]** 选项卡： **[!UICONTROL File collector]**, **[!UICONTROL File transfer]**, **[!UICONTROL Web download]**, **[!UICONTROL Email reception]** &amp; **[!UICONTROL SMS]**&#x200B;等。

对于所有计划任务（即具有计划选项的所有活动），您可以选择要应用的时区。 通过 **[!UICONTROL Advanced]** 选项卡：

![](assets/wf-timezone-in-a-box.png)

可能的值包括：

* 服务器时区

   使用Adobe Campaign应用程序服务器的时区。

* 用户时区

   使用执行工作流的Adobe Campaign运算符的时区。

* 数据库时区

   使用所用数据库服务器的时区。

* 特定时区

   使用选定的时区。

如果 **[!UICONTROL By default]** 值时，将应用工作流的时区，或应用服务器的时区。

## 将时区链接到活动 {#linking-a-time-zone-to-an-activity}

的 **[!UICONTROL Advanced]** 使用工作流活动的选项卡，可以选择其时区。 尽管在大多数情况下，工作流的时区已足够，但是可能需要针对特定活动（如数据导入）一次又一次地使其过载，以便将日期链接到其正确时区。
