---
title: Campaign界面设置
description: 了解如何自定义Campaign界面设置
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 2898fe400e9bf53fc2fe8fde26ccc61ec43bc69e
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 20%

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

## 管理和自定义列表 {#customize-lists}

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


## 其他资源

* **[从Campaign用户界面开始](../start/campaign-ui.md)** — 了解如何访问和浏览Adobe Campaign界面。
* **[使用枚举](../config/enumerations.md)** — 使用预定义的下拉列表标准化字段值，以便更快、更一致地输入数据。
