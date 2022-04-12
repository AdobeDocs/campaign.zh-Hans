---
title: 在Campaign中导入用户档案
description: 了解如何在Campaign中导入联系人
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 9c5c5e825294bd39742ecbd07b98a90b4555c138
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 17%

---

# 从文件导入用户档案{#create-profiles}

要填充Campaign数据库，您可以 [手动添加用户档案](create-profiles.md) 或导入用户档案，详情如下所述。 您还可以使用导入的文件来更新联系人数据。

## 用工作流导入用户档案 {#import-profiles-with-a-wf}

工作流程可以用来自动执行某些导入过程。无论是从本地文件还是从 SFTP 导入数据，都可以使用工作流程来标准化数据管理过程。

### 使用列表中的数据：读取列表 {#data-from-read-list}

在文件中准备和构建数据，以使用工作流导入数据。

有关在工作流中使用读取列表活动的更多信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/read-list.html){target=&quot;_blank&quot;}。

### 从文件加载数据 {#data-from-a-file}

可以在工作流中处理的数据可以从结构化文件中提取，以便将其导入Adobe Campaign。

有关加载数据活动的描述，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/data-loading--file-.html){target=&quot;_blank&quot;}。

收集数据后，您可以在工作流中使用它，例如扩充投放或更新数据库。 有关更多信息，请参阅 [Campaign Classicv7文档]https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/how-to-use-workflow-data.htmll){target=&quot;_blank&quot;}。

## 一次性进口{#import-jobs}

Adobe Campaign提供了通用导入功能，例如，允许您提取随后将成为目标群体一部分的客户或潜在客户列表，或向数据库提供来自外部文件的数据。

从 **[!UICONTROL Profiles and Targets > Jobs]** 菜单。

![](assets/new-import-job.png)

有关执行通用导入的详细步骤，请参见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=zh-Hans){target=&quot;_blank&quot;}。
