---
title: 在Campaign导入用户档案
description: 了解如何在Campaign中导入联系人
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 15%

---

# 从文件导入用户档案{#create-profiles}

要填充Campaign数据库，您可以 [手动添加用户档案](create-profiles.md) 或导入用户档案，如下所述。 您也可以使用导入的文件来更新联系人数据。

## 用工作流导入用户档案 {#import-profiles-with-a-wf}

工作流可能是自动执行某些导入流程的有用方法。 无论是从本地文件还是从 SFTP 导入数据，都可以使用工作流程来标准化数据管理过程。

### 使用列表中的数据：读取列表 {#data-from-read-list}

在文件中准备和构建数据，以使用工作流导入数据。 [了解详情](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html){target="_blank"}。

### 从文件加载数据 {#data-from-a-file}

可在工作流中处理的数据可从结构化文件中提取，以便将其导入Adobe Campaign。 [了解详情](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html){target="_blank"}。

收集数据后，您可以在工作流中使用该数据，例如，扩充投放或更新数据库。 有关详细信息，请参见 [本节](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html){target="_blank"}.

## 一次性导入{#import-jobs}

Adobe Campaign提供了一般导入功能，例如，可让您提取随后将成为目标群体一部分的客户或潜在客户列表，或向您的数据库提供来自外部文件的数据。

通用导入由管理 **[!UICONTROL Profiles and Targets > Jobs]** Adobe Campaign主页的菜单。

![](assets/new-import-job.png)

有关执行一般导入的详细步骤，请参见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=zh-Hans){target="_blank"}.
