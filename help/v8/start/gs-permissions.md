---
title: Campaign v8中的权限入门
description: 了解在Campaign v8中定义权限的步骤
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 2%

---

# 权限入门{#gs-permissions}

Adobe Campaign允许您定义和管理分配给用户的权限。 这些权限和限制是授权或拒绝的一组权限和限制：

* 访问某些功能
* 访问特定数据
* 访问某些操作（创建、修改、删除）

这些权限通过组合操作员群组权限、命名权限和文件夹权限来定义。

在Adobe Campaign中，用户是 **运算符** 和 **运算符组** 表示用户角色。 操作员是具有登录和执行操作权限的Adobe Campaign用户。 用户是在Admin Console中创建的。 权限适用于用户配置文件或用户组。 您可以授予两种类型的权限：

* 您可以定义属性权限的运算符组，然后将运算符与一个或多个组关联。 这样，您就可以重复使用权限，并使操作员配置文件更加一致。 它还方便了用户配置文件的管理和维护。
* 您可以直接将命名权限分配给用户，在某些情况下，会导致通过组分配的权限过载。

## 授予权限的关键步骤{#key-steps-permissions}

作为产品管理员，您可以向组织的用户授予权限。 权限通过Adobe Admin Console和Campaign客户端控制台授予。 用户使用其Adobe ID登录Adobe Campaign。 了解如何在中连接到Adobe Campaign [本页](connect.md).

关键步骤包括：

* **步骤1**:在Campaign客户端控制台中定义操作员组并为其分配权限。 [了解详情](manage-permissions.md#create-product-profile).
请注意，您还可以使用内置的运算符组从开始。 这些默认群组及其权限列在 [此部分](manage-permissions.md#ootb-productprofiles).
* **步骤2**:在Admin Console中创建与这些组匹配的产品配置文件。 [了解详情](manage-permissions.md#create-product-profile).
您可以从使用内置产品配置文件开始。 [了解详情](manage-permissions.md#ootb-productprofiles)。
* **步骤3**:在Admin Console中创建用户，并将其分配给产品配置文件。 [了解详情](manage-permissions.md#add-users)。
* **步骤4** （可选）：为文件夹分配权限。 [了解详情](manage-permissions.md#ootb-productprofiles)。

## 关于Admin Console{#gs-admin-console}

Adobe Admin Console是管理整个组织中Adobe权限的中心位置。 仅产品管理员可访问此功能。

使用Admin Console可添加用户、创建和分配产品配置文件（即操作员角色组）。

了解如何在 [本页](manage-permissions.md#add-users).

## 关于产品配置文件{#ootb-product-profiles}

产品配置文件是可分配给用户的产品和服务组。 在Adobe Experience Cloud中，权限基于产品的配置文件，而不是用户。 但是，您可以将管理权限委派给特定用户。

在Admin Console中，每个Adobe Experience Cloud **产品配置文件** 对于，促销活动与 **操作员组** 在Campaign客户端控制台中。

了解如何在 [本页](manage-permissions.md#create-a-product-profile).

## 营销活动已命名权限{#named-rights}

作为产品配置文件（即操作员组）的成员，用户具有执行操作（称为“指定权限”）的权限，并具有对数据的读取和/或写入权限。 运算符可以是多个运算符组的成员：权限和访问权限是附加的。

进一步了解中的指定权限 [此部分](manage-permissions.md#use-named-rights).
