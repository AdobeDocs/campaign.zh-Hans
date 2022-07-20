---
title: 更改数据源
description: 了解有关更改数据源活动的更多信息
feature: Workflows, Data Management, Federated Data Access
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# 更改数据源 {#change-data-source}

使用 **[!UICONTROL Change data source]** 活动来更改 [工作流工作表](use-workflow-data.md#workflow-temporary-work-table). 此活动为跨不同数据源(如联合数据访问(FDA)、Campaign Cloud数据库(FFDA)和Campaign本地数据库)管理数据提供了更大的灵活性。

工作流 **[!UICONTROL Working table]** 用于处理数据并与工作流活动共享数据。

默认情况下， **[!UICONTROL Working table]** 在与要查询的数据源相同的数据库中创建。
例如，在查询 **[!UICONTROL Recipients]** 表，存储在云数据库中，工作流将创建 **[!UICONTROL Working table]** 在同一云数据库上。

使用 **[!UICONTROL Change Data Source]** 活动，以将其他数据源用于 **[!UICONTROL Working table]**.

请注意，在使用 **[!UICONTROL Change Data Source]** 活动时，您需要切换回云数据库以继续执行工作流。

使用 **[!UICONTROL Change Data Source]** 活动时，您必须：

1. 创建工作流.

1. 使用 **[!UICONTROL Query]** 活动。

   有关 **[!UICONTROL Query]** 活动，请参阅此 [页面](query.md#create-a-query).

1. 添加 **[!UICONTROL Change data source]** 活动。

   ![](assets/change-data-source.png)

1. 编辑 **[!UICONTROL Change data source]** 活动 **[!UICONTROL Default data source]**.

   将包含查询结果的工作表移到默认的Campaign本地数据库。

   ![](assets/change-data-source_2.png)

1. 添加 **[!UICONTROL JavaScript code]** 对工作表执行统一操作的活动。

   有关 **[!UICONTROL JavaScript code]** 活动，请参阅 [本页](sql-code-and-javascript-code.md#javascript-code).

1. 添加其他 **[!UICONTROL Change data source]** 活动切换回云数据库。

1. 编辑此活动，然后选择 **[!UICONTROL Active FDA external account]**、和对应的 **[!UICONTROL External database]** 外部帐户。

   ![](assets/change-data-source_3.png)

1. 您现在可以启动工作流。
