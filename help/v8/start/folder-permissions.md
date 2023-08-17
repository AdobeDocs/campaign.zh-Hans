---
title: 授予和限制对Campaign文件夹的权限
description: 了解如何授予或限制对文件夹的权限
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 管理文件夹权限{#manage-folder-permissions}

## 限制对文件夹的访问{#restrict-access-to-a-folder}

使用文件夹的权限可组织和控制对Campaign数据的访问。

有关文件夹管理的详情，请参见 [此页面](../audiences/folders-and-views.md).

要编辑特定Campaign文件夹的权限，请执行以下步骤：

1. 右键单击文件夹，然后选择 **[!UICONTROL Properties...]**.
1. 浏览至 **[!UICONTROL Security]** 选项卡查看此文件夹的授权。

   ![](assets/folder-permissions.png)

* 至 **授权组或操作员**，单击 **[!UICONTROL Add]** 按钮并选择组或运算符以分配此文件夹的授权。
* 至 **禁止组或操作员**，单击 **[!UICONTROL Delete]** 并选择组或操作员以删除此文件夹的授权。
* 至 **选择分配给组或操作员的权限**，选择组或操作员，选择要授予的访问权限，然后取消选择其他权限。

## 传播权限 {#propagate-permissions}

要传播授权和访问权限，请选择 **[!UICONTROL Propagate]** 选项。

此窗口中定义的授权随后将应用于当前节点的所有子文件夹。 您始终可以为每个子文件夹重载这些授权。

>[!NOTE]
>
>取消选中 **[!UICONTROL Propagate]** 文件夹选项不会为子文件夹清除它：您必须为每个子文件夹显式清除它。

## 向所有操作员授予访问权限 {#grant-access-to-all-operators}

在 **[!UICONTROL Security]** 选项卡，选择 **[!UICONTROL System folder]** 允许访问所有操作员，而不管其权限如何。

如果清除此选项，则必须将运算符（或其组）明确添加回授权列表，以便他们能够访问。
