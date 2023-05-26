---
title: 更改数据源
description: 详细了解更改数据源活动
feature: Workflows, Data Management, Federated Data Access
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# 更改数据源 {#change-data-source}

使用 **[!UICONTROL Change data source]** 用于更改数据源的活动 [工作流工作表](use-workflow-data.md#workflow-temporary-work-table). 此活动为跨不同数据源(如联合数据访问(FDA)、Campaign云数据库(FFDA)和Campaign本地数据库)管理数据提供了更大的灵活性。

工作流 **[!UICONTROL Working table]** 用于处理与工作流活动共享数据。

默认情况下， **[!UICONTROL Working table]** 是在与需要查询的数据源相同的数据库中创建的。
例如，在查询 **[!UICONTROL Recipients]** 表，存储在云数据库中，工作流将创建 **[!UICONTROL Working table]** 在同一云数据库上。

使用 **[!UICONTROL Change Data Source]** 活动，以便为使用其他数据源 **[!UICONTROL Working table]**.

请注意，在使用时 **[!UICONTROL Change Data Source]** 活动，您需要切换回云数据库以继续工作流执行。

要使用 **[!UICONTROL Change Data Source]** 活动，您必须：

1. 创建工作流.

1. 使用查询定向收件人 **[!UICONTROL Query]** 活动。

   欲知关于 **[!UICONTROL Query]** 活动，请参阅此 [页面](query.md#create-a-query).

1. 添加 **[!UICONTROL Change data source]** 活动。

   ![](assets/change-data-source.png)

1. 编辑您的 **[!UICONTROL Change data source]** 要选择的活动 **[!UICONTROL Default data source]**.

   随后会将包含查询结果的工作表移动到默认的Campaign Local数据库。

   ![](assets/change-data-source_2.png)

1. 添加 **[!UICONTROL JavaScript code]** 对工作表执行单一操作的活动。

   欲知关于 **[!UICONTROL JavaScript code]** 活动，请参阅 [此页面](sql-code-and-javascript-code.md#javascript-code).

1. 添加另一个 **[!UICONTROL Change data source]** 活动以切换回云数据库。

1. 编辑此活动并选择 **[!UICONTROL Active FDA external account]**，以及相应的 **[!UICONTROL External database]** 外部帐户。

   ![](assets/change-data-source_3.png)

1. 您现在可以启动工作流。
