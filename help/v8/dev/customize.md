---
title: 自定义实例
description: 了解如何自定义实例
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 1%

---

# 自定义实例 {#gs-ac-custom}

了解如何&#x200B;**自定义您的Campaign实例**。

>[!CAUTION]
>
>Adobe Campaign自定义项仅保留给专家用户。

## 创建新数据字段和架构

Adobe Campaign利用数据架构来：

* 定义应用程序中的数据对象如何与底层数据库表绑定
* 定义Campaign应用程序中不同数据对象之间的链接
* 定义并描述每个对象中包含的各个字段

例如，要向现有表(如收件人表(nms：recipient))添加字段，您必须扩展该模式。

提供了两种表扩展模式：

* 通过接口，使用&#x200B;**新字段**&#x200B;助手

  请参阅[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=zh-Hans#configuring-campaign-classic){target="_blank"}以了解如何在Campaign中快速添加新字段

* 通过扩展模式，以编程方式实现。 在[本节](../dev/extend-schema.md)中了解如何扩展现有架构。

您还可以在Campaign数据库中创建新表并扩展内置数据模型。

要添加在Adobe Campaign中现成不存在的全新类型数据（例如合同表），您可以直接创建自定义架构。 有关详细信息，请参阅[此示例](../dev/create-schema.md#example--creating-a-contract-table)。

**相关主题**

[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=zh-Hans#configuring-campaign-classic){target="_blank"}中的架构版本示例

用例：将字段链接到[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=zh-Hans#uc-link){target="_blank"}中的现有引用表


## 修改输入表单

Campaign输入表单可进行调整以适合您的实施。 您可以通过修改XML内容来添加或删除表单字段。

了解如何在[本节](../dev/forms.md)中修改现有的输入表单或创建新表单。

## 自定义仪表板{#gs-custom-dashboards}

Adobe Campaign界面使用许多Web应用程序来访问、管理收件人、投放、营销活动、库存等，并与之交互。 在界面中，它们以仅包含一个页面的功能板的形式显示。

内置Web应用程序存储在资源管理器的&#x200B;**管理>配置> Web应用程序**&#x200B;文件夹中。

请参阅[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=zh-Hans#creating-a-single-page-web-application){target="_blank"}以了解如何在Campaign中创建概述页面


## 自定义列表和创建过滤器 {#gs-lists-and-filters}

营销活动列表带有预定义过滤器，有助于导航和数据可视化。

在Adobe Campaign资源管理器树中导航时，数据库中包含的数据将显示在列表中。 您可以筛选这些列表、运行搜索、添加信息、筛选和排序数据。

了解如何在[此页面](../start/campaign-ui.md)中配置列表并保存列表配置。

您可以对这些列表应用过滤器，以仅显示运算符所需的数据。 然后，可以对过滤的数据执行操作。 筛选器配置允许您从列表中选择动态数据。 如果修改了数据，则更新过滤的数据。

在[此页面](../audiences/create-filters.md)中了解有关筛选选项的更多信息。
