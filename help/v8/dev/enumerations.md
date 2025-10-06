---
title: 管理枚举
description: 了解如何使用枚举
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: fbde111671fb972f6c96ba45eba4c8a88dbcac64
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 1%

---

# 使用明细列表 {#enumerations}

枚举（也称为明细列表）是预定义的值列表，可用于填写某些字段。 枚举有助于标准化字段值，使数据输入更加一致并简化查询。

如果可用，这些值将显示在下拉列表中。 您可以直接选择一个值或开始键入 — 预测输入会建议匹配值并自动完成它们。

![](assets/enum_values.png)

某些控制台字段配置了枚举。 如果枚举是&#x200B;**open**，则还可以直接在字段中添加新值。

![访问枚举](assets/enumerations-menu.png)

## 枚举类型 {#types-of-enum}

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


## 别名清理 {#alias-cleansing}

在枚举字段中，您可以选择值，或输入在下拉列表中不可用的自定义值。 可以将自定义值作为新值添加到现有枚举值中 — 在这种情况下，必须选择&#x200B;**[!UICONTROL Open]**&#x200B;选项。 可以使用别名清理功能清理这些自定义值。 例如，如果用户输入`Adob`而不是`Adobe`，则别名清理过程可以自动用正确的术语替换它。

>[!CAUTION]
>
>数据清理是影响数据库中数据的关键过程。 Adobe Campaign会执行批量数据更新，这可能会导致某些值被删除。 因此，此操作是为专家用户保留的。

启用&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;选项以使用枚举的数据清理功能。 选择此选项时，**[!UICONTROL Alias]**&#x200B;选项卡将显示在窗口的底部。

当用户输入的值在Alias清理枚举中不存在时，该值会被添加到&#x200B;**值**&#x200B;列表中。 您可以[根据这些值](#convert-to-alias)创建别名，或[从头开始创建新别名](#create-alias)。

### 创建别名{#create-alias}

要创建别名，请执行以下步骤：

1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;选项卡的&#x200B;**[!UICONTROL Alias]**&#x200B;按钮。
1. 输入要转换的别名，然后在下拉列表中选择要应用的值。

   ![创建新别名](assets/new-alias.png)

1. 单击&#x200B;**[!UICONTROL Ok]**&#x200B;并确认。

1. 保存您的更改。值替换由&#x200B;**别名清理**&#x200B;工作流执行，该工作流每晚执行。 请参阅[运行数据清理](#running-data-cleansing)。

对于基于此枚举的所有字段，当用户在“公司”字段(在Adobe Campaign客户端控制台的Web窗体中)中输入值&#x200B;**Adobe**&#x200B;时，该值将自动被值&#x200B;**Adobe**&#x200B;替换。

### 将错误值转换为别名{#convert-to-alias}

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
>您可以在&#x200B;**[!UICONTROL Hits]**&#x200B;子选项卡的&#x200B;**[!UICONTROL Alias]**&#x200B;列中跟踪别名的发生次数。 它可以显示输入此值的次数。  [了解详情](#calculate-entry-occurrences)。

### 运行数据清理 {#running-data-cleansing}

数据清理由&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;技术工作流执行。 默认情况下，此工作流每日执行。

清理也可以通过&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;链接触发。

通过&#x200B;**[!UICONTROL Advanced parameters...]**&#x200B;链接，可设置考虑收集值的开始日期。

单击&#x200B;**[!UICONTROL Start]**&#x200B;按钮以运行数据清理。

### 监测发生次数 {#calculate-entry-occurrences}

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
* **-updateHits:full**&#x200B;以重新计算所有别名点击。
