---
title: 投放分析
description: 了解如何准备和检查投放
feature: Personalization
role: User
level: Beginner
exl-id: 1526048d-9f02-4853-948f-8fb618670dbd
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 5%

---

# 投放分析 {#analyze-delivery}

分析是投放准备步骤。 一旦定义了目标受众，并且消息内容已准备就绪并进行了测试，就可以启动定向功能。 在投放分析期间，会计算目标群体并准备投放内容。 完成后，即可发送投放。

## 开始分析 {#start-the-analysis}

要准备投放，请确保已定义投放内容和目标，然后执行以下步骤：

1. 在投放窗口中，单击&#x200B;**[!UICONTROL Send]**&#x200B;按钮。
1. 选择&#x200B;**[!UICONTROL Deliver as soon as possible]**&#x200B;以执行受众计算，并准备立即发送的内容。 您还可以将投放推迟到以后的日期，或在不准备内容的情况下获取群体估计。

   ![](assets/delivery-analysis-start.png)

1. 单击&#x200B;**[!UICONTROL Analyze]**&#x200B;以手动启动分析。 进度条显示分析的进度。

   在投放分析期间应用一组检查规则。 这些规则是在投放属性的&#x200B;**[!UICONTROL Typology]**&#x200B;选项卡中选择的&#x200B;**类型**&#x200B;中定义的。 在[本节](../../automation/campaign-opt/campaign-typologies.md)中了解有关类型的更多信息。

   默认情况下，对于电子邮件，分析涵盖以下几点：

   * 批准对象
   * 批准URL和图像
   * 批准URL标签
   * 批准退订链接
   * 检查验证的大小
   * 检查有效期
   * 检查批次计划


1. 您可以随时通过单击&#x200B;**[!UICONTROL Stop]**&#x200B;按钮停止分析。

   在准备阶段不会发送任何消息。 这样，您就可以毫无风险地开始或取消分析。

   >[!IMPORTANT]
   >
   >运行时，分析会冻结投放（或验证）。 对投放（或证明）所做的任何更改必须在应用之前进行其他分析。

   分析完成后，窗口的上半部分将指示投放准备是否已完成或者是否发生任何错误。 这将列出所有验证步骤、警告和错误。彩色图标显示消息类型：

   * 蓝色图标表示信息性消息。
   * 黄色图标表示非关键处理错误。
   * 红色图标表示阻止发送投放的严重错误。

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;更正错误（如果有）。 进行更改后，单击&#x200B;**[!UICONTROL Analyze]**&#x200B;重新启动分析。

   >[!NOTE]
   >
   >如果要发送的邮件数与您的预期不符，请单击&#x200B;**[!UICONTROL Change the main delivery target]**&#x200B;链接。 利用此选项，可更改目标群体的定义并重新启动分析。
   >

1. 检查分析结果后，单击&#x200B;**[!UICONTROL Confirm delivery]**&#x200B;将消息发送到主目标。


## 分析设置 {#analysis-settings}

浏览到投放属性的&#x200B;**[!UICONTROL Analysis]**&#x200B;选项卡，以定义分析阶段中消息准备的设置。

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

通过此选项卡可访问以下选项：

* **[!UICONTROL Label and code of the delivery]**：此部分中的选项用于在投放分析阶段计算这些字段的值。 **[!UICONTROL Compute the execution folder during the delivery analysis]**&#x200B;字段计算分析阶段将包含此投放操作的文件夹的名称。

* **[!UICONTROL Approval mode]**：利用此字段可定义分析完成后手动或自动投放。

  如果在分析期间生成警告（例如，如果投放主题中强调某些字符等），则可以配置投放以定义是否应仍执行此投放。 默认情况下，用户必须在分析阶段结束时确认消息的发送：这是&#x200B;**手动**&#x200B;验证。

  从相应字段的下拉列表中选择其他审批模式。

  可以使用以下审批模式：

   * **[!UICONTROL Manual]**：在分析阶段结束时，用户必须确认投放才能开始发送。 为此，请单击&#x200B;**[!UICONTROL Start]**&#x200B;按钮以启动投放。
   * **[!UICONTROL Semi-automatic]**：如果分析阶段未生成警告消息，则自动开始发送。
   * **[!UICONTROL Automatic]**：在分析阶段结束时自动开始发送，与其结果无关。

* **[!UICONTROL Start job in a detached process]**：利用此选项，可在单独的进程中启动投放分析。 默认情况下，分析函数使用Adobe Campaign应用程序服务器进程(web nlserver)。 通过选择此选项，可以确保即使在应用程序服务器出现故障时也能完成分析。
* **[!UICONTROL Log SQL queries generated during the analysis in the journal]**：此选项在分析阶段将SQL查询日志添加到投放日志。
* **[!UICONTROL Ignore personalization scripts during sending]**：此选项允许您绕过对HTML内容中找到JavaScript指令的解释。 它们将按原样显示在交付的内容中。 这些指令随`<%=`标记引入。
