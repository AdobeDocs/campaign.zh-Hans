---
title: 访问跟踪日志
description: 了解如何访问和解读跟踪日志
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# 访问跟踪日志 {#accessing-the-tracking-logs}

发送投放并激活跟踪后，**[!UICONTROL Tracking]**&#x200B;技术工作流将负责检索跟踪数据。 默认情况下，每小时执行一次。

## 在收件人用户档案中查看跟踪 {#recipient-tracking}

此信息显示在投放所定向的收件人用户档案的&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡中，如以下示例所示：

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

此选项卡显示收件人跟踪和点击的所有URL，包括：

* 已单击的URL
* 单击的日期和时间
* 从中找到URL的投放
* 任何其他相关跟踪信息

您可以过滤和排序此信息，以分析收件人行为并确定参与模式。

## 在投放中查看跟踪 {#delivery-tracking}

跟踪信息也可通过投放的&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡访问。

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

在此选项卡中，您可以查看：

* **[!UICONTROL Tracking statistics]**：提供打开、点击和其他跟踪事件的概述
* **[!UICONTROL URLs and click streams]**：显示点击了哪些链接以及点击次数
* **[!UICONTROL Hot clicks]**：显示收件人点击邮件位置的可视化表示形式
* **[!UICONTROL Tracking logs]**：提供详细的个人跟踪记录

## 跟踪疑难解答 {#troubleshooting}

>[!NOTE]
>
>如果您看不到投放的&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡，则意味着尚未激活跟踪。 请参阅[此部分](tracked-links.md)以了解如何配置跟踪。

### 检查跟踪技术工作流 {#check-tracking-workflow}

必须运行跟踪技术工作流才能收集跟踪数据。 您可以在&#x200B;**[!UICONTROL Administration > Production > Technical workflows]**&#x200B;文件夹中找到“跟踪”技术工作流。

要验证工作流，请执行以下操作：

1. 打开&#x200B;**[!UICONTROL Tracking]**&#x200B;工作流
1. 检查上一个执行日期
1. 验证工作流日志中没有任何错误

如果工作流未运行或有错误，请与系统管理员联系。

## 验证跟踪数据收集

发送启用了跟踪的投放后：

1. 等待跟踪工作流执行（默认情况下，每小时）
1. 打开投放，然后转到&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡
1. 检查是否存在跟踪数据
1. 如果未显示任何数据，请检查：
   * 已在投放设置中激活跟踪
   * 跟踪技术工作流正在运行
   * 收件人已打开电子邮件并单击链接

## 相关主题 {#related-topics}

* [了解如何配置跟踪的链接](tracked-links.md)
* [了解如何测试跟踪](testing-tracking.md)
* [了解跟踪报表](../reporting/delivery-reports.md#tracking-indicators)

