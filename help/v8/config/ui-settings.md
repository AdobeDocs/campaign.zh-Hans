---
title: Campaign界面设置
description: 了解如何自定义Campaign界面设置
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 5251885f0493eb41f93d07f0e22dcf77926e69dd
workflow-type: tm+mt
source-wordcount: '1845'
ht-degree: 23%

---

# Campaign用户界面设置 {#ui-settings}

## 默认单位 {#default-units}

在Adobe Campaign中，对于表示持续时间的字段（例如，资源的有效期、任务的批准截止时间等），值可以用以下方式表示 **单位**:

* **[!UICONTROL s]** 表示秒
* **[!UICONTROL mn]** 分钟
* **[!UICONTROL h]** 表示小时
* **[!UICONTROL d]** 表示天

## 自定义Campaign Explorer{#customize-explorer}

您可以向Campaign Explorer添加文件夹、创建视图和分配权限。

了解如何在 [本页](../audiences/folders-and-views.md)

## 管理和自定义列表{#customize-lists}

在Campaign客户端控制台中，数据显示在列表中。 您可以根据自己的需要调整这些列表。 例如，您可以添加列、过滤数据、计数记录、保存和共享设置。

此外，您还可以创建和保存过滤器。  了解有关 [本页](../audiences/create-filters.md).

### 记录数 {#number-of-records}

默认情况下，Adobe Campaign 会加载列表的前 200 条记录。这意味着不一定会显示您所查看的数据库表的所有记录。您可以统计列表中的记录数量并加载更多记录。

在列表屏幕的右下角，**计数器**&#x200B;会显示已加载的记录数，以及数据库中的记录总数（应用任何过滤器之后的记录数）：

![显示列表中的记录总数](assets/number-of-records.png)

如果右侧显示问号而不是数字，例如 `240/?`，单击计数器以启动计算。

要加载和显示其他记录，请单击 **[!UICONTROL Continue loading]**. 默认情况下，将加载200条记录。 要更改要加载的默认记录数，请使用 **[!UICONTROL Configure list]** 图标。 在列表配置窗口中，单击 **[!UICONTROL Advanced parameters]** （左下方）并更改要检索的行数。

要加载所有记录，可右键单击列表，然后选择 **[!UICONTROL Load all]**。

>[!CAUTION]
>
>当列表包含大量记录时，完全加载可能需要一些时间。

### 添加和删除列 {#add-columns}

对于每个列表，内置列配置可适于显示更多信息或隐藏未使用的列。

当数据在记录详细信息中可见时，右键单击该字段并选择 **[!UICONTROL Add in the list]**.

![在列表中添加字段](assets/add-in-the-list.png)

该列会添加到现有列的右侧。

![添加字段列](assets/add-a-column.png)

您还可以使用列表配置屏幕添加和删除列：

1. 在记录列表中，单击 **[!UICONTROL Configure list]** 图标。
1. 双击要在 **[!UICONTROL Available fields]** 列表：它们会添加到 **[!UICONTROL Output columns]** 列表。

   ![列表配置屏幕](assets/list-config-screen.png)


   >[!NOTE]
   >
   >默认不会显示高级字段。要显示它们，请单击 **显示高级字段** 图标。
   >
   >通过具体图标标识各字段：SQL 字段、链接的表、已计算字段等。针对选中的每个字段，在可用字段的列表下会显示其说明。

1. 使用向上/向下箭头修改 **显示顺序**.

1. 单击 **[!UICONTROL OK]** 确认配置并显示结果。

如果需要删除某列，请选择该列，然后单击 **垃圾** 图标。

您可以使用 **[!UICONTROL Distribution of values]** 图标，查看当前文件夹中选定字段的值重新分区。

![](assets/value-distribution.png)


### 新建列 {#create-a-new-column}

您可以创建新的列来显示列表中的其他字段。

要创建列，请执行以下步骤：

1. 在记录列表中，单击 **[!UICONTROL Configure list]** 图标。
1. 单击 **[!UICONTROL Add]** 图标以在列表中显示新字段。
1. 配置要在列中添加的字段。


### 在子文件夹中显示数据 {#display-sub-folders-records}

列表可显示：

* 选定文件夹中包含的所有记录（默认）
* 所选文件夹及其子文件夹中包含的所有记录

要从一种显示模式切换到另一种显示模式，请单击 **[!UICONTROL Display sub-levels]** 中。

### 保存列表配置 {#saving-a-list-configuration}

列表配置在本地为每个用户定义。 清空本地缓存时，本地配置被禁用。

默认情况下，设置参数将应用于具有相应文件夹类型的所有列表。 在从文件夹修改收件人列表的显示方式时，此配置将应用于所有其他收件人文件夹。

您可以保存多个配置，以将其应用于同一类型的不同文件夹。 该配置会随包含数据的文件夹的属性一同保存，并可重新应用。

要保存列表配置以便可重复使用，请执行以下步骤：

1. 在资源管理器中，右键单击包含显示数据的文件夹。
1. 选择 **[!UICONTROL Properties]**。
1. 单击 **[!UICONTROL Advanced settings]** 然后在 **[!UICONTROL Configuration]** 字段。
1. 单击 **[!UICONTROL OK]** 然后单击 **[!UICONTROL Save]**.

然后，您可以将此配置应用到任何其他同类型的文件夹。 了解有关 [本页](../audiences/folders-and-views.md).

### 导出列表 {#exporting-a-list}

要从列表中导出数据，必须使用导出向导。要启动此向导，可从列表中选择要导出的元素，右键单击它后选择 **[!UICONTROL Export...]**。

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>不得使用“复制/粘贴”功能从列表中导出元素。

### 对列表排序 {#sorting-a-list}

列表中可包含大量的数据。您可以排序这些数据，或者应用简单或高级过滤器。利用排序，您可以按升序或降序顺序显示数据。您可以利用过滤器来定义并组合各种标准，从而仅显示所选的数据。

单击列标题可应用升序或降序排序，或者取消数据排序。正在使用的排序状态和排序顺序会在列标签前方以蓝色箭头表示。列标签前方的红色破折号表示该排序已应用到数据库中已建立索引的数据。此排序方法用于优化排序作业。

此外也可以配置排序或组合排序标准。为此请执行以下操作步骤：

1. **[!UICONTROL Configure list]** 列表右侧。
1. 在列表配置窗口中，单击 **[!UICONTROL Sorting]** 选项卡。
1. 选择要排序的字段以及排序方向（升序或降序）。
1. 排序优先级通过排序列的顺序来定义。要改变优先级，可使用适当的图标改变各列的顺序。

   排序优先级不会影响列表中各类的显示情况。

1. 单击 **[!UICONTROL Ok]** 确认此配置，并在列表中显示结果。




## 使用枚举 {#enumerations}

明细列表（也称为“明细列表”）是系统建议用于填充字段的值列表。 使用枚举来标准化这些字段的值，帮助进行数据输入或在查询中使用。

值列表将显示为一个下拉列表，您可以从中选择要在字段中输入的值。 下拉列表还支持预测输入：输入前几个字母，应用程序将填写其余字母。

已定义此类型字段的值，并通过 **[!UICONTROL Administration > Platform > Enumerations]** 树的节点。

![访问枚举](assets/enumerations-menu.png)

### 枚举类型 {#types-of-enum}

枚举存储在 **[!UICONTROL Administration > Platform > Enumerations]** 文件夹。

它们可以是：打开、系统、表情符号或关闭。

* 安 **打开** 枚举允许用户根据此枚举直接在字段中添加新值。
* A **已关闭** 枚举具有一个固定的值列表，这些值只能从 **[!UICONTROL Administration > Platform > Enumerations]** 文件夹。
* 安 **表情符号** 枚举用于更新表情符号列表。 了解详情
* A **系统** 枚举与系统字段关联，并且具有内部名称。

对于 **打开** 和 **已关闭** 枚举、特定选项可用：

* **简单枚举** 是默认的标准类型。
* **别名清理** 枚举用于协调存储在数据库中的枚举值。 [了解详情](#alias-cleansing)
* **保留用于绑定** 是用于将多维数据集值链接到此枚举的选项。 [了解详情](../reporting/gs-cubes.md)


### 别名清理 {#alias-cleansing}

在枚举字段中，您可以选择一个值，或输入一个在下拉列表中不可用的自定义值。 可以将自定义值作为新枚举值添加到现有枚举值中，在本例中， **[!UICONTROL Open]** 选项。 可以使用别名清理功能清理这些自定义值。 例如，如果用户输入 `Adob` 而不是 `Adobe`，别名清理过程可以自动用正确的术语替换它。

>[!CAUTION]
>
>数据清理是影响数据库中数据的关键过程。 Adobe Campaign会进行批量数据更新，这可能会导致某些值被删除。 因此，此操作是专家用户专用的。

启用 **[!UICONTROL Alias cleansing]** 选项来对枚举使用数据清理功能。 选择此选项后， **[!UICONTROL Alias]** 选项卡。

当用户输入的值在别名清理枚举中不存在时，该值会添加到 **值** 列表。 您可以 [从这些值创建别名](#convert-to-alias)或 [从头开始创建新别名](#create-alias).

#### 创建别名{#create-alias}

要创建别名，请执行以下步骤：

1. 单击 **[!UICONTROL Add]** 按钮 **[!UICONTROL Alias]** 选项卡。
1. 输入要转换的别名，然后选择要在下拉列表中应用的值。

   ![创建新别名](assets/new-alias.png)

1. 单击 **[!UICONTROL Ok]** 确认。

1. 保存更改。值的替换由 **别名清理** 工作流，每晚执行。 请参阅 [运行数据清理](#running-data-cleansing).

对于基于此枚举的所有字段，当用户输入值时 **Adobe** 在“公司”字段(在Adobe Campaign控制台中，在Web窗体中)中，该字段将自动替换为值 **Adobe**.

#### 将错误值转换为别名{#convert-to-alias}

您还可以将现有枚举值转换为别名。 要执行此操作，请执行以下操作：

1. 在枚举的值列表中，右键单击并浏览 **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![将值转换为别名](assets/convert-into-aliases.png)

1. 选择要以别名转换的值，然后单击 **[!UICONTROL Next]**.
1. 单击 **[!UICONTROL Start]** 以运行转化。

   执行完成后，别名将添加到 **别名** 选项卡。 您可以关联正确的值以替换错误的条目。 要执行此操作，请执行以下操作：

1. 选择要清理的值。
1. 单击 **细节……** 按钮。
1. 在下拉列表中选择新值。

   ![创建新别名](assets/define-new-alias.png)


>[!NOTE]
>
>您可以在 **[!UICONTROL Hits]** 列 **[!UICONTROL Alias]** 子选项卡。 它可显示输入此值的次数。  [了解详情](#calculate-entry-occurrences)。

#### 运行数据清理 {#running-data-cleansing}

数据清理由 **[!UICONTROL Alias cleansing]** 技术工作流。 默认情况下，每天执行一次。

还可以通过 **[!UICONTROL Cleanse values...]** 链接。

的 **[!UICONTROL Advanced parameters...]** 链接允许您设置开始考虑收集值的日期。

单击 **[!UICONTROL Start]** 按钮来运行数据清理。

##### 监控发生次数 {#calculate-entry-occurrences}

的 **[!UICONTROL Alias]** 枚举的子选项卡可显示在输入的所有值中出现别名的次数。 此信息是估计值，将显示在 **[!UICONTROL Hits]** 列。

>[!CAUTION]
>
>计算别名条目发生次数可能需要很长时间。

您可以通过 **[!UICONTROL Cleanse values...]** 链接。 为此，请单击 **[!UICONTROL Advanced parameters...]** 链接并选择选项。

* **[!UICONTROL Update the number of alias hits]**:这允许您根据输入的日期更新已计算的点击量。
* **[!UICONTROL Recalculate the number of alias hits from the start]**:允许您在整个Adobe Campaign平台上运行计算。

您还可以创建专用工作流，以便计算在给定时间段内自动运行，例如每周运行一次。

为此，请创建 **[!UICONTROL Alias cleansing]** 工作流中，更改调度程序，并在 **[!UICONTROL Enumeration value cleansing]** 活动：

* **-updateHits** 要更新别名点击数，
* **-updateHits:full** 重新计算所有别名点击。
