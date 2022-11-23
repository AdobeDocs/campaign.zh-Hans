---
title: 文件夹和视图
description: 了解如何在Campaign资源管理器中管理文件夹和视图
feature: Audiences, Profiles, Application Settings
role: User
level: Beginner, Intermediate
exl-id: 762dcacc-4aeb-4990-af01-7f793bd69170
source-git-commit: 515520bb5b7131fc2ed2d1b2a843373f01af306a
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# 管理文件夹和视图 {#folders-and-views}

Campaign文件夹是资源管理器树中的节点。 根据数据类型，它们包含某些类型的数据。

视图是一个特定的文件夹，它不包含任何数据，但显示实际存储在同类型其他文件夹中的数据。 例如，如果将投放文件夹转换为视图，则此文件夹将显示所有投放。 然后，可以过滤此数据。


>[!NOTE]
>为了将视图与标准文件夹区分开，其名称以浅蓝色而非黑色显示。

请注意，您可以为文件夹分配权限，以限制对特定数据的访问。 [了解详情](#restrict-access-to-a-folder)

## 使用文件夹时的最佳实践{#best-practices-folders}

* **使用内置文件夹** 以便项目中每个参与人员都能更轻松地使用、维护和排除应用程序故障。 避免为收件人、列表、投放等创建自定义文件夹结构，但应使用标准文件夹，例如 **管理**, **用户档案和目标**, **营销活动管理**.

* **创建子文件夹**&#x200B;例如，将技术工作流保存在内置文件夹下： **[!UICONTROL Administration > Production > Technical Workflows]**，并按工作流类型创建子文件夹。

* **定义和应用命名约定**&#x200B;例如，您可以按字母顺序命名工作流，以便它们按执行顺序显示，例如：

   A1 — 导入收件人，从10:00开始；A2 — 导入票证，于11:00开始。

## 创建文件夹{#create-a-folder}

要创建文件夹，请右键单击现有文件夹，然后使用上下文菜单。

要创建与您选择的文件夹类型相同的文件夹，请在上下文菜单中选择第一个选项。 例如，从“收件人”文件夹中，选择 **[!UICONTROL Create a new 'Recipients' folder]**.

![](assets/create-recipient-folder.png)

您可以拖放新文件夹以根据需要组织Campaign资源管理器树。

要创建其他类型的文件夹，请右键单击现有文件夹，然后选择 **[!UICONTROL Add new folder]**. 您可以根据要存储的数据创建所有类型的文件夹。

![](assets/add-new-folder.png)

>[!CAUTION]
>这些更改适用于所有Campaign用户。

## 将文件夹转换为视图{#turn-a-folder-to-a-view}

视图是一个特定的文件夹，它不包含任何数据，但显示实际存储在同类型其他文件夹中的数据。

您可以将任意文件夹转换为视图，但文件夹必须为空。 将文件夹转换为视图时，存储在文件夹中的任何数据都会被删除。

>[!CAUTION]
>
>视图显示数据并提供对数据的访问，即使数据未实际存储在视图文件夹中。 要访问内容，操作员必须在源文件夹中拥有适当的权限，至少具有读取权限。
>
>要授予对视图的访问权限而不授予对其源文件夹的访问权限，请勿授予对源文件夹父节点的读取权限。

在以下示例中，我们将根据美国投放的内部名称创建一个新文件夹，以仅显示美国投放。

1. 创建 **[!UICONTROL Deliveries]** 文件夹，并将其命名为 **美国投放**.
1. 右键单击此文件夹并选择 **[!UICONTROL Properties...]**.
1. 在 **[!UICONTROL Restriction]** 选项卡中，选择 **[!UICONTROL This folder is a view]**。随后将显示数据库中的所有投放。

   ![](assets/this-folder-is-a-view.png)

1. 从窗口中心部分的查询编辑器中定义筛选条件：文件夹中仅显示与过滤器对应的投放。

   ![](assets/filter-view.png)

   >[!NOTE]
   >
   >了解如何在 [本页](create-filters.md#advanced-filters)


>[!CAUTION]
>
>管理 [事务性消息传递](../send/transactional.md) 事件、 **[!UICONTROL Real time events]** 或 **[!UICONTROL Batch events]** 文件夹不能设置为执行实例上的视图，因为这可能会导致权限问题。

## 组织文件夹{#organize-your-folders}

默认情况下，会在层级的顶部添加新文件夹。

浏览 **子文件夹** 选项卡来组织其子文件夹。

您可以使用右侧的箭头移动文件夹，或选择 **[!UICONTROL Sort the sub-folders in alphabetical order]** 选项来自动排序。

![](assets/sort-folders.png)


## 在文件夹中过滤数据{#filter-data-in-a-folder}

要过滤存储在文件夹中的数据，请访问文件夹属性并选择限制选项卡。

例如，以下文件夹将仅包含具有电子邮件地址且其来源未标记为“外部”或为空的联系人。

![](assets/add-a-filter-to-a-folder.png)


## 限制对文件夹的访问{#restrict-access-to-a-folder}

使用文件夹的权限来组织和控制对Campaign数据的访问。 了解有关 [此部分](../start/folder-permissions.md).
