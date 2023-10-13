---
title: 开始使用用户档案
description: 开始使用用户档案
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 100%

---

# 将数据导入 Campaign {#ootb-profiles}

Campaign 可帮助您将联系人添加到云数据库。您可以加载文件、计划和自动更新多个联系人，在网站上收集数据，或直接在收件人表格中输入用户档案信息。

![](../assets/do-not-localize/glass.png) [受众](audiences.md)入门

![](../assets/do-not-localize/glass.png) 了解 Campaign [数据模型](../dev/datamodel.md)

## 在工作流中导入用户档案

用户档案导入在专用模板中进行配置，通过&#x200B;**导入**&#x200B;活动工作流执行。它们可以根据计划自动重复，例如用于在多个信息系统之间自动交换数据。在[此部分](../../automation/workflow/recurring-import-workflow.md)中了解更多信息。

![](assets/import-wf.png)


## 运行统一导入

创建并执行通用数据导入任务，以便在云数据库中加载联系人。

![](assets/new-import.png)

![](../assets/do-not-localize/book.png)在 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=zh-Hans){target="_blank"}中了解如何运行统一导入任务以馈送到数据库。

## 通过 Web 应用程序收集用户档案

使用 Campaign 创建 Web 窗体，轻松高效地收集和管理用户档案信息。您可以将这些表单共享到您的网站中，这样您的联系人就可以轻松地提供其信息。他们的信息会被发送到 Campaign，用来创建他们的用户档案或更新其信息（如果数据库中已存在这些信息）。

![](assets/web-form-page.png)

![](../assets/do-not-localize/book.png)在 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=zh-Hans){target="_blank"}中了解如何创建 Web 窗体。

**相关主题**

* [创建受众](audiences.md)
* [消除重复用户档案](../../automation/workflow/deduplication-merge.md)
* [丰富用户档案数据](../../automation/workflow/enrich-data.md)
