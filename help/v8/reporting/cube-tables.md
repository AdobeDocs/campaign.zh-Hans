---
product: campaign
title: 使用多维数据集创建数据报告
description: 了解如何使用多维数据集创建报告
feature: Reporting
source-git-commit: 7fc3e5b9f12ca48ef0921e27844ef9fef71ac06b
workflow-type: tm+mt
source-wordcount: '941'
ht-degree: 1%

---

# 使用多维数据集浏览数据{#use-cubes-to-create-reports}

使用多维数据集创建报告，并识别和选择数据库中的数据。 您可以：

* 根据多维数据集创建报告。 [了解详情](#explore-the-data-in-a-report)。
* 收集数据库中的数据并将其分组到列表中，例如，识别和构建目标和投放。 [了解详情](#build-a-target-population)。
* 在报表中插入数据透视表，引用报表中的现有多维数据集。 [了解详情](#insert-a-pivot-table-into-a-report)。

## 浏览报表中的数据 {#explore-the-data-in-a-report}

### 第1步 — 基于多维数据集创建报告 {#step-1---create-a-report-based-on-a-cube}

一旦 [多维数据集已配置](cube-indicators.md)，则可将其用作创建新报表的模板。

要基于现有多维数据集创建报告，请执行以下步骤：

1. 单击 **[!UICONTROL Create]** 按钮 **[!UICONTROL Reports]** 选项卡，然后选择您刚刚创建的多维数据集。

   ![](assets/new-report-based-on-cube.png)

1. 单击 **[!UICONTROL Create]** 按钮确认：这会将您转到报表配置和查看页面。

   默认情况下，前两个可用维度以行和列的形式提供，但表中不显示任何值。 要生成表，请单击主图标：

   ![](assets/cube-report-config.png)

1. 可以切换尺寸的轴、删除这些轴、添加新测量等。 为此，请使用相应的图标。

   ![](assets/cube-switch-axis.png)

   这些操作详见下文。

### 步骤2 — 选择行和列 {#step-2---select-lines-and-columns}

默认显示显示立方的前两个维度（在本例中为年龄和城市）。

的 **[!UICONTROL Add]** 通过每个轴上的按钮，可添加尺寸。

![](assets/cube-switch.png)

1. 选择要在表的行和列中显示的尺寸。 为此，请拖放可用的维度。
1. 从列表中选择要添加到表格的维度：
   ![](assets/cube-select-dimension.png)

1. 然后，选择此维度的参数。

   ![](assets/cube-dimension-param.png)

   这些参数取决于所选维度的数据类型。

   例如，对于日期，可以使用多个级别。 有关更多信息，请参阅 [显示度量](customize-cubes.md#display-measures).

   在这种情况下，可以使用以下选项：

   ![](assets/cube-config.png)

   您可以：

   * 在加载期间展开数据：默认情况下，每次更新报表时，都会显示这些值(默认值：否)。
   * 在行末显示总计：当数据显示在列中时，您还可以使用其他选项在行末尾显示总计：列即会添加到表中(默认值：是)。
   * 应用排序：可以根据值、标签或度量(默认值：值)。
   * 以升序(a-z， 0-9)或降序(z-a， 9-0)显示值。
   * 更改加载时要显示的列数(默认情况下：200)。

1. 单击 **[!UICONTROL Ok]** 确认：该维度会添加到现有维度。

   表格上方的黄色横幅显示您已进行更改：单击 **[!UICONTROL Save]** 按钮以保存它们。

   ![](assets/cube-in-report.png)

### 步骤3 — 配置要显示的测量 {#step-3---configure-the-measures-to-display}

定义行和列后，选择要显示的度量。 默认情况下，只显示一个度量。

要添加和配置措施，请执行以下步骤：

1. 单击 **[!UICONTROL Measures]** 按钮。

   ![](assets/cube-measure-button.png)

1. 维特 **[!UICONTROL Use a measure]** 按钮，选择现有度量之一。

   ![](assets/cube-add-measure.png)

   选择要显示的信息和格式选项。 选项列表取决于度量类型。

   ![](assets/cube-measure-options.png)

   还可通过 **[!UICONTROL Edit the configuration of the pivot table]** 图标。

   ![](assets/cube-pivot-table-config.png)

   然后，您可以选择是否显示测量标签。 [了解详情](customize-cubes.md#configure-the-display)。

1. 您可以基于现有度量来构建新度量。 为此，请单击 **[!UICONTROL Create a measure]** 并对其进行配置。

   ![](assets/cube-create-new-measure.png)

   可使用以下类型的度量：

   * 措施组合：此类型的度量允许您使用现有度量构建新度量：

      可用的运算符包括：和、差、乘和速率。

   * 比例：此类型的度量允许您计算针对给定维度测量的记录数。 您可以根据维或子维计算比例。
   * 变量：此度量允许您计算级别值的变化。
   * 标准偏差：此类型的度量允许您计算每组单元格中与平均值之间的偏差。 例如，您可以比较所有现有区段的购买量。

   创建后，该度量将添加到报表中。

   ![](assets/cube-display-new-measure.png)

   创建度量后，可以编辑它并更改其配置。 为此，请单击 **[!UICONTROL Measures]** 按钮，然后浏览到要编辑的测量的选项卡。

   然后，单击 **[!UICONTROL Edit the dynamic measure]** 来访问“设置”菜单。

## 构建目标群体 {#build-a-target-population}

使用多维数据集构建报表允许您从表中收集数据并将其保存在列表中。

要将群体分组到列表中，请执行以下步骤：

1. 单击包含要收集的群体的单元格以选择它们，然后单击 **[!UICONTROL Add to cart]** 图标。

   ![](assets/cube-add-to-cart.png)

   收集各种用户档案时，需要多次执行此操作

1. 单击 **[!UICONTROL Show cart]** 按钮以查看其内容。

   ![](assets/cube-show-cart.png)

1. 使用 **[!UICONTROL Export]** 按钮将购物车中的项目分组到列表中。

   输入列表名称并选择要执行的导出类型。

   ![](assets/cube-export-report.png)

   单击 **[!UICONTROL Start]** 以运行导出。

1. 导出完成后，将显示一条消息，确认其执行情况以及已处理的记录数。

   ![](assets/cube-export-confirm.png)

   您可以保存购物车的内容或将其清空。

   新列表可通过 **[!UICONTROL Profiles and targets]** 选项卡。

   ![](assets/cube-list-available.png)

## 将数据透视表插入报表 {#insert-a-pivot-table-into-a-report}

要创建表并浏览多维数据集中的数据，请执行以下步骤：

1. 使用单个页面创建新报表，并在其中插入数据透视表。

   ![](assets/cube-insert-in-report.png)

1. 在 **[!UICONTROL Data]** 选项卡中，选择一个多维数据集以处理它包含的维度并显示计算量度。

   ![](assets/cube-selected-in-report.png)

   这样，您就可以生成要显示的报表。 有关更多信息，请参阅 [步骤2 — 选择行和列](#step-2---select-lines-and-columns).
