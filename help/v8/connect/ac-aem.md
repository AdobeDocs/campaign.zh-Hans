---
title: 使用Campaign和Adobe Experience Manager
description: 了解如何使用Campaign和Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
source-git-commit: fc461fbbae23925dd29f17c8674cc287ba360147
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 0%

---

# 使用Campaign和Adobe Experience Manager {#ac-aem}

Adobe Campaign与Adobe Experience Manager之间的集成允许您直接在Adobe Experience Manager中管理电子邮件投放的内容以及表单。 您可以选择导入 **Adobe Experience Manager** 将内容导入Campaign或连接 **Adobe Experience Manager即云服务** 帐户，允许您直接在Web界面中编辑内容。

![](../assets/do-not-localize/book.png) [了解如何在Campaign Web界面中将Adobe Experience Manager编辑为Cloud Service内容](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-content.html?lang=en)

![](../assets/do-not-localize/book.png) [在本文档中了解有关Adobe Experience Manager的更多信息](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html#aem-and-adobe-campaign-integration-workflow)

## 从Adobe Experience Manager导入内容 {#integrating-with-aem}

![](../assets/do-not-localize/speech.png)  作为托管Cloud Service用户， [联系人Adobe](../start/campaign-faq.md#support) 将Adobe Experience Manager与Campaign集成。

例如，此集成可用于在Adobe Experience Manager中创建新闻稿，然后在Adobe Campaign中将其用作电子邮件营销活动的一部分。

**从Adobe Experience Manager：**

1. 导航到 [!DNL Adobe Experience Manager] 创作实例，然后单击页面左上角的Adobe体验。 选择 **[!UICONTROL Sites]** 菜单。

   ![](assets/aem_authoring_1.png)

1. 访问 **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. 单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Page]** 下拉菜单中。

   ![](assets/aem_authoring_2.png)

1. 选择 **[!UICONTROL Adobe Campaign Email]** 模板和命名您的新闻稿。

1. 创建页面后，访问 **[!UICONTROL Page information]** 菜单并单击 **[!UICONTROL Open Properties]**.

   ![](assets/aem_authoring_3.png)

1. 通过添加组件(例如Adobe Campaign中的个性化字段)自定义电子邮件内容。 [了解详情](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=en#editing-email-content)

1. 电子邮件准备就绪后，导航到 **[!UICONTROL Page information]** 菜单并单击 **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_4.png)

1. 从第一个下拉菜单中，选择 **[!UICONTROL Approve Adobe Campaign]** 作为工作流模型，然后单击 **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_5.png)

1. 免责声明将显示在页面顶部，声明： `This page is subject to the workflow Approve for Adobe Campaign`. 单击 **[!UICONTROL Complete]** 单击免责声明旁边的，以确认审阅并单击 **[!UICONTROL Ok]**.

1. 单击 **[!UICONTROL Complete]** 再次并选择 **[!UICONTROL Newsletter approval]** 在 **[!UICONTROL Next Step]** 下拉菜单。

   ![](assets/aem_authoring_6.png)

您的新闻稿现已准备就绪，并已在Adobe Campaign中同步。

**从Adobe Campaign：**

1. 从 **[!UICONTROL Campaigns]** 选项卡，单击 **[!UICONTROL Deliveries]** 则 **[!UICONTROL Create]**.

1. 选择 **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** 模板来自 **[!UICONTROL Delivery template]** 下拉菜单。

   ![](assets/aem_authoring_7.png)

1. 添加 **[!UICONTROL Label]** 到您的投放，然后单击 **[!UICONTROL Continue]**.

1. 单击 **[!UICONTROL Synchronize]** 以访问您的AEM投放。

   如果您的界面中看不到该按钮，请导航到 **[!UICONTROL Properties]** 按钮并访问 **[!UICONTROL Advanced]** 选项卡。 确保 **[!UICONTROL Content editing mode]** 字段配置为 **[!UICONTROL AEM]**，并在中输入您的AEM实例详细信息 **[!UICONTROL AEM account]** 字段。

   ![](assets/aem_authoring_8.png)

1. 选择之前在中创建的AEM投放 [!DNL Adobe Experience Manager] 并通过单击确认 **[!UICONTROL Ok]**.

   ![](assets/aem_authoring_11.png)

1. 确保单击 **[!UICONTROL Refresh content]** 每次对AEM投放进行修改时，此按钮都会出现。

   ![](assets/aem_authoring_12.png)

1. 要删除Experience Manager与Campaign之间的关联，请单击 **[!UICONTROL Desynchronize]**.

您的电子邮件现已准备就绪，可发送给受众。

## 从Adobe Experience Manager Assets库导入资源 {#assets-library}

您还可以直接从插入资源 [!DNL Adobe Experience Manager Assets Library] 在Adobe Campaign中编辑电子邮件或登陆页面时。 有关此功能详情，请参阅 [Adobe Experience Manager Assets文档](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=en).

**从Adobe Experience Manager：**

1. 导航到 [!DNL Adobe Experience Manager] 创作实例，然后单击页面左上角的Adobe体验。 选择 **[!UICONTROL Assets]** `>` **[!UICONTROL Files]** 菜单。

   ![](assets/aem_assets_1.png)

1. 单击 **创建** 则 **文件** 要将您的资产导入 **Adobe Experience Manager Assets Library**. [了解详情](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=en#uploading-assets)

   ![](assets/aem_assets_2.png)

1. 根据需要重命名您的资源并选择 **上传**.

您的资产现已上传到 **Adobe Experience Manager Assets Library**.

**从Adobe Campaign：**

1. 在Adobe Campaign中，通过浏览至 **营销活动** 选项卡，单击 **投放** 然后单击 **创建** 按钮来指定现有投放列表的上方。

   ![](assets/aem_assets_3.png)

1. 选择 **投放模板**，然后命名您的投放。

1. 定义消息内容并使其个性化。 [了解详情](../send/email.md)

1. 使用您的 **Adobe Experience Manager Assets library**，访问 **[!UICONTROL Properties]** AEM ，然后选择 **[!UICONTROL Advanced]** 选项卡。

   选择您的 **AEM帐户** 并启用 **[!UICONTROL Use above AEM instance as shared asset library]** 选项。

   ![](assets/aem_authoring_9.png)

1. 从 **图像** 图标，访问 **[!UICONTROL Select a shared asset]** 菜单。

   ![](assets/aem_assets_4.png)

1. 从选择窗口中，从 **Adobe Experience Manager Assets library**，则 **选择**.

   ![](assets/aem_assets_5.png)

您的资产现已上传至您的电子邮件投放。 您现在可以指定目标受众，确认投放，然后继续发送。
