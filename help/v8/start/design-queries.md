---
title: 在Campaign v8中设计查询
description: 了解如何创建查询
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: adea4eb54f3d519802119646bc501aae2ef5f831
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 3%

---

# 查询营销活动数据库

使用所选表的字段或使用公式可以创建查询。

在Adobe Campaign中构建查询的步骤如下所示：

1. [选择工作表](#step-1---choose-a-table)。
1. [选择要提取的数据](#step-2---choose-data-to-extract)。
1. [定义数据排序模式](#step-3---sort-data)。
1. [定义数据过滤选项](#step-4---filter-data)。
1. [配置数据格式](#step-5---format-data)。
1. [预览查询结果](#step-6---preview-data)。

所有这些步骤在[通用查询编辑器](query-editor.md)中均可用。 在另一个上下文中创建查询时，某些步骤可能缺失。 若要了解有关查询的更多信息，另请参阅[工作流查询活动文档](../../automation/workflow/query.md)。


## 第1步 — 选择表 {#step-1---choose-a-table}

要查询Campaign数据库，请打开&#x200B;**[通用查询编辑器](query-editor.md)**，然后在&#x200B;**[!UICONTROL Document type]**&#x200B;窗口中选择包含要查询的数据的表。

![](assets/query_editor_nveau_21.png)

如果需要，请使用筛选器字段或&#x200B;**[!UICONTROL Filters]**&#x200B;按钮筛选数据。

## 步骤2 — 选择要提取的数据 {#step-2---choose-data-to-extract}

在&#x200B;**[!UICONTROL Data to extract]**&#x200B;屏幕上，选择要包含在输出中的字段。 这些字段将定义结果中显示的列。

例如，您可以选择&#x200B;**[!UICONTROL Age]**、**[!UICONTROL Primary key]**、**[!UICONTROL Email domain]**&#x200B;和&#x200B;**[!UICONTROL City]**。 将根据此选择构建输出。 要调整列的顺序，请使用窗口右侧的蓝色箭头。

![](assets/query_editor_nveau_01.png)

您可以通过添加公式或向聚合函数应用进程来修改表达式。 要编辑表达式，请单击&#x200B;**[!UICONTROL Expression]**&#x200B;列字段，然后选择&#x200B;**[!UICONTROL Edit expression]**。

![](assets/query_editor_nveau_97.png)

您可以对输出列中显示的数据进行分组。 为此，请在&#x200B;**[!UICONTROL Yes]**&#x200B;窗口的&#x200B;**[!UICONTROL Group]**&#x200B;列中选择&#x200B;**[!UICONTROL Data to extract]**。 然后，将根据所选的分组轴聚合结果。 有关使用分组的查询示例，请参阅[此部分](../../automation/workflow/query-delivery-info.md)。

![](assets/query_editor_nveau_56.png)

* **[!UICONTROL Handle groupings (GROUP BY + HAVING)]**&#x200B;选项允许您对结果分组，并将条件应用于这些组。 它适用于输出列中的所有字段。 例如，您可以使用它对输出列中的值进行分组，然后筛选结果以仅检索特定信息，例如年龄在35到50岁之间的收件人。

  如需详细信息，请参阅[此小节](../../automation/workflow/query-grouping-management.md)。

**[!UICONTROL Remove duplicate rows (DISTINCT)]**&#x200B;选项从输出中消除相同的行（删除重复项）。 例如，如果您选择&#x200B;**姓氏**、**名字**&#x200B;和&#x200B;**电子邮件**&#x200B;作为输出列，则所有三个字段中具有相同值的任何记录都将被视为重复项。 结果中将只保留一个实例，确保每个联系人仅出现一次。

## 步骤3 — 排序数据 {#step-3---sort-data}

**[!UICONTROL Sorting]**&#x200B;窗口允许您对列内容进行排序。 使用箭头可更改列顺序：

* **[!UICONTROL Sorting]**&#x200B;列启用简单排序并按从A到Z或升序排列列内容。
* **[!UICONTROL Descending sort]**&#x200B;将内容从Z到A按降序排列。 这对于查看记录销售额非常有用，例如：最高数字显示在列表顶部。

在此示例中，数据根据收件人年龄按升序排序。

![](assets/query_editor_nveau_57.png)

## 第4步 — 筛选数据 {#step-4---filter-data}

利用查询编辑器，可筛选数据以缩小结果范围。 可用的过滤器取决于您要查询的表。

![](assets/query_editor_nveau_09.png)

选择&#x200B;**[!UICONTROL Filtering conditions]**&#x200B;后，**[!UICONTROL Target elements]**&#x200B;部分打开。 在这里，您可以定义用于筛选要收集的数据的规则。

* 要创建新过滤器，请选择构建条件所需的字段、运算符和值。 您还可以合并多个条件，如本页[上的](filter-conditions.md)所述。

* 要重用现有的筛选器，请单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮，选择&#x200B;**[!UICONTROL Predefined filter]**&#x200B;并选择所需的筛选器。

  ![](assets/query_editor_15.png)

在&#x200B;**[!UICONTROL Generic query editor]**&#x200B;中创建的筛选器可以在其他查询应用程序中重用，反之亦然。 要保存过滤器以供将来使用，请单击&#x200B;**[!UICONTROL Save]**&#x200B;图标。

>[!NOTE]
>
>有关创建和使用筛选器的详细信息，请参阅[筛选选项](filter-conditions.md)。

如以下示例所示，要恢复所有说英语的收件人，请选择“收件人语言&#x200B;**等于** EN”。

![](assets/query_editor_nveau_89.png)

>[!NOTE]
>
>您可以通过在&#x200B;**值**&#x200B;字段中键入以下公式来直接访问选项： **$(options:OPTION_NAME)**。

单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡以查看筛选条件的结果。 在这种情况下，所有说英语的收件人都会显示其姓名、名字和电子邮件地址。

![](assets/query_editor_nveau_98.png)

熟悉SQL语言的用户可以单击&#x200B;**[!UICONTROL Generate SQL query]**&#x200B;查看SQL中的查询。

![](assets/query_editor_nveau_99.png)

## 步骤5 — 设置数据格式 {#step-5---format-data}

配置限制筛选器后，**[!UICONTROL Data formatting]**&#x200B;窗口将打开。 在此窗口中，您可以重新排列输出列、转换数据和调整列标签大小写。 您还可以通过创建计算字段将公式应用于最终结果。

>[!NOTE]
>
>有关计算字段类型的详细信息，请参阅[创建计算字段](filter-conditions.md#creating-calculated-fields)。

未选中的列在数据预览窗口中隐藏。

![](assets/query_editor_nveau_10.png)

通过&#x200B;**[!UICONTROL Transformation]**&#x200B;列，可将列标签更改为大写或小写。 选择该列并单击&#x200B;**[!UICONTROL Transformation]**&#x200B;列中的。 您可以选择：

* **[!UICONTROL Switch to lower case]**，
* **[!UICONTROL Switch to upper case]**，
* **[!UICONTROL First letter in upper case]**。

![](assets/query_editor_nveau_42.png)

## 步骤6 — 预览数据 {#step-6---preview-data}

**[!UICONTROL Data preview]**&#x200B;窗口标记了查询过程的最后阶段。 单击&#x200B;**[!UICONTROL Start the preview of the data]**&#x200B;查看结果，结果可以按列或XML格式显示。 要检查基础SQL查询，请打开&#x200B;**[!UICONTROL Generated SQL queries]**&#x200B;选项卡。 此步骤允许您验证查询在进一步使用它之前是否按预期运行。

在此示例中，数据根据收件人年龄按升序排序。

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>与中的控制台中所有可用列表一样，默认情况下，**[!UICONTROL Data preview]**&#x200B;窗口中仅显示前200行。 若要更改此设置，请在&#x200B;**[!UICONTROL Lines to display]**&#x200B;框中输入一个数字，然后单击&#x200B;**[!UICONTROL Start the preview of the data]**。 [了解详情](../config/ui-settings.md#manage-and-customize-lists)



**相关主题**

* [工作流查询活动](../../automation/workflow/query.md)
* [查询收件人表](../../automation/workflow/querying-recipient-table.md)
* [筛选条件](filter-conditions.md)