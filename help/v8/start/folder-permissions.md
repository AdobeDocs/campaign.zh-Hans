---
title: 授予和限制对Campaign文件夹的权限
description: 了解如何授予或限制对文件夹的权限
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 18%

---

# 管理文件夹权限{#manage-folder-permissions}

## 限制对文件夹的访问{#restrict-access-to-a-folder}

使用文件夹的权限可组织和控制对Campaign数据的访问。

[此页面](../audiences/folders-and-views.md)中详细介绍了文件夹管理。

要编辑特定Campaign文件夹的权限，请执行以下步骤：

1. 右键单击该文件夹并选择&#x200B;**[!UICONTROL Properties...]**。
1. 浏览到&#x200B;**[!UICONTROL Security]**&#x200B;选项卡以查看此文件夹的授权。

   ![](assets/folder-permissions.png)

* 要&#x200B;**授权组或操作员**，请单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮并选择组或操作员以分配此文件夹的授权。
* 要&#x200B;**禁止组或操作员**，请单击&#x200B;**[!UICONTROL Delete]**&#x200B;并选择组或操作员以删除此文件夹的授权。
* 要&#x200B;**选择分配给某个组或操作员的权限**，请选择该组或操作员，选择要授予的访问权限，然后取消选择其他权限。

>[!NOTE]
>
>如果您对某个对象没有至少一个文件夹的写入权限，就无法创建该对象。
>
>您不需要成为管理员即可创建片段，但您必须对至少一个“内容可视片段”文件夹拥有写入权限。否则，您将无法创建可视片段。

## 传播权限 {#propagate-permissions}

要传播授权和访问权限，请选择文件夹属性中的&#x200B;**[!UICONTROL Propagate]**&#x200B;选项。

此窗口中定义的授权随后将应用于当前节点的所有子文件夹。 您始终可以为每个子文件夹重载这些授权。

>[!NOTE]
>
>取消选中文件夹的&#x200B;**[!UICONTROL Propagate]**&#x200B;选项不会为子文件夹清除它：您必须为每个子文件夹显式清除它。

## 向所有操作员授予访问权限 {#grant-access-to-all-operators}

在&#x200B;**[!UICONTROL Security]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL System folder]**&#x200B;以允许访问所有操作员，无论其权限如何。

如果清除此选项，则必须将运算符（或其组）明确添加回授权列表，以便他们能够访问。
