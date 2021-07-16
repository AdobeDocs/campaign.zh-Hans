---
solution: Campaign
product: Adobe Campaign
title: 授予Campaign v8的权限
description: 了解如何授予Campaign v8的权限
feature: 受众
role: Data Engineer
level: Beginner
source-git-commit: a57855556751e85e7a1f7751a103ca157f434a8a
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 5%

---

# 权限入门

在Adobe Campaign中，用户是&#x200B;**运算符**，而&#x200B;**运算符组**&#x200B;表示用户角色。

操作员是具有登录和执行操作权限的Adobe Campaign用户。 默认情况下，运算符存储在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;节点中。

Adobe Campaign附带内置的运算符组，如促销活动管理器或工作流监督者。 所有内置组均列在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}中。

作为运算符组的成员，用户具有执行名为“命名权限”的操作的权限，并有权访问数据，该数据包含在&#x200B;**Explorer**&#x200B;视图的文件夹中。 运算符可以是多个运算符组的成员：权限和访问权限是附加的。

命名权限授予以下用户权限：

* 执行操作
例如，为具有**Prepare Delivery**&#x200B;命名右侧的&#x200B;**Delivery Operator**&#x200B;组成员激活投放编辑器中的&#x200B;**Analyze**&#x200B;按钮

* 访问文件夹
操作员组的成员资格可以通过更改文件夹的安全设置来授予或限制对文件夹的访问权限。 [请参阅 Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}以了解详情。例如，它会影响：**写入访问**&#x200B;以创建新实体（如投放、配置文件等），**读取访问**&#x200B;以使用实体，**删除访问**&#x200B;以删除实体。

## 安全区

每个操作员需要链接到区域才能登录到实例，并且操作员IP必须包含在安全区域中定义的地址或地址集中。 安全区域配置在Adobe Campaign服务器的配置文件中执行。

操作员从控制台中的配置文件链接到安全区域，可在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;节点中访问该安全区域。

??作为托管Cloud Services用户，Adobe会为您设置安全区。 有关详细信息，请[联系Adobe](support.md#support)。

**请参阅 Campaign Classic v7 文档**&#x200B;以了解详情

* [内置命名权限](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [内置运算符组](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [设置权限的步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
