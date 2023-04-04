---
title: 自定义实例
description: 了解如何自定义实例
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 1%

---

# 自定义实例{#gs-ac-custom}

了解如何 **自定义Campaign实例**.

>[!CAUTION]
>
>Adobe Campaign自定义仅保留给专家用户。

## 创建新数据字段和架构

Adobe Campaign利用数据模式：

* 定义应用程序中数据对象如何与基础数据库表绑定
* 在Campaign应用程序中定义不同数据对象之间的链接
* 定义并描述每个对象中包含的各个字段

例如，要向现有表(如收件人表(nms:recipient))添加字段，必须扩展该模式。

提供了两种表扩展模式：

* 通过界面，使用 **新建字段** 助理

   ![](../assets/do-not-localize/book.png) 了解如何在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic){target="_blank"}

* 以编程方式，通过扩展模式

   ![](../assets/do-not-localize/glass.png) 了解如何在 [此部分](../dev/extend-schema.md).


您还可以在Campaign数据库中创建新表并扩展内置数据模型。

要添加Adobe Campaign中不存在的现成数据类型（例如合同表），您可以直接创建自定义架构。 有关更多信息，请参阅 [此示例](../dev/create-schema.md#example--creating-a-contract-table).

**相关主题**

![](../assets/do-not-localize/book.png) 中的模式版本示例 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic){target="_blank"}

![](../assets/do-not-localize/book.png) 用例：将字段链接到 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link){target="_blank"}


## 修改输入表单

营销活动输入表单可以根据您的实施进行调整。 您可以通过修改XML内容来添加或删除表单字段。

![](../assets/do-not-localize/glass.png) 了解如何修改现有输入表单或在 [此部分](../dev/forms.md).

## 自定义功能板{#gs-custom-dashboards}

Adobe Campaign界面使用许多Web应用程序来访问、管理收件人、投放、营销活动、库存等内容并与之进行交互。 在界面中，它们以功能板的形式显示，且仅包含一个页面。

现成的Web应用程序存储在“管理”>“配置”>“Web应用程序”节点中。

![](../assets/do-not-localize/book.png) 了解如何在Campaign中创建概述页面(位于 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application){target="_blank"}


## 自定义列表和创建过滤器 {#gs-lists-and-filters}

### 从功能板访问数据

营销活动列表附带预定义过滤器，以促进导航和数据可视化。

![](../assets/do-not-localize/book.png) 了解有关 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering){target="_blank"}


### 从资源管理器访问数据

在Adobe Campaign Explorer树中导航时，数据库中包含的数据将显示在列表中。 您可以过滤这些列表、运行搜索、添加信息、过滤和排序数据。

![](../assets/do-not-localize/book.png) 了解如何在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started){target="_blank"}


您可以对这些列表应用过滤器，以仅显示运算符所需的数据。 然后，可以对过滤的数据执行操作。 过滤器配置允许您从列表中动态选择数据。 如果数据被修改，则会更新过滤的数据。

![](../assets/do-not-localize/book.png) 了解如何在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters){target="_blank"}
