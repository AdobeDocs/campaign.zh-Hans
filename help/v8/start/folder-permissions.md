---
title: 授予和限制Campaign文件夹的权限
description: 了解如何授予或限制文件夹的权限
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

使用文件夹的权限来组织和控制对Campaign数据的访问。

有关文件夹管理的详细信息，请参阅 [本页](../audiences/folders-and-views.md).

要编辑对特定Campaign文件夹的权限，请执行以下步骤：

1. 右键单击文件夹并选择 **[!UICONTROL Properties...]**.
1. 浏览到 **[!UICONTROL Security]** 选项卡查看此文件夹的授权。

   ![](assets/folder-permissions.png)

* 至 **授权组或运算符**，请单击 **[!UICONTROL Add]** 按钮，然后选择组或运算符以分配此文件夹的权限。
* 至 **禁止组或操作员**，单击 **[!UICONTROL Delete]** 并选择组或运算符以删除此文件夹的授权。
* 至 **选择分配给组或运算符的权限**，选择组或运算符，选择要授予的访问权限，然后取消选择其他权限。

## 传播权限 {#propagate-permissions}

要传播授权和访问权限，请选择 **[!UICONTROL Propagate]** 选项。

然后，此窗口中定义的授权将应用于当前节点的所有子文件夹。 您始终可以为每个子文件夹过载这些授权。

>[!NOTE]
>
>取消选中 **[!UICONTROL Propagate]** 文件夹的选项不会清除子文件夹：必须为每个子文件夹明确清除它。

## 授予对所有运算符的访问权限 {#grant-access-to-all-operators}

在 **[!UICONTROL Security]** 选项卡，选择 **[!UICONTROL System folder]** 以允许访问所有运算符，而不考虑它们的权限。

如果清除此选项，则必须将运算符（或其组）明确地添加回授权列表，以供其访问。
