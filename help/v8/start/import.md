---
solution: Campaign v8
product: Adobe Campaign
title: 用户档案入门
description: 用户档案入门
feature: 用户档案
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 8%

---

# 将数据导入Campaign {#ootb-profiles}

Campaign可帮助您将联系人添加到云数据库。 您可以加载文件、计划和自动进行多次联系人更新、在Web上收集数据或直接在收件人表中输入用户档案信息。

[!DNL :bulb:] 受众快速入 [](audiences.md)
[!DNL :bulb:] 门了解Campaign数据 [模型](../dev/datamodel.md)

## 在工作流中导入用户档案

配置文件导入在通过工作流通过&#x200B;**Import**&#x200B;活动执行的专用模板中配置。 它们可以根据时间表自动重复，例如用于在多个信息系统之间自动交换数据。在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html)中了解更多信息。

![](assets/import-wf.png)

请参阅Campaign Classicv7文档，以了解更多信息：

[!DNL :arrow_upper_right:] [进出口入门](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html)

[!DNL :arrow_upper_right:] [导入和导出最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html)

[!DNL :arrow_upper_right:] [配置并执行导入](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html)

## 运行统一导入

创建并执行通用数据导入作业，以在云数据库中加载联系人。

![](assets/new-import.png)

[!DNL :arrow_upper_right:] 在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html)中了解如何运行统一导入作业以填充数据库。

## 通过Web应用程序收集用户档案

使用Campaign创建Web窗体，轻松高效地收集和管理用户档案信息。 您可以将这些表单共享到您的网站中，这样您的联系人就可以轻松地提供其信息。 他们的信息会发送到Campaign以创建其用户档案或更新其信息（如果数据库中已存在）。

![](assets/web-form-page.png)

[!DNL :arrow_upper_right:] 了解如何在 [Campaign Classicv7文档中创建Web窗体](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html)。

**相关主题**

* [创建受众](audiences.md)
* [删除重复的用户档案](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html)
* [扩充用户档案数据](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)
