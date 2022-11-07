---
product: campaign
title: 使用投放模板
description: 了解如何在Campaign中创建和使用投放模板
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
source-git-commit: 822d1bee472330b6195ad9527a7e23e90c7650b4
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 7%

---

# 使用投放模板{#creating-a-delivery-template}

使用投放模板标准化创意外观，以便更快地执行和启动活动。

模板可以系统地包括：

* 类型
* 发件人和回复地址
* 基本的个性化块
* 镜像页面和退订的链接 链接
* 内容、公司徽标或签名
* 其他投放属性，如资源有效性、重试参数或隔离设置。

![](assets/do-not-localize/how-to-video.png) [在视频中发现此功能](#delivery-template-video)

要创建投放模板，您可以复制内置模板、将现有投放转换为模板或从头开始创建投放模板。

## 复制现有模板{#copy-an-existing-template}

Campaign附带适用于每个渠道的一组内置模板：电子邮件、推送、短信、直邮等。

创建投放模板的最简单方法是复制和自定义内置模板。

要复制投放模板，请执行以下步骤：

1. 浏览到 **[!UICONTROL Resources > Templates > Delivery templates]** 在Adobe Campaign资源管理器中。
1. 选择内置投放模板。 内置模板在列表中显示为粗体。
1. 右键单击并选择 **[!UICONTROL Duplicate]**.

   ![](assets/duplicate-built-in-template.png)

1. 定义模板设置并保存新模板。

   ![](assets/delivery-template-new.png)

模板将添加到投放模板列表。 现在，您可以在创建新投放时选择该投放。

![](assets/select-the-new-template.png)

## 将现有投放转换为模板 {#convert-an-existing-delivery}

可以将投放转换为模板，以便执行新的重复投放操作。

要将投放转换为模板，请执行以下步骤：

1. 从投放列表中选择投放，可通过 **[!UICONTROL Campaign management]** Campaign资源管理器的节点。

1. 右键单击并选择 **[!UICONTROL Actions > Save as template...]**.

   ![](assets/save-as-template.png)

1. 编辑投放属性，并选择必须保存新模板的文件夹(位于 **[!UICONTROL Folder]** 字段)，且必须在其中创建基于此模板创建的投放的文件夹(位于 **[!UICONTROL Execution folder]** 字段。

   ![](assets/template-select-folders.png)

## 创建新模板 {#create-a-new-template}

>[!NOTE]
>
>为避免配置错误，Adobe建议您 [复制内置模板](#copy-an-existing-template) 和自定义其属性，而不是创建新模板。

要从头开始配置投放模板，请执行以下步骤：

1. 浏览到 **资源** 文件夹，然后选择 **模板** then **投放模板**.
1. 单击 **新建** ，以创建新投放模板。
1. 设置 **标签** 和 **内部名称** 的子菜单。
1. 保存并重新打开模板。
1. 从 **属性** 按钮，调整设置。
1. 在 **常规** ，确认或更改 **执行文件夹**, **文件夹**&#x200B;和 **路由** 下拉菜单。
1. 完成 **电子邮件参数** 类别。
1. 添加 **HTML内容** 要个性化您的模板，您可以显示镜像页面链接和退订链接。
1. 选择 **预览** 选项卡。 在 **测试个性化** 下拉菜单，选择 **收件人** 以预览模板作为所选配置文件。
1. 单击&#x200B;**保存**。您的模板现已准备就绪，可在投放中使用。


## 从模板创建投放{#create-a-delivery-from-a-template}

要基于现有模板创建投放，请从可用投放模板列表中选择该模板。

![](assets/select-the-new-template.png)

如果看不到模板，请单击 **[!UICONTROL Select link]** 文件夹来浏览Campaign文件夹。

![](assets/browse-templates.png)

从 **[!UICONTROL Folder]** ，或单击 **[!UICONTROL Display sub-levels]** 图标，以在当前目录的子树中显示目录的内容。

选择要使用的投放模板，然后单击 **[!UICONTROL Ok]**.

### 执行模板 {#execute-a-template}

您可以直接从模板列表启动模板的执行，而无需先创建投放。

要执行此操作，请选择要执行的模板并右键单击。 选择 **[!UICONTROL Actions>Execute the delivery template...]**。

您还可以使用 **[!UICONTROL File>Actions>Execute the delivery template...]**.

![](assets/execute-delivery-template.png)

输入投放参数并单击 **[!UICONTROL Send]**.

此操作会在与模板关联的文件夹中生成投放。 此投放的名称是从中创建该投放模板的名称。


## 教程视频 {#delivery-template-video}

### 如何配置投放模板

以下视频演示了如何为临时投放配置模板。

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### 如何设置投放模板属性

以下视频演示了如何设置投放模板属性，并详细说明了每个属性。

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### 如何部署临时投放模板

此视频介绍如何部署临时电子邮件投放模板，并说明电子邮件投放与投放工作流之间的区别。

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

提供了其他Campaign Classic操作方法视频 [此处](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=zh-Hans).
