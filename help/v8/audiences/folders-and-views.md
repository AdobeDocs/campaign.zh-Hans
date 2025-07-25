---
title: 文件夹和视图
description: 了解如何在Campaign Explorer中管理文件夹和视图
feature: Audiences, Profiles, Application Settings
role: User
level: Beginner, Intermediate
exl-id: 762dcacc-4aeb-4990-af01-7f793bd69170
version: Campaign v8, Campaign Classic v7
source-git-commit: 567ca1cd8fa6e4f03c8871488152710753ea02f1
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 1%

---

# 管理文件夹和视图 {#folders-and-views}

Campaign文件夹是资源管理器树中的节点。 它们根据其类型，包含特定类型的数据。

视图是一个特定的文件夹，它不包含任何数据，但显示实际存储在相同类型的其他文件夹中的数据。 例如，如果将投放文件夹转换为视图，则此文件夹将显示所有投放。 然后，可以过滤此数据。


>[!NOTE]
>
>为了将视图与标准文件夹区分开来，其名称以浅蓝色而非黑色显示。

请注意，您可以为文件夹分配权限，以限制对特定数据的访问。 [了解详情](#restrict-access-to-a-folder)

## 使用文件夹时的最佳实践{#best-practices-folders}

* **使用内置文件夹**，使参与项目的每个人更轻松地使用、维护和排除应用程序故障。 避免为收件人、列表、投放等创建自定义文件夹结构，而使用标准文件夹，如&#x200B;**管理**、**配置文件和目标**、**营销活动管理**。

* **创建子文件夹**，例如，将您的技术工作流保存在内置文件夹&#x200B;**[!UICONTROL Administration > Production > Technical Workflows]**&#x200B;下，并根据工作流类型创建子文件夹。

* **定义并应用命名约定**，例如，您可以按字母顺序命名工作流，以便工作流按执行顺序排序，例如：

  A1 — 导入收件人，从10:00开始；
A2 — 导入票证，11:00开始。

## 创建文件夹{#create-a-folder}

要创建文件夹，请右键单击现有文件夹并使用上下文菜单。

要创建与所选文件夹相同的文件夹类型，请选择上下文菜单中的第一个选项。 例如，从“收件人”文件夹中，选择&#x200B;**[!UICONTROL Create a new 'Recipients' folder]**。

![](assets/create-recipient-folder.png)

您可以根据需要拖放新文件夹以整理Campaign资源管理器树。

要创建其他类型的文件夹，请右键单击现有文件夹并选择&#x200B;**[!UICONTROL Add new folder]**。 您可以根据要存储的数据创建所有类型的文件夹。

![](assets/add-new-folder.png)

>[!CAUTION]
>
>这些更改适用于所有Campaign用户。

## 将文件夹转换为视图{#turn-a-folder-to-a-view}

视图是一个特定的文件夹，它不包含任何数据，但显示实际存储在相同类型的其他文件夹中的数据。

您可以将任何文件夹转换为视图，但文件夹必须为空。 在将文件夹转换为视图时，将删除该文件夹中存储的任何数据。

>[!IMPORTANT]
>
>不应将现成文件夹转换为视图。


>[!CAUTION]
>
>视图显示数据并提供对数据的访问，即使数据并未实际存储在视图文件夹中。 要访问内容，操作员必须在源文件夹中具有适当的权限，至少具有读取权限。
>
>要授予对视图的访问权限而不授予对其源文件夹的访问权限，请不要授予对源文件夹的父节点的读取权限。

在下面的示例中，我们将创建一个新文件夹，以根据其内部名称仅显示美国投放。

1. 创建一个&#x200B;**[!UICONTROL Deliveries]**&#x200B;文件夹，并将其命名为&#x200B;**美国投放**。
1. 右键单击此文件夹并选择&#x200B;**[!UICONTROL Properties...]**。
1. 在&#x200B;**[!UICONTROL Restriction]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL This folder is a view]**。 随后将显示数据库中的所有投放。

   ![](assets/this-folder-is-a-view.png)

1. 从窗口中央部分的查询编辑器定义筛选条件：文件夹中仅显示与筛选条件对应的投放。

   ![](assets/filter-view.png)

   >[!NOTE]
   >
   >在[此页面](create-filters.md#advanced-filters)中了解如何设计查询


>[!CAUTION]
>
>管理[事务性消息传递](../send/transactional.md)事件时，**[!UICONTROL Real time events]**&#x200B;或&#x200B;**[!UICONTROL Batch events]**&#x200B;文件夹不能设置为执行实例上的视图，因为这可能导致权限问题。

## 组织您的文件夹{#organize-your-folders}

默认情况下，新文件夹将添加到层次结构的顶部。

浏览文件夹属性的&#x200B;**子文件夹**&#x200B;选项卡以组织其子文件夹。

您可以使用右侧的箭头移动文件夹，或选择&#x200B;**[!UICONTROL Sort the sub-folders in alphabetical order]**&#x200B;选项以自动对它们进行排序。

![](assets/sort-folders.png)


## 过滤文件夹中的数据{#filter-data-in-a-folder}

要过滤存储在文件夹中的数据，请访问文件夹属性并选择限制选项卡。

例如，下面的文件夹将仅包含具有电子邮件地址且其来源未标记为“外部”的联系人 — 或为空。

![](assets/add-a-filter-to-a-folder.png)


## 限制对文件夹的访问{#restrict-access-to-a-folder}

使用文件夹的权限可组织和控制对Campaign数据的访问。 在[本节](../start/folder-permissions.md)中了解有关文件夹权限的详细信息。
