---
title: Campaign v8权限入门
description: 了解在Campaign v8中定义权限的步骤
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 19f85d4e19f756d8a45ce5364dd0601373128f50
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 4%

---

# 权限入门{#gs-permissions}

Adobe Campaign允许您定义和管理分配给用户的权限。 这些权限是一组授权或拒绝的权限和限制：

* 访问特定功能
* 访问特定数据
* Access 对某些操作（创建、修改、删除）

这些权限是通过组合操作员组权限、命名权限和文件夹权限来定义的。

在Adobe Campaign中，用户是&#x200B;**操作员**&#x200B;和&#x200B;**操作员组**&#x200B;代表用户角色。 操作员是具有登录和执行操作权限的Adobe Campaign用户。 用户是在Admin Console中创建的。 这些权限适用于用户配置文件或用户组。 您可以授予两种类型的权限：

* 您可以定义赋予权限的运算符组，然后将运算符与一个或多个组关联。 这使您可以重复使用权限并使操作员配置文件更加一致。 它还有助于用户档案的管理和维护。
* 您可以直接将已命名权限分配给用户，在某些情况下，这会使通过组分配的权限过载。

## 授予权限的关键步骤{#key-steps-permissions}

作为产品管理员，您可以向组织的用户授予权限。 权限是通过Adobe Admin Console和Campaign客户端控制台授予的。 用户使用其Adobe ID登录到Adobe Campaign。 在[此页面](connect.md)中了解如何连接到Adobe Campaign。

关键步骤包括：

* **步骤1**：在Campaign客户端控制台中定义操作员组并为其分配权限。 [了解更多](manage-permissions.md#create-product-profile)。
请注意，您还可以使用内置运算符组作为开头。 这些默认组及其权限在[此部分](manage-permissions.md#ootb-productprofiles)中列出。
* **步骤2**：在Adobe Admin Console中创建与这些组匹配的产品配置文件。 [了解更多](manage-permissions.md#create-product-profile)。
您可以首先使用内置的产品配置文件。 [了解详情](manage-permissions.md#ootb-productprofiles)。
* **步骤3**：在Adobe Admin Console中创建用户，并将其分配给产品配置文件。 [了解详情](manage-permissions.md#add-users)。
* **步骤4**（可选）：分配文件夹权限。 [了解详情](manage-permissions.md#ootb-productprofiles)。

## 关于Admin Console{#gs-admin-console}

Adobe Admin Console是一个中央位置，用于管理整个组织的Adobe授权。 它仅可供产品管理员访问。

使用Admin Console添加用户、创建和分配产品配置文件（操作员角色组）。

了解如何在[此页面](manage-permissions.md#add-users)中添加用户。

## 关于产品配置文件{#ootb-product-profiles}

产品配置文件是可以分配给用户的产品组和服务组。 在Adobe Experience Cloud中，权限基于产品的配置文件，而不是基于用户。 但是，您可以将管理权限委派给特定用户。

在Admin Console中，Campaign的每个Adobe Experience Cloud **产品配置文件**&#x200B;都与Campaign客户端控制台中的&#x200B;**操作员组**&#x200B;相关联。

在[此页面](manage-permissions.md#create-a-product-profile)中了解如何创建和分配产品配置文件。

## 营销活动已命名权限{#named-rights}

作为产品配置文件（即操作员组）的成员，用户有权执行称为“已命名权限”的操作，并具有数据的读取和/或写入权限。 一个操作员可以是多个操作员组的成员：权限和访问权限是相加的。

在[本节](manage-permissions.md#use-named-rights)中了解有关已命名权限的详细信息。
