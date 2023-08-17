---
title: 在Adobe Campaign中创建多维数据集
description: 了解如何创建多维数据集
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: 03a6816b-e51a-4eaf-ab76-02d24f97ba46
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 3%

---

# 创建多维数据集{#create-a-cube}

## 多维数据集工作区 {#cube-workspace}

要访问多维数据集，请浏览 **[!UICONTROL Administration > Configuration > Cubes]** 从Campaign资源管理器。

![](assets/cube-node.png)

通过多维数据集，您可以：

* 直接在报表中导出数据，在中设计 **[!UICONTROL Reports]** Adobe Campaign选项卡。

  要执行此操作，请创建新报告并选择要使用的多维数据集。

  ![](assets/create-new-cube.png)

  多维数据集看起来像模板，其创建基于哪些报告。 选择模板后，单击 **[!UICONTROL Create]** 以配置和查看新报表。

  您可以调整度量、更改显示模式或配置表，然后使用主按钮显示报表。

  ![](assets/display-cube-table.png)

* 在中引用多维数据集 **[!UICONTROL Query]** 框以使用指标，如下所示：

  ![](assets/cube-report-query.png)

* 将基于多维数据集的透视表插入报表的任何页面。 要执行此操作，请引用要用于 **[!UICONTROL Data]** 页上的数据透视表选项卡。

  ![](assets/cube-in-a-report.png)

  有关详细信息，请参见 [在报表中浏览数据](cube-tables.md#explore-the-data-in-a-report).


>[!CAUTION]
>
>创建多维数据集需要管理员权限。
>

## 构建多维数据集{#cube-create}

在开始构建多维数据集报表之前，请确定相关的维和度量，并在多维数据集中创建它们。

要创建多维数据集，请应用以下步骤：

1. 选择工作表。 [了解详情](#select-the-work-table)。
1. 定义维度。 [了解详情](#define-dimensions)。
1. 定义度量。 [了解详情](#build-indicators)。
1. 创建聚合（可选）。 [了解详情](customize-cubes.md#calculate-and-use-aggregates)。

在以下示例中，了解如何在报告中快速创建简单多维数据集以导出其度量。

### 选择工作表 {#select-the-work-table}

要创建多维数据集，请执行以下步骤：

1. 单击 **[!UICONTROL New]** 按钮。

   ![](assets/create-a-cube.png)

1. 选择包含您要浏览的元素的架构（也称为“事实架构”）。 在此示例中，选择默认值 **收件人** 表格。
1. 单击 **[!UICONTROL Save]** 创建多维数据集：将其添加到多维数据集列表。 您现在可以使用选项卡对其进行配置。

1. 单击 **[!UICONTROL Filter the source data...]** 用于将此多维数据集的计算应用于数据库中的数据的链接。

   ![](assets/cube-filter-source.png)

### 定义维度 {#define-dimensions}

创建多维数据集后，定义其维。 Dimension是根据每个多维数据集的相关事实架构为其定义的分析轴。 这些是在分析中探索的维度，如时间（年、月、日）、产品或合同的分类（家庭、参考资料等）、人口区段（按城市、年龄组、地位等）。

要创建维度，请执行以下步骤：

1. 浏览至 **[!UICONTROL Dimension]** 立方的选项卡，然后单击 **[!UICONTROL Add]** 按钮以创建新维度。
1. 在 **[!UICONTROL Expression field]**，单击 **[!UICONTROL Edit expression]** 图标以选择包含相关数据的字段。

   ![](assets/cube-add-dimension.png)

1. 在本例中，我们将选择收件人 **年龄**. 对于此字段，您可以定义对年龄进行分组，并使信息阅读更加容易。 当存在多个单独值的可能性时，我们建议使用量化。

要执行此操作，请查看 **[!UICONTROL Enable binning]** 选项。 [了解详情](customize-cubes.md#data-binning)。

1. 添加 **日期** 类型维度。 在这里，我们要显示收件人用户档案创建日期。 为此，请单击 **[!UICONTROL Add]** 并选择 **[!UICONTROL Creation date]** 收件人表中的字段。
您可以自定义日期显示模式。 要执行此操作，请选择要使用的层次和要生成的级别：

![](assets/cube-date-dimension.png)

在我们的示例中，我们只希望显示年、月和日。 请注意，您不能同时使用周和学期/月：这些级别不兼容。

1. 创建另一个维度以分析相对于收件人城市的数据。 要执行此操作，请添加新维度并在 **[!UICONTROL Location]** 收件人模式的节点。

您可以启用量化以使信息读取更轻松并将值链接到明细列表。

从下拉列表中选择明细列表。 请注意，必须将此枚举定义为 **[!UICONTROL Reserved for binning]**.

![](assets/cube-dimension-with-enum.png)

将仅显示枚举中的值。 其他组将按照 **[!UICONTROL Label of the other values]** 字段。

如需详细信息，请参阅[此部分](customize-cubes.md#dynamically-manage-bins)。

### 构建指标 {#build-indicators}

定义维后，为要在单元格中显示的值指定计算模式。

要实现此目的，请在 **[!UICONTROL Measures]** 选项卡。 根据此多维数据集创建要显示在报表中的列数。

要构建指标，请执行以下步骤：

1. 浏览至 **[!UICONTROL Measures]** 选项卡，然后单击 **[!UICONTROL Add]** 按钮。
1. 选择要应用的度量类型和公式。 在本例中，我们统计了接收者中的妇女人数。 我们的衡量标准基于事实架构，并使用 **[!UICONTROL Count]** 运算符。

   ![](assets/cube-new-measure.png)

   使用 **[!UICONTROL Filter the measure data...]** 仅选择女性的链接。 [了解详情](customize-cubes.md#define-measures)。

   ![](assets/cube-filter-measure-data.png)

1. 输入度量的标签并保存。

   ![](assets/cube-save-measure.png)

1. 保存多维数据集。


您现在可以基于此多维数据集创建报告。 [了解详情](cube-tables.md)。
