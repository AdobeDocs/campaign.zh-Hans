---
title: Campaign界面设置
description: 了解如何自定义Campaign界面设置
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '1848'
ht-degree: 12%

---

# Campaign用户界面设置 {#ui-settings}

## 默认单位 {#default-units}

在Adobe Campaign中，对于表示持续时间（例如资源的有效期、任务的审批截止日期等）的字段，值可以按以下&#x200B;**单位**&#x200B;表示：

* **[!UICONTROL s]**&#x200B;表示秒
* **[!UICONTROL mn]**&#x200B;表示分钟
* **[!UICONTROL h]**&#x200B;表示小时
* **[!UICONTROL d]**&#x200B;天

## 自定义Campaign资源管理器{#customize-explorer}

您可以将文件夹添加到Campaign Explorer、创建视图和分配权限。

在[此页面](../audiences/folders-and-views.md)中了解如何管理文件夹和视图

## 管理和自定义列表{#customize-lists}

在Campaign客户端控制台中，数据显示在列表中。 您可以根据自己的需求调整这些列表。 例如，您可以添加列、过滤数据、计算记录、保存和共享设置。

此外，您还可以创建和保存过滤器。  在[此页面](../audiences/create-filters.md)中了解有关筛选器的更多信息。

### 记录数 {#number-of-records}

默认情况下，Adobe Campaign会加载列表的前200条记录。 这意味着显示不一定显示您正在查看的表的所有记录。 您可以统计列表中的记录数量并加载更多记录。

在列表屏幕的右下角，**计数器**&#x200B;会显示已加载的记录数，以及数据库中的记录总数（应用任何过滤器之后的记录数）：

![显示列表中的记录总数](assets/number-of-records.png)

如果出现问号而不是右侧的数字（如`240/?`），请单击计数器以启动计算。

要加载和显示其他记录，请单击&#x200B;**[!UICONTROL Continue loading]**。 默认情况下，将加载200条记录。 要更改默认加载的记录数，请使用列表右下角的&#x200B;**[!UICONTROL Configure list]**&#x200B;图标。 在列表配置窗口中，单击&#x200B;**[!UICONTROL Advanced parameters]** （左下方）并更改要检索的行数。

要加载所有记录，请右键单击列表并选择&#x200B;**[!UICONTROL Load all]**。

>[!CAUTION]
>
>当列表包含大量记录时，完全加载可能需要一些时间。
>

### 添加和删除列 {#add-columns}

对于每个列表，内置列配置可适于显示更多信息或隐藏未使用的列。

当数据在记录的详细信息中可见时，右键单击该字段并选择&#x200B;**[!UICONTROL Add in the list]**。

![在列表中添加字段](assets/add-in-the-list.png)

该列会添加到现有列的右侧。

![添加字段列](assets/add-a-column.png)

您还可以使用列表配置屏幕添加和删除列：

1. 从记录列表中，单击右下角的&#x200B;**[!UICONTROL Configure list]**&#x200B;图标。
1. 双击要添加到&#x200B;**[!UICONTROL Available fields]**&#x200B;列表中的字段：它们已添加到&#x200B;**[!UICONTROL Output columns]**&#x200B;列表。

   ![列出配置屏幕](assets/list-config-screen.png)


   >[!NOTE]
   >
   >默认情况下，不显示高级字段。 要显示它们，请单击可用字段列表右下角的&#x200B;**显示高级字段**&#x200B;图标。
   >
   >通过具体图标标识各字段：SQL 字段、链接的表、已计算字段等。针对选中的每个字段，在可用字段的列表下会显示其说明。
   >

1. 使用上/下箭头修改&#x200B;**显示顺序**。

1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;以确认配置并显示结果。

如果需要删除列，请选择该列并单击&#x200B;**垃圾桶**&#x200B;图标。

您可以使用&#x200B;**[!UICONTROL Distribution of values]**&#x200B;图标查看当前文件夹中选定字段值的重新分区。

![](assets/value-distribution.png)


### 新建列 {#create-a-new-column}

您可以创建新的列来显示列表中的其他字段。

要创建列，请执行以下步骤：

1. 从记录列表中，单击右下角的&#x200B;**[!UICONTROL Configure list]**&#x200B;图标。
1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;图标以在列表中显示新字段。
1. 配置要添加到列中的字段。


### 在子文件夹中显示数据 {#display-sub-folders-records}

列表可显示：

* 所选文件夹中包含的所有记录（默认）
* 选定文件夹及其子文件夹中包含的所有记录

要从一种显示模式切换到另一种显示模式，请单击“促销活动”工具栏中的&#x200B;**[!UICONTROL Display sub-levels]**。

### 保存列表配置 {#saving-a-list-configuration}

列表配置是为每个用户本地定义的。 清空本地缓存时，本地配置被禁用。

默认情况下，设置参数适用于具有相应文件夹类型的所有列表。 当您修改文件夹中收件人列表的显示方式时，此配置将应用于所有其他收件人文件夹。

您可以保存多个要应用于相同类型不同文件夹的配置。 该配置会随包含数据的文件夹的属性一同保存，并可重新应用。

要保存列表配置以便重复使用，请执行以下步骤：

1. 在资源管理器中，右键单击包含所显示数据的文件夹。
1. 选择 **[!UICONTROL Properties]**。
1. 单击&#x200B;**[!UICONTROL Advanced settings]**，然后在&#x200B;**[!UICONTROL Configuration]**&#x200B;字段中指定名称。
1. 单击&#x200B;**[!UICONTROL OK]**，然后单击&#x200B;**[!UICONTROL Save]**。

然后，您可以将此配置应用于相同类型的任何其他文件夹。 在[此页面](../audiences/folders-and-views.md)中了解有关文件夹的更多信息。

### 导出列表 {#exporting-a-list}

要从列表中导出数据，必须使用导出向导。 要访问它，请从列表中选择要导出的元素，右键单击并选择&#x200B;**[!UICONTROL Export...]**。

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>不得使用“复制/粘贴”功能从列表中导出元素。

### 对列表排序 {#sorting-a-list}

列表可能包含大量数据。 您可以对这些数据进行排序，或者应用简单或高级过滤器。 排序允许您按升序或降序显示数据。 您可以利用过滤器来定义并组合各种标准，从而仅显示所选的数据。

单击列标题可应用升序或降序排序，或取消数据排序。 活动排序状态和排序顺序在列标签之前用蓝色箭头指示。 列标签前面的红色短划线表示排序应用于从数据库索引的数据。 此排序方法用于优化排序作业。

您还可以配置排序或组合排序标准。 为此请执行以下操作步骤：

1. 列表右侧的下方&#x200B;**[!UICONTROL Configure list]**。
1. 在列表配置窗口中，单击&#x200B;**[!UICONTROL Sorting]**&#x200B;选项卡。
1. 选择要排序的字段以及排序方向（升序或降序）。
1. 排序优先级由排序列的顺序定义。 要改变优先级，可使用适当的图标改变各列的顺序。

   排序优先级不会影响列表中各类的显示情况。

1. 单击&#x200B;**[!UICONTROL Ok]**&#x200B;以确认此配置并在列表中显示结果。




## 使用明细列表 {#enumerations}

枚举（也称为“明细列表”）是系统建议用于填充字段的值列表。 使用枚举来标准化这些字段的值，帮助在查询中输入或使用数据。

值列表将显示为一个下拉列表，您可以从中选择要在字段中输入的值。 下拉列表还支持预测输入：输入第一个字母，应用程序填充其余字母。

此类字段的值已定义，通过树的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;节点对这些字段执行整体管理（添加/删除值）。

![访问枚举](assets/enumerations-menu.png)

### 枚举类型 {#types-of-enum}

枚举存储在资源管理器的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;文件夹中。

它们可以是：开放、系统、表情符号或闭合。

* **Open**&#x200B;枚举允许用户直接基于此枚举在字段中添加新值。
* **Closed**&#x200B;枚举具有只能从资源管理器的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;文件夹中修改的固定值列表。
* **表情符号**&#x200B;枚举用于更新表情符号列表。 了解详情
* **系统**&#x200B;枚举与系统字段相关联，并带有内部名称。

对于&#x200B;**Open**&#x200B;和&#x200B;**Closed**&#x200B;枚举，可以使用特定选项：

* **简单枚举**&#x200B;是默认的标准类型。
* **别名清理**&#x200B;枚举用于协调存储在数据库中的枚举值。 [了解详情](#alias-cleansing)
* **保留用于量化**&#x200B;是一个选项，它允许您将Cube值链接到此枚举。 [了解详情](../reporting/gs-cubes.md)


### 别名清理 {#alias-cleansing}

在枚举字段中，您可以选择值，或输入在下拉列表中不可用的自定义值。 可以将自定义值作为新值添加到现有枚举值中 — 在这种情况下，必须选择&#x200B;**[!UICONTROL Open]**&#x200B;选项。 可以使用别名清理功能清理这些自定义值。 例如，如果用户输入`Adob`而不是`Adobe`，则别名清理过程可以自动用正确的术语替换它。

>[!CAUTION]
>
>数据清理是影响数据库中数据的关键过程。 Adobe Campaign会执行批量数据更新，这可能会导致某些值被删除。 因此，此操作是为专家用户保留的。

启用&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;选项以使用枚举的数据清理功能。 选择此选项时，**[!UICONTROL Alias]**&#x200B;选项卡将显示在窗口的底部。

当用户输入的值在Alias清理枚举中不存在时，该值会被添加到&#x200B;**值**&#x200B;列表中。 您可以[根据这些值](#convert-to-alias)创建别名，或[从头开始创建新别名](#create-alias)。

#### 创建别名{#create-alias}

要创建别名，请执行以下步骤：

1. 单击&#x200B;**[!UICONTROL Alias]**&#x200B;选项卡的&#x200B;**[!UICONTROL Add]**&#x200B;按钮。
1. 输入要转换的别名，然后在下拉列表中选择要应用的值。

   ![创建新别名](assets/new-alias.png)

1. 单击&#x200B;**[!UICONTROL Ok]**&#x200B;并确认。

1. 保存您的更改。值替换由&#x200B;**别名清理**&#x200B;工作流执行，该工作流每晚执行。 请参阅[运行数据清理](#running-data-cleansing)。

对于基于此枚举的所有字段，当用户在“company”字段(在Adobe Campaign客户端控制台的Web窗体中)中输入值&#x200B;**Adobe**&#x200B;时，该值将自动被值&#x200B;**Adobe**&#x200B;替换。

#### 将错误值转换为别名{#convert-to-alias}

您还可以将现有枚举值转换为别名。 要执行此操作，请执行以下操作：

1. 在枚举的值列表中，右键单击并浏览到&#x200B;**[!UICONTROL Actions... > Convert values into aliases...]**。

   ![将值转换为别名](assets/convert-into-aliases.png)

1. 选择要以别名转换的值，然后单击&#x200B;**[!UICONTROL Next]**。
1. 单击&#x200B;**[!UICONTROL Start]**&#x200B;运行转换。

   执行完成后，别名将添加到&#x200B;**别名**&#x200B;选项卡的列表中。 您可以关联正确的值以替换错误的条目。 要执行此操作，请执行以下操作：

1. 选择要清除的值。
1. 单击&#x200B;**详细信息……**&#x200B;按钮。
1. 在下拉列表中选择新值。

   ![创建新别名](assets/define-new-alias.png)


>[!NOTE]
>
>您可以在&#x200B;**[!UICONTROL Alias]**&#x200B;子选项卡的&#x200B;**[!UICONTROL Hits]**&#x200B;列中跟踪别名的发生次数。 它可以显示输入此值的次数。  [了解详情](#calculate-entry-occurrences)。

#### 运行数据清理 {#running-data-cleansing}

数据清理由&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;技术工作流执行。 默认情况下，此工作流每日执行。

清理也可以通过&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;链接触发。

通过&#x200B;**[!UICONTROL Advanced parameters...]**&#x200B;链接，可设置考虑收集值的开始日期。

单击&#x200B;**[!UICONTROL Start]**&#x200B;按钮以运行数据清理。

##### 监测发生次数 {#calculate-entry-occurrences}

枚举的&#x200B;**[!UICONTROL Alias]**&#x200B;子选项卡可以显示输入的所有值中别名的发生次数。 此信息是估计值，将显示在&#x200B;**[!UICONTROL Hits]**&#x200B;列中。

>[!CAUTION]
>
>计算别名条目发生次数可能需要较长时间。
>

您可以通过&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;链接手动运行点击计算。 为此，请单击&#x200B;**[!UICONTROL Advanced parameters...]**&#x200B;链接并选择选项。

* **[!UICONTROL Update the number of alias hits]**：允许您更新基于输入日期已计算的点击。
* **[!UICONTROL Recalculate the number of alias hits from the start]**：允许您在整个Adobe Campaign平台上运行计算。

您还可以创建一个专用工作流，以便计算在给定时间段自动运行，例如每周运行一次。

为此，请创建&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;工作流的副本，更改调度程序并在&#x200B;**[!UICONTROL Enumeration value cleansing]**&#x200B;活动中使用以下设置：

* **-updateHits**&#x200B;以更新别名点击数，
* **-updateHits：full**&#x200B;以重新计算所有别名点击。
