---
product: campaign
title: 构建工作流
description: 了解如何构建工作流
feature: Workflows
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 4%

---

# 构建工作流 {#build-a-workflow}

## 创建新工作流 {#create-a-new-workflow}

工作流创建流程取决于工作流的类型。 您可以：

* 创建 [定位工作流](#targeting-workflows) 从 **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]** 的节点，或从 **[!UICONTROL Profiles and Targets]** 选项卡，通过 **[!UICONTROL Targeting workflows]** 子选项卡。

   ![](assets/create-targeting-wf.png)

* 创建 [活动工作流](#campaign-workflows) 从 **[!UICONTROL Targeting and workflows]** 营销活动的选项卡

* 创建 [技术工作流](#technical-workflows) 从 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** 节点。 最佳做法是创建特定的工作流文件夹以保存您的技术工作流。

单击 **[!UICONTROL New]** 按钮。

![](assets/create_a_wf_icon.png)

输入标签并单击 **[!UICONTROL Save]**.

## 添加和链接活动 {#add-and-link-activities}

您现在必须定义各种活动，并在图表中将它们链接到一起。在此配置阶段，我们可以看到图表标签和工作流状态（正在编辑）。 窗口的下部仅用于编辑图表。 它包含工具栏、活动面板（左侧）和图表本身（右侧）。

![](assets/new-workflow-2.png)

>[!NOTE]
>
>如果未显示面板，请单击工作流工具栏上的第一个按钮以显示面板。

在面板的不同选项卡中，按类别对活动进行分组。 可用的选项卡和活动可能因工作流类型（技术、定位或营销活动工作流）而异。

* 第一个选项卡包含定位和数据处理活动。 这些活动详见 [定位活动](targeting-activities.md).
* 第二个选项卡包含计划活动，主要用于协调其他活动。 这些活动详见 [流量控制活动](flow-control-activities.md).
* 第三个选项卡包含可在工作流中使用的工具和操作。 这些活动详见 [操作活动](action-activities.md).
* 第四个选项卡包含依赖于给定事件的活动，例如收到电子邮件或文件到达服务器。 这些活动详见 [事件活动](event-activities.md).

创建图表

1. 添加活动，方法是在面板中选择活动，然后使用拖放操作将其移至图表。

   添加 **开始** 活动，然后 **投放** 活动。

   ![](assets/new-workflow-3.png)

1. 通过将 **开始** 活动过渡并将其拖放到 **投放** 活动。

   ![](assets/new-workflow-4.png)

   您可以将新活动放在过渡的末尾，从而自动将活动与上一个活动链接起来。

1. 添加所需的活动并将它们链接在一起，如下图所示。

   ![](assets/new-workflow-5.png)

>[!CAUTION]
>
>您可以在同一工作流中复制并粘贴活动。 但是，我们不建议跨不同的工作流复制粘贴活动。 执行目标工作流时，附加到活动（如“投放”和“调度程序”）的某些设置可能会导致冲突和错误。 我们建议您  **复制** 工作流。 有关更多信息，请参阅 [复制工作流](#duplicate-workflows).

您可以使用以下元素更改图表的显示和布局：

* **使用工具栏**

   图表编辑工具栏允许您访问工作流的布局和执行功能。

   ![](assets/wf-toolbar.png)

   这可让您调整编辑工具的布局：面板的显示以及图形对象的概述、大小和对齐方式。

   ![](assets/s_user_segmentation_toolbar.png)

   以下章节详细介绍了与进度和日志显示相关的图标：

   * [显示进度](monitor-workflow-execution.md#displaying-progress)
   * [显示日志](monitor-workflow-execution.md#displaying-logs)

* **对象对齐**

   要对齐图标，请选择图标并单击 **[!UICONTROL Align vertically]** 或 **[!UICONTROL Align horizontally]** 图标。

   使用 **CTRL** 键可选择多个分散的活动或取消选择一个或多个活动。 单击图表背景可取消选择所有内容。

* **映像管理**

   您可以自定义图表的背景图像以及与各种活动相关的背景图像。 请参阅 [更改活动图像](change-activity-images.md).

## 配置活动 {#configure-activities}

双击某个活动以对其进行配置，或右键单击并选择 **[!UICONTROL Open...]**.

>[!NOTE]
>
>有关营销活动工作流活动的详细信息，请参阅 [此部分](activities.md).

第一个选项卡包含基本配置。 的 **[!UICONTROL Advanced]** 选项卡包含其他参数，这些参数特别用于在遇到错误时定义行为、指定活动的执行持续时间以及输入初始化脚本。

为了更好地了解活动并提高工作流的可读性，您可以在活动中输入注释。

![](assets/example1-comment.png)

当运算符滚动到活动上时，这些注释会自动显示。

![](assets/example2-comment.png)


## 工作流模板 {#workflow-templates}

工作流模板包含属性的整体配置，以及可能在图中连接的一系列活动。 此配置可重复用于创建包含特定数量的预配置元素的新工作流

您可以基于现有模板创建新的工作流模板，也可以直接将工作流更改为模板。

工作流模板存储在 **[!UICONTROL Resources > Templates > Workflow templates]** 节点。

除了常规的工作流属性之外，模板属性还允许您为基于此模板创建的工作流指定执行文件。

![](assets/wf-template-properties.png)

## 复制工作流 {#duplicate-workflows}

您可以复制不同类型的工作流。 复制后，对于原工作流的修改不会被应用到该工作流的副本。

>[!CAUTION]
>
>复制粘贴功能在工作流中可用，但我们建议您使用 **复制**. 复制活动后，将保留其整个配置。 对于投放活动（电子邮件、短信、推送通知……），还会复制附加到活动的投放对象，这可能会导致崩溃。

1. 右键单击工作流。
1. 单击 **复制**.

   ![](assets/duplicate-workflows.png)

1. 在工作流窗口中，更改工作流标签。
1. 单击&#x200B;**保存**。

复制功能不能直接在营销活动视图中提供。

但是，您可以创建一个视图来显示实例上的所有工作流。 在此视图中，您可以使用 **复制到**.

**创建视图**

1. 在 **资源管理器**，转到在中创建视图所需的文件夹。
1. 右键单击并转到 **添加新文件夹** > **进程**，选择 **工作流**.

   ![](assets/add-new-folder-workflows.png)

新文件夹 **工作流** 创建时。

1. 右键单击并选择 **属性**.
1. 在 **限制** 选项卡，启用 **此文件夹是一个视图** 选项并单击 **保存**.

   ![](assets/folder-is-a-view.png)

现在，文件夹中已填充实例的所有工作流。

**复制营销活动工作流**

1. 在工作流视图中选择营销活动工作流。
1. 右键单击 **复制到**.
1. 更改其标签。
1. 单击&#x200B;**保存**。

您可以在工作流视图中查看重复的工作流。
