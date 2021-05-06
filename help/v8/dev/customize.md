---
solution: Campaign Classic
product: campaign
title: 自定义实例
description: 了解如何自定义实例
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
translation-type: tm+mt
source-git-commit: 805deadf994e2c4fdfb850ea5b1c3dedf565ef2d
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 0%

---

# 自定义实例{#gs-ac-custom}

了解如何&#x200B;**自定义活动实例**

>[!CAUTION]
>
>Adobe Campaign自定义仅保留给专家用户。

## 创建新数据字段和模式

Adobe Campaign使用数据模式来：

* 定义应用程序中数据对象与基础数据库表的绑定方式
* 定义活动应用程序中不同数据对象之间的链接
* 定义和描述每个对象中包含的各个字段

可以向现有表(如收件人表(nms:收件人))添加字段，您必须扩展该模式。

有两种表扩展模式可用：

* 通过接口，使用&#x200B;**New field** assistant

   :arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)中快速在活动中添加新字段

* 以编程方式，通过扩展模式

   ：灯泡：了解如何扩展[本节](../dev/extend-schema.md)中的现有模式。


您可以在活动数据库中创建新表并扩展内置的数据模型。

要添加Adobe Campaign中不存在的现成数据（例如合同表）的全新类型，您可以直接创建自定义模式。 有关此问题的详细信息，请参阅[此示例](../dev/create-schema.md#example--creating-a-contract-table)。

**相关主题**

:arrow_upper_right:[模式文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)中的Campaign Classic版示例

:arrow_upper_right:用例：将字段链接到[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)中的现有引用表


## 修改输入表单

活动输入表单可以调整为适合您的实现。 您可以通过修改XML内容来添加或删除字段。

：灯泡：了解如何修改现有输入表单或在[本节](../dev/forms.md)中创建新表单。

## 自定义仪表板{#gs-custom-dashboards}

Adobe Campaign界面使用许多Web 应用程序来访问、管理收件人、投放、活动、股票等，并与之交互。 在界面中，它们以仪表板形式显示，只有一页。

现成的Web 应用程序存储在“管理”>“配置”>“Web 应用程序”节点中。

:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)中的活动中创建概述页面


## 自定义列表并创建过滤器{#gs-lists-and-filters}

### 访问仪表板

活动列表附带预定义过滤器以促进导航和数据可视化。

:arrow_upper_right:了解有关[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)中筛选选项的更多信息


### 从资源管理器访问数据

在Adobe Campaign资源管理器树中导航时，数据库中包含的数据将以列表显示。 您可以过滤这些列表、运行搜索、添加信息、过滤和排序数据。

:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)中配置列表并保存列表配置


您可以对这些列表应用过滤器，以仅显示操作员需要的数据。 然后，可以对过滤的数据执行操作。 过滤器配置允许您动态地从列表中选择数据。 如果修改了数据，则更新筛选的数据。

:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)中筛选数据
