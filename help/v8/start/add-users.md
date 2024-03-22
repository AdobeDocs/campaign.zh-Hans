---
title: 向Campaign v8授予权限
description: 了解如何向Campaign v8授予权限
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 2%

---

# 权限入门

在Adobe Campaign中，用户是 **运算符** 和 **操作员组** 表示用户角色。

操作员是具有登录和执行操作权限的Adobe Campaign用户。 默认情况下，运算符存储在 **[!UICONTROL Administration > Access management > Operators]** 节点。

Adobe Campaign附带内置操作员组，如活动经理或工作流主管。 要了解有关权限的更多信息，请参阅 [本节](../start/gs-permissions.md)

作为操作员组的成员，用户有权执行称为“已命名权限”的操作，并且有权访问包含在 **资源管理器** 视图。 一个操作员可以是多个操作员组的成员：权限和访问权限是相加的。

已命名权限将权限授予：

* 执行操作例如， **分析** 投放编辑器中的按钮已为成员激活 **投放操作员** 拥有 **准备投放** 已命名权限

* 对文件夹的访问操作员组的成员资格可以通过更改文件夹的安全性设置来授予或限制对文件夹的访问权限。 了解详情，请参阅 [此页面](../start/folder-permissions.md). 例如，它可以影响： **写入权限** 要创建新实体（例如投放、用户档案等），请执行以下操作： **读取权限** 要使用实体，请执行以下操作 **删除访问权限** 以删除实体。

## 安全区域

每个运算符都需要链接到区域才能登录到实例，并且运算符IP必须包含在安全区域中定义的地址或地址集中。 安全区域配置在Adobe Campaign服务器的配置文件中执行。

操作员在控制台中从其配置文件链接到安全区域，可在中访问 **[!UICONTROL Administration > Access management > Operators]** 节点。

>[!NOTE]
>
>作为托管Cloud Service用户，Adobe将为您设置安全区域。 有关详细信息， [联系人Adobe](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**了解详情**

* [内置命名权限](../start/gs-permissions.md)

* [设置权限的步骤](../start/manage-permissions.md)
