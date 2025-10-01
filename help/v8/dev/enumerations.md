---
title: 管理枚举
description: 了解如何使用枚举
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 428de72e0459b95a6db0b06ec8541d0475b72fdd
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# 管理枚举 {#manage-enumerations}

枚举（也称为明细列表）是预定义的值列表，可用于填写某些字段。 枚举有助于标准化字段值，使数据输入更加一致并简化查询。

如果可用，这些值将显示在下拉列表中。 您可以直接选择一个值或开始键入 — 预测输入会建议匹配值并自动完成它们。

![](assets/enum_values.png)

某些控制台字段配置了枚举。 如果枚举是&#x200B;**open**，则还可以直接在字段中添加新值。

## 访问枚举

这些字段中使用的值被集中管理。 您可以在&#x200B;**管理** `>` **平台** `>` **枚举**&#x200B;下的Explorer树中添加、编辑、更新或删除它们。

* 上半部分提供了已定义枚举的字段列表。
* 下面的部分列出了可用的值。

当枚举为&#x200B;**[!UICONTROL Open]**&#x200B;时，用户可以直接在用户界面的相应字段中输入新值。

当枚举为&#x200B;**[!UICONTROL Closed]**&#x200B;时，只能从&#x200B;**枚举**&#x200B;菜单添加新值。

## 添加新值

要创建新的枚举值，请单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮。

![](assets/enumeration_screen.png)

输入值的标签。


## 别名清理 {#alias-cleansing}

在枚举字段中，可以输入除枚举值之外的值。 它们可以按原样存储，也可以进行清理。

>[!CAUTION]
>
>数据清理是影响数据库中数据的关键过程。 Adobe Campaign会执行批量数据更新，这可能会导致某些值被删除。 因此，此操作是为专家用户保留的。

然后，输入的值将为：

* 已添加到明细列表值：在这种情况下，必须选择&#x200B;**[!UICONTROL Open]**&#x200B;选项，
* 或自动替换为相应的别名：在这种情况下，必须在明细列表的&#x200B;**[!UICONTROL Alias]**&#x200B;选项卡中定义此用例，
* 或存储在别名列表中：稍后将为其分配别名。

### 创建别名 {#creating-an-alias}

选项&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;允许对选定的明细列表使用别名。 选择此选项时，**[!UICONTROL Alias]**&#x200B;选项卡将显示在窗口的底部。

要创建别名，请执行以下步骤：

1. 浏览到要更新的明细列表，然后单击&#x200B;**[!UICONTROL Add]**。

   ![](assets/enumeration_alias_create.png)

1. 输入要转换的别名以及要应用的值，然后单击&#x200B;**[!UICONTROL Ok]**。

1. 在确认此操作之前，请检查参数。

>[!CAUTION]
>
>确认此步骤后，可能无法恢复先前的值：将替换它们。

因此，当用户在“公司”字段(在Adobe Campaign控制台中或表单中)中输入值&#x200B;**NEILSEN**&#x200B;时，该值将自动被值&#x200B;**NIELSEN Ltd**&#x200B;替换。 值替换由&#x200B;**别名清理**&#x200B;工作流执行。 请参阅[运行数据清理](#running-data-cleansing)。

![](assets/enumeration_alias_use.png)

### 将值转换为别名 {#values-into-aliases}

您可以将现有值转换为别名。 要执行此操作，请执行以下步骤：

1. 右键单击值列表并选择&#x200B;**[!UICONTROL Convert values into aliases...]**。

1. 选择要转换的值，然后单击&#x200B;**[!UICONTROL Next]**。

1. 单击&#x200B;**[!UICONTROL Start]**&#x200B;运行转换。

执行完成后，别名将添加到别名列表中。

### 检索别名点击 {#alias-hits}

当用户输入未包含在枚举中的值时，它们存储在&#x200B;**[!UICONTROL Alias]**&#x200B;选项卡中。

**别名清理**&#x200B;技术工作流每晚恢复这些值以更新枚举。 请参阅[运行数据清理](#running-data-cleansing)

如果需要，**[!UICONTROL Hits]**&#x200B;列可以显示输入此值的次数。 但是，计算此值既费时又费内存。 有关详细信息，请参阅[计算条目发生次数](#calculating-entry-occurrences)。

### 运行数据清理 {#run-data-cleansing}

数据清理由&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;技术工作流执行。 为执行期间应用为枚举定义的配置。 请参阅[别名清理工作流](#alias-cleansing-workflow)。

可通过&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;链接触发清理。

通过&#x200B;**[!UICONTROL Advanced parameters...]**&#x200B;链接，可设置考虑收集值的开始日期。

单击&#x200B;**[!UICONTROL Start]**&#x200B;按钮以运行数据清理。

### 计算条目出现次数 {#entry-occurrences}

明细列表的&#x200B;**[!UICONTROL Alias]**&#x200B;子选项卡可以显示输入的所有值中某个别名的发生次数。 此信息是估计值，将显示在&#x200B;**[!UICONTROL Hits]**&#x200B;列中。

>[!CAUTION]
>
>计算别名条目发生次数可能需要较长时间。 因此，使用此函数时应谨慎。

您可以通过&#x200B;**[!UICONTROL Cleanse values...]**&#x200B;链接手动运行点击计算。 为此，请单击&#x200B;**[!UICONTROL Advanced parameters...]**&#x200B;链接并选择所需的选项。

* **[!UICONTROL Update the number of alias hits]**：允许您更新基于输入日期已计算的点击。
* **[!UICONTROL Recalculate the number of alias hits from the start]**：允许您在整个Adobe Campaign平台上运行计算。

您还可以创建一个专用工作流，以便计算在给定时间段自动运行，例如每周运行一次。

为此，请创建&#x200B;**[!UICONTROL Alias cleansing]**&#x200B;工作流的副本，更改调度程序并在&#x200B;**[!UICONTROL Enumeration value cleansing]**&#x200B;活动中使用以下设置：

* **-updateHits**&#x200B;以更新别名点击数，
* **-updateHits:full**&#x200B;以重新计算所有别名点击。

### 别名清理工作流 {#alias-cleansing-workflow}

**别名清理**&#x200B;工作流运行枚举值清理。 默认情况下，此工作流每日执行。

通过&#x200B;**[!UICONTROL Administration > Production > Technical workflows]**&#x200B;节点访问。


