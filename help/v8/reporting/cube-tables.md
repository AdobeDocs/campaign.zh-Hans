---
product: campaign
title: 使用多维数据集创建数据报告
description: 了解如何使用多维数据集创建报告
feature: Reporting
role: User, Developer
level: Beginner
exl-id: 7dbc66ab-a468-40ff-9db2-b33e4fd27754
TQID: 'https://experienceleague.adobe.com/fVo8tGw-kPgGgB7djOQr8tv5MoRvrPr-MF2bzYYKDgI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 82ae202007873dab2324bfa4b13a6014efd19887
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 1%
---
# 使用多维数据集浏览数据{#use-cubes-to-create-reports}

使用多维数据集创建报告，并识别和选择数据库中的数据。 您可以：

* 根据多维数据集创建报告。 [了解详情](#explore-the-data-in-a-report)。
* 收集数据库中的数据，并将其分组到列表中，例如，识别和构建目标和投放。 [了解详情](#build-a-target-population)。
* 将透视表插入报表中，引用其中的现有多维数据集。 [了解详情](#insert-a-pivot-table-into-a-report)。

## 在报表中浏览数据 {#explore-the-data-in-a-report}

### 第1步 — 基于多维数据集创建报告 {#step-1---create-a-report-based-on-a-cube}

配置[多维数据集后](cube-indicators.md)，可将其用作创建新报告的模板。

要基于现有多维数据集创建报告，请执行以下步骤：

1. 单击&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡的&#x200B;**[!UICONTROL Create]**&#x200B;按钮，然后选择刚刚创建的多维数据集。

   ![使用“新建客户端配置文件”多维数据集模板和“创建”按钮创建新报告页面](assets/new-report-based-on-cube.png)

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮确认：这会将您转到报告配置和查看页面。

   默认情况下，前两个可用尺寸以行和列提供，但表中不显示任何值。 要生成表，请单击主图标：

   ![具有年龄和创建日期轴以及显示数据透视表的图标的新客户端配置文件报表](assets/cube-report-config.png)

1. 可以切换尺寸的轴、删除它们、添加新测量等。要实现此目的，请使用相应的图标。

   ![在新建客户端配置文件报表中，创建日期维度从左轴拖动到年龄旁边的上轴](assets/cube-switch-axis.png)

   这些操作详见下文。

### 第2步 — 选择行和列 {#step-2---select-lines-and-columns}

默认显示显示多维数据集的前两个维（在本例中是年龄和城市）。

每个轴上的&#x200B;**[!UICONTROL Add]**&#x200B;按钮允许您添加维度。

![添加用于添加维度的新客户端配置文件报表的行轴上的添加按钮](assets/cube-switch.png)

1. 选择要显示在表的行和列中的尺寸。 为此，请拖放可用的维度。
1. 从列表中选择要添加到表中的维：
   ![将维度添加到列有城市、国家/地区、上次购买日期和购买金额的列对话框中](assets/cube-select-dimension.png)

1. 然后选择此尺寸的参数。

   ![城市的Dimension设置：标签、加载时展开、数据排序、显示行的顺序和行数](assets/cube-dimension-param.png)

   这些参数取决于所选维的数据类型。

   例如，对于日期，可以使用多个级别。 有关详细信息，请参阅[显示度量](customize-cubes.md#display-measures)。

   在这种情况下，可以使用以下选项：

   ![每个级别、年份和月份的日期维度设置，包括长格式或短格式](assets/cube-config.png)

   您可以：

   * 加载期间展开数据：默认情况下，每次更新报表时都会显示这些值（默认值：否）。
   * 在行末显示合计：当数据以列显示时，附加选项允许您在行末显示合计：向表中添加一列（默认值：是）。
   * 应用排序：列的值可以根据值、标签或度量进行排序（默认值：按值）。
   * 按升序(a-z， 0-9)或降序(z-a， 9-0)显示值。
   * 更改加载时要显示的列数（默认情况下： 200）。

1. 单击&#x200B;**[!UICONTROL Ok]**&#x200B;确认：该维度已添加到现有维度。

   表上方的黄色横幅显示您已进行更改：单击&#x200B;**[!UICONTROL Save]**&#x200B;按钮进行保存。

   ![城市已添加到折线轴，黄色横幅提示您保存报告更改](assets/cube-in-report.png)

### 步骤3 — 配置要显示的度量 {#step-3---configure-the-measures-to-display}

定义行和列后，选择要显示的度量。 默认情况下，只显示一个度量。

要添加和配置度量，请执行以下步骤：

1. 单击 **[!UICONTROL Measures]** 按钮。

   ![使用“标签”、“格式”和“单位”选项打开“配置度量”对话框的“度量”按钮](assets/cube-measure-button.png)

1. 使用&#x200B;**[!UICONTROL Use a measure]**&#x200B;按钮，选择现有度量之一。

   ![将现有度量值添加到列有法语、德语、男性和女性的透视表对话框中](assets/cube-add-measure.png)

   选择要显示的信息和格式选项。 选项列表取决于测量类型。

   ![使用“格式选项”“数字”和“百分比”配置“度量”对话框并编辑“动态度量”按钮](assets/cube-measure-options.png)

   通过标题中的&#x200B;**[!UICONTROL Edit the configuration of the pivot table]**&#x200B;图标，还可以使用整体度量值配置。

   ![在报表工具栏中编辑数据透视表配置图标](assets/cube-pivot-table-config.png)

   然后，您可以选择是否显示度量标签。 [了解详情](customize-cubes.md#configuring-the-display)。

1. 您可以基于现有度量构建新度量。 为此，请单击&#x200B;**[!UICONTROL Create a measure]**&#x200B;并进行配置。

   ![使用度量类型、运算符和两个度量的组合创建动态度量对话框](assets/cube-create-new-measure.png)

   可用的测量类型如下：

   * 测量组合：此类型的测量允许您使用现有测量构建新测量：

     可用的运算符有：和、差、乘和速率。

   * 比例：此类型的测量使您能够计算针对给定维度测量的记录数。 您可以根据维度或子维度计算比例性。
   * 变量：通过此度量，可计算某个级别值的变量。
   * 标准偏差：通过此类度量，可计算每组单元格内与平均值之间的偏差。 例如，您可以比较所有现有区段的购买量。

   创建之后，度量会添加到报表中。

   ![数据透视表按公司在“男女”旁显示新的德语和英语度量值](assets/cube-display-new-measure.png)

   创建测量后，可以对其进行编辑并更改其配置。 为此，请单击&#x200B;**[!UICONTROL Measures]**&#x200B;按钮，然后浏览到要编辑的度量的选项卡。

   然后单击&#x200B;**[!UICONTROL Edit the dynamic measure]**&#x200B;以访问设置菜单。

## 构建目标群体 {#build-a-target-population}

使用多维数据集构建的报告允许您从表中收集数据并将其保存在列表中。

要将群体分组到列表中，请执行以下步骤：

1. 单击包含要收集的群体的单元格以选择它们，然后单击&#x200B;**[!UICONTROL Add to cart]**&#x200B;图标。

   ![在包含选定单元格的CLIENTS数据透视表的工具栏中，添加到购物车图标](assets/cube-add-to-cart.png)

   根据需要执行此操作多次，以收集各种用户档案。

1. 单击&#x200B;**[!UICONTROL Show cart]**&#x200B;按钮以查看其内容，然后再运行导出。

   ![显示购物车按钮打开包含购物车项目的购物车详细信息对话框和导出按钮](assets/cube-show-cart.png)

1. 使用&#x200B;**[!UICONTROL Export]**&#x200B;按钮将购物车中的项目分组到列表中。

   输入列表名称并选择要执行的导出类型。

   ![导出到新列表、标签、文件夹和导出类型以及“开始”按钮的导出购物车1/2对话框](assets/cube-export-report.png)

   单击&#x200B;**[!UICONTROL Start]**&#x200B;以运行导出。

1. 导出完成后，将显示一条消息，确认其执行和已处理的记录数。

   ![导出购物车2/2对话框确认导出已完成，记录数已达，并关闭按钮](assets/cube-export-confirm.png)

   您可以保存购物车的内容或将其清空。

   新列表可通过&#x200B;**[!UICONTROL Profiles and targets]**&#x200B;选项卡使用。

   ![在“配置文件和目标”下列出页面，显示新的金牌收件人列表](assets/cube-list-available.png)

## 在报表中插入数据透视表 {#insert-a-pivot-table-into-a-report}

要创建表并浏览多维数据集中的数据，请执行以下步骤：

1. 创建一个具有单个页面的新报表，并在其中插入数据透视表。

   ![具有页面活动和工具栏菜单中的透视表选项的报表编辑器](assets/cube-insert-in-report.png)

1. 在该页的&#x200B;**[!UICONTROL Data]**&#x200B;选项卡中，选择一个多维数据集以处理它包含的维并显示计算的度量。

   在Cube字段中选择了New Client Profile多维数据集的透视表的![数据选项卡](assets/cube-selected-in-report.png)

   这样，您就可以构建要显示的报表。 有关详细信息，请参阅[第2步 — 选择行和列](#step-2---select-lines-and-columns)。
