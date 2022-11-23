---
title: 授予Campaign v8的权限
description: 了解如何授予Campaign v8的权限
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: ac4d0d0c16f429ca0948a3c3257558c46700baeb
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 7%

---

# 权限入门

在Adobe Campaign中，用户是 **运算符** 和 **运算符组** 表示用户角色。

操作员是具有登录和执行操作权限的Adobe Campaign用户。 默认情况下，运算符存储在 **[!UICONTROL Administration > Access management > Operators]** 节点。

Adobe Campaign附带内置的运算符组，如促销活动管理器或工作流监督者。 所有内置组均列在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}。

作为操作员组的成员，用户具有执行操作（称为“命名权限”）的权限，并有权访问数据，该数据包含在 **资源管理器** 中。 运算符可以是多个运算符组的成员：权限和访问权限是附加的。

命名权限授予以下用户权限：

* 执行操作例如， **分析** 按钮 **投放运算符** 具有 **准备投放** 已命名右侧

* 对文件夹的访问权限操作员组的成员资格可以通过更改文件夹的安全设置，授予或限制对文件夹的访问权限。 [请参阅 Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}以了解详情。例如，它会影响： **写入访问** 创建新实体（如投放、用户档案等）， **读取访问** 使用实体， **删除访问权限** 删除实体。

## 安全区

每个操作员需要链接到区域才能登录到实例，并且操作员IP必须包含在安全区域中定义的地址或地址集中。 安全区域配置在Adobe Campaign服务器的配置文件中执行。

操作员从控制台中的配置文件链接到安全区域，可在 **[!UICONTROL Administration > Access management > Operators]** 节点。

![](../assets/do-not-localize/speech.png)  作为托管Cloud Services用户，Adobe会为您设置安全区。 有关更多信息，请 [联系Adobe](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

**请参阅 Campaign Classic v7 文档**&#x200B;以了解详情

* [内置命名权限](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [内置运算符组](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [设置权限的步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
