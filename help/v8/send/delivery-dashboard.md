---
title: 在Campaign UI中监控投放
description: 了解如何访问投放列表，并使用投放仪表板监控您的投放
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 3%

---

# 在Campaign UI中监控投放 {#delivery-dashboard}

监测投放对于确保营销活动有效并接触到客户至关重要。 Adobe Campaign提供了一些工具，用于访问投放并通过投放列表和投放仪表板监控其性能。

## 访问投放列表 {#list-of-deliveries}

您可以通过树的&#x200B;**[!UICONTROL Campaign Management > Deliveries]**&#x200B;节点，从投放列表访问投放。

![](assets/deliveries-list.png)

默认情况下，投放列表包含在所选节点中创建的投放的名称和状态。 它还显示成功发送、处理和发送的消息数。

* **[!UICONTROL Messages to send]**&#x200B;的数量对应于分析后和投放前定向的收件人数量。
* **[!UICONTROL Success]**&#x200B;列中的邮件数与服务器发送和收件人接收的邮件数相对应。
* **[!UICONTROL Processed]**&#x200B;条消息的数量对应于已接收的消息数加上有错误的消息数。

>[!NOTE]
>
>对于大型投放，您可能希望更新这些值。 要实现此目的，请选择相关投放，然后右键单击它。 选择&#x200B;**[!UICONTROL Action > Recompute delivery and tracking indicators...]**，然后使用该助理更新此信息。

## 投放仪表板概述 {#delivery-dashboard-overview}

**投放仪表板**&#x200B;是监测您的投放以及在发送消息期间遇到的最终问题的关键。

利用该功能，可检索投放信息并在必要时对其进行编辑。 请注意，一旦发送投放，选项卡内容可能无法再更改。

您可以使用功能板中的几个选项卡监控以下信息：

* [投放摘要](#delivery-summary)
* [投放报告](#delivery-reports)
* [投放日志、镜像页面、排除项](#delivery-logs-and-history)
* [投放跟踪日志和历史记录](#tracking-logs)
* [投放呈现](#delivery-rendering)
* [投放审核](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**相关主题：**

* [了解投放失败](delivery-failures.md)
* [隔离管理](quarantines.md)
* [投放最佳实践](../start/delivery-best-practices.md)
* [管理可投放性](about-deliverability.md)

## 投放摘要 {#delivery-summary}

**[!UICONTROL Summary]**&#x200B;选项卡包含投放的特征：投放状态、使用的渠道、有关发件人的信息、主题、有关执行的信息。

## 投放报告 {#delivery-reports}

可从&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡访问的&#x200B;**[!UICONTROL Summary]**&#x200B;链接允许您查看与投放操作相关的一组报告：常规投放报告、详细报告、投放报告、失败消息的分发、打开率、点击数和交易数等。

可以根据您的要求配置此选项卡的内容。 有关投放报告的详细信息，请参阅[此章节](../reporting/delivery-reports.md)。

![](assets/delivery-report.png)

## 投放日志、历史记录和排除项 {#delivery-logs-and-history}

**[!UICONTROL Delivery]**&#x200B;选项卡提供了此投放中发生的历史记录。 它包含投放日志，即已发送消息的列表及其状态和相关消息。

对于投放，您可以仅显示（例如）投放失败或地址被隔离的收件人。 为此，请单击&#x200B;**[!UICONTROL Filters]**&#x200B;按钮并选择&#x200B;**[!UICONTROL By state]**。 然后在下拉列表中选择状态。 [投放状态页面](delivery-statuses.md)中列出了各种状态。

>[!NOTE]
>
>显示投放日志的列表可与Campaign中的任何列表一样进行自定义。 例如，您可以添加一列来了解在投放中发送了每封电子邮件的IP地址。 有关配置列表显示的详细信息，请参阅[此章节](../config/ui-settings.md#customize-lists)。

![](assets/s_ncs_user_delivery_delivery_tab.png)

**[!UICONTROL Display the mirror page for this message...]**&#x200B;链接允许您在新窗口中查看从列表中选择的投放内容的镜像页面。

镜像页面仅适用于已为其定义HTML内容的投放。 有关详细信息，请参阅[指向镜像页面的链接](mirror-page.md)。

![](assets/s_ncs_user_wizard_miror_page_link.png)

## 投放跟踪日志和历史记录 {#tracking-logs}

**[!UICONTROL Tracking]**&#x200B;选项卡列出了此投放的跟踪历史记录。 此选项卡显示已发送消息的跟踪数据，即所有受Adobe Campaign跟踪的URL。 跟踪数据每小时更新一次。

>[!NOTE]
>
>如果未为投放启用跟踪，则不会显示此选项卡。

跟踪配置在投放助理的相应阶段执行。 请参阅[如何配置跟踪的链接](tracking.md)。

**[!UICONTROL Tracking]**&#x200B;数据在投放报告中被解释。 请参阅[此小节](../reporting/delivery-reports.md)。

![](assets/s_ncs_user_delivery_tracking_tab.png)

## 收件箱呈现 {#delivery-rendering}

**[!UICONTROL Inbox rendering]**&#x200B;选项卡允许您在可能接收消息的不同上下文中预览该消息，并检查主要桌面和应用程序中的兼容性。

这样，您就可以确保以最佳方式在各种Web客户端、Web邮件和设备上向收件人显示您的消息。

有关收件箱渲染的详细信息，请参阅[此页面](inbox-rendering.md)


## 投放审核 {#delivery-audit-}

**[!UICONTROL Audit]**&#x200B;选项卡包含投放日志和涉及校样的所有消息。

使用&#x200B;**[!UICONTROL Refresh]**&#x200B;按钮可更新数据。 使用&#x200B;**[!UICONTROL Filters]**&#x200B;按钮定义数据过滤器。

使用特殊图标可以识别错误或警告。 请参阅[投放分析](delivery-analysis.md)。

**[!UICONTROL Proofs]**&#x200B;子选项卡允许您查看已发送的校样列表。

![](assets/s_ncs_user_delivery_log_tab.png)

通过选择要显示的列，您可以修改此窗口中显示的信息（以及&#x200B;**[!UICONTROL Delivery]**&#x200B;和&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡的信息）。 为此，请单击位于右下角的&#x200B;**[!UICONTROL Configure list]**&#x200B;图标。 有关配置列表显示的详细信息，请参阅[此章节](../config/ui-settings.md#customize-lists)。

## 投放仪表板同步 {#delivery-dashboard-synchronization}

在投放仪表板中，检查已处理的消息和投放日志，确保投放已成功发送。

某些指标或状态可能不正确或不是最新的，此问题可通过以下解决方案解决：

* 如果您的投放状态不正确，请检查是否已为此投放完成所有必要的批准，或者&#x200B;**[!UICONTROL operationMgt]**&#x200B;和&#x200B;**[!UICONTROL deliveryMgt]**&#x200B;技术工作流是否正在运行，且没有错误。

* 如果投放计数器与您的投放不匹配，请尝试重新计算指示器，方法是在Adobe Campaign资源管理器中右键单击相关投放，然后选择&#x200B;**[!UICONTROL Actions]** > **[!UICONTROL Recompute delivery and tracking indicators]**&#x200B;以重新同步。 有关跟踪指示器的详细信息，请参阅此[部分](../reporting/delivery-reports.md#tracking-indicators)。

您还可以通过投放仪表板使用不同的报告跟踪您的投放。 有关更多信息，请参阅此[&#128279;](../reporting/delivery-reports.md)章节。

>[!NOTE]
>
>作为Campaign v8托管云服务用户，基础架构由Adobe进行监控和管理。 如果您遇到投放指示器或功能板同步的长期问题，请联系Adobe客户关怀团队。

## 对缓慢投放进行故障排除 {#troubleshooting-slow-deliveries}

如果单击&#x200B;**[!UICONTROL Send]**&#x200B;按钮后投放时间似乎比平时长，请检查以下可能原因：

### IP地址信誉问题

某些电子邮件提供商可能已将您的IP地址添加到阻止列表。 在&#x200B;**[!UICONTROL Delivery]**&#x200B;选项卡中查看您的投放日志(broadlog)，查看指示信誉问题的退回消息。 有关信誉管理的指导，请参阅[可投放性监控](monitoring-deliverability.md)部分。

### 投放规模和复杂性

您的投放可能太大，无法快速处理。 这可能与以下情况有关：

繁重的JavaScript个性化，要求为每个收件人处理大量数据。

由于大量HTML内容、嵌入的图像或广泛的个性化设置，投放重量超过60 KB。

请参阅[投放最佳实践](../start/delivery-best-practices.md)，了解有关内容准则和个性化最佳实践的信息。 为获得最佳性能，建议的最大大小约为35KB。

### 系统性能

系统问题可能会妨碍服务器高效地处理投放。 如果您怀疑存在性能问题，请检查投放日志以了解超时错误或通信问题。

>[!NOTE]
>
>作为Campaign v8托管云服务用户，服务器基础架构监控由Adobe管理。 如果您在投放发送时遇到永久性性能问题，请联系Adobe客户关怀团队，并提供您的投放日志。

