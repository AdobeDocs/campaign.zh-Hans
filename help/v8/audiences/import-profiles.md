---
title: 在Campaign导入用户档案
description: 了解如何在Campaign中导入联系人
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
TQID: 'https://experienceleague.adobe.com/qoVtBCkTTk2DKaR605exVaJvjQ7kjKRoRg-9fJqdoo4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 21%
---
# 从文件导入轮廓{#create-profiles}

要填充Campaign数据库，您可以[手动添加用户档案](create-profiles.md)或导入用户档案，如下所述。 您也可以使用导入的文件来更新联系人数据。

## 用工作流导入轮廓 {#import-profiles-with-a-wf}

工作流可能是自动执行某些导入流程的有用方法。 无论是从本地文件还是从 SFTP 导入数据，都可以使用工作流程来标准化数据管理过程。

### 使用列表中的数据：读取列表 {#data-from-read-list}

在文件中准备和构建数据，以使用工作流导入数据。 [了解详情](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html){target="_blank"}。

### 从文件加载数据 {#data-from-a-file}

可在工作流中处理的数据可从结构化文件中提取，以便将其导入Adobe Campaign。 [了解详情](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html){target="_blank"}。

收集数据后，您可以在工作流中使用该数据，例如，扩充投放或更新数据库。 如需详细信息，请参阅[此小节](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html){target="_blank"}。

## 一次性导入{#import-jobs}

Adobe Campaign提供了一般导入功能，例如，可让您提取随后将成为目标群体一部分的客户或潜在客户列表，或向您的数据库提供来自外部文件的数据。

通用导入通过Adobe Campaign主页的&#x200B;**[!UICONTROL Profiles and Targets > Jobs]**&#x200B;菜单进行管理。

![](assets/new-import-job.png)

[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=zh-Hans){target="_blank"}中详细介绍了执行通用导入的步骤。
