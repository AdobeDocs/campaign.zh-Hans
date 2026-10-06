---
title: 向Campaign v8授予权限
description: 了解如何向Campaign v8授予权限
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%
---
# 权限快速入门

在Adobe Campaign中，用户是&#x200B;**操作员**&#x200B;和&#x200B;**操作员组**&#x200B;代表用户角色。

操作员是具有登录和执行操作权限的Adobe Campaign用户。 默认情况下，运算符存储在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;节点中。

Adobe Campaign附带内置操作员组，如活动经理或工作流主管。 在[本节](../start/gs-permissions.md)中了解有关权限的详细信息

作为操作员组的成员，用户有权执行名为“已命名权限”的操作，并且有权访问&#x200B;**资源管理器**&#x200B;视图的文件夹中所包含的数据。 一个操作员可以是多个操作员组的成员：权限和访问权限是相加的。

已命名权限将权限授予：

* 执行操作
例如，为具有&#x200B;**准备投放**&#x200B;命名权限的&#x200B;**投放操作员**&#x200B;组的成员激活投放编辑器中的&#x200B;**分析**&#x200B;按钮

* 对文件夹的访问权限
操作员组成员资格可以通过更改文件夹的安全性设置来授予或限制对文件夹的访问权限。 请参阅[此页面](../start/folder-permissions.md)以了解详情。 例如，它可以影响：**写访问权限**&#x200B;以创建新实体（例如投放、配置文件等），**读访问权限**&#x200B;以使用实体，**删除访问权限**&#x200B;以删除实体。

## 安全区域

每个运算符都需要链接到区域才能登录到实例，并且运算符IP必须包含在安全区域中定义的地址或地址集中。 安全区域配置在Adobe Campaign服务器的配置文件中执行。

操作员在控制台中从其配置文件链接到安全区域，可在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;节点中访问。

>[!NOTE]
>
>作为托管云服务用户，Adobe会为您设置安全区域。 有关详细信息，[联系Adobe](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}。

**了解详情**

* [内置命名权限](../start/gs-permissions.md)

* [设置权限的步骤](../start/manage-permissions.md)
