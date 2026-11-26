---
title: 使用Campaign和Adobe Experience Manager
description: 了解如何使用Campaign和Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
TQID: 'https://experienceleague.adobe.com/LM635Kjl7bucy1SMcEPuhCElUI7MNrO4B3fwo9fpyFQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: df0d6518-6f49-46e2-b46e-3bcc513f553f
    internal-label: Experience Manager integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 765af3342eb29f27dafa12f72634f5d91361bed5
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 0%
---
# 使用Campaign和Adobe Experience Manager {#ac-aem}

Adobe Campaign与Adobe Experience Manager之间的集成允许您直接在Adobe Experience Manager中管理电子邮件投放的内容以及表单。

## 将Adobe Experience Manager as a Cloud Service与Campaign Web用户界面结合使用 {#aem-cs-web-ui}

借助Campaign Web用户界面，您可以连接Adobe Experience Manager as a Cloud Service环境以集中处理内容。 资产和模板的单一真实来源，可跨渠道保持电子邮件一致性，并避免在两个解决方案之间重复内容。

* **Assets**：在Adobe Experience Manager Assets中管理您的资源并直接在电子邮件内容中重复使用。 [了解详情](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/integrations/aem-assets){target="_blank"}
* **模板**：在Adobe Experience Manager as a Cloud Service中创建和批准电子邮件模板，然后将其用作投放中的内容模板。 [了解详情](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/integrations/aem-content){target="_blank"}

该连接依赖于客户端控制台中配置的&#x200B;**[!UICONTROL AEM]**&#x200B;外部帐户。 查看[外部帐户](../config/external-accounts.md)。

## 在客户端控制台中使用Adobe Experience Manager {#aem-console}

以下部分介绍了Campaign客户端控制台中的集成。

[在本文档中了解有关Adobe Experience Manager的更多信息](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=zh-Hans#aem-and-adobe-campaign-integration-workflow){target="_blank"}。


>[!NOTE]
>
>作为托管云服务用户，[联系Adobe](../start/campaign-faq-comprehensive.md#support)以将Adobe Experience Manager与Campaign集成。

## 从Adobe Experience Manager导入内容 {#integrating-with-aem}

例如，此集成可用于在Adobe Experience Manager中创建新闻稿，然后在Adobe Campaign中将其用作电子邮件营销活动的一部分。

来自Adobe Experience Manager的&#x200B;**：**

1. 导航到您的[!DNL Adobe Experience Manager]创作实例，然后单击页面左上角的Adobe Experience 。 从菜单中选择&#x200B;**[!UICONTROL Sites]**。

   ![突出显示了Sites选项的Adobe Experience Manager导航菜单](assets/aem_authoring_1.png)

1. 访问&#x200B;**[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**。

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;并从下拉菜单中选择&#x200B;**[!UICONTROL Page]**。

   打开“创建”菜单并选择“页面”的![AEM Sites电子邮件文件夹](assets/aem_authoring_2.png)

1. Select **[!UICONTROL Adobe Campaign Email]**&#x200B;模板并命名您的新闻稿。

1. 创建页面后，访问&#x200B;**[!UICONTROL Page information]**&#x200B;菜单并单击&#x200B;**[!UICONTROL Open Properties]**。

   ![打开了“页面信息”菜单并突出显示了“打开属性”的新闻稿页面编辑器](assets/aem_authoring_3.png)

1. 通过添加组件（例如Adobe Campaign中的个性化字段）自定义电子邮件内容。 请参阅[Adobe Experience Manager文档](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=zh-Hans#editing-email-content){target="_blank"}以了解详情。

1. 电子邮件准备就绪后，导航到&#x200B;**[!UICONTROL Page information]**&#x200B;菜单，然后单击&#x200B;**[!UICONTROL Start workflow]**。

   ![打开了“页面信息”菜单并突出显示了“启动工作流”的新闻稿页面编辑器](assets/aem_authoring_4.png)

1. 从第一个下拉列表中，选择&#x200B;**[!UICONTROL Approve Adobe Campaign]**&#x200B;作为工作流模型，然后单击&#x200B;**[!UICONTROL Start workflow]**。

   ![选择“批准Adobe Campaign”作为工作流模型的“启动工作流”对话框](assets/aem_authoring_5.png)

1. 免责声明将显示在页面顶部，声明`This page is subject to the workflow Approve for Adobe Campaign`。 单击免责声明旁边的&#x200B;**[!UICONTROL Complete]**&#x200B;以确认审核，然后单击&#x200B;**[!UICONTROL Ok]**。

1. 再次单击&#x200B;**[!UICONTROL Complete]**&#x200B;并在&#x200B;**[!UICONTROL Next Step]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Newsletter approval]**。

   ![在“下一个”列表和“确定”按钮中选择了新闻稿批准，从而完成工作项目对话框](assets/aem_authoring_6.png)

您的新闻稿现已准备就绪，并已在Adobe Campaign中同步。

来自Adobe Campaign的&#x200B;**：**

1. 在&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Deliveries]**，然后单击&#x200B;**[!UICONTROL Create]**。

1. 从&#x200B;**[!UICONTROL Delivery template]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL Email delivery with AEM content (mailAEMContent)]**&#x200B;模板。

   ![已选择AEM内容(mailAEMContent)的电子邮件投放的营销活动投放模板列表](assets/aem_authoring_7.png)

1. 向投放添加&#x200B;**[!UICONTROL Label]**&#x200B;并单击&#x200B;**[!UICONTROL Continue]**。

1. 单击&#x200B;**[!UICONTROL Synchronize]**&#x200B;以访问您的AEM投放。

   如果您的界面中看不到该按钮，请导航到&#x200B;**[!UICONTROL Properties]**&#x200B;按钮并访问&#x200B;**[!UICONTROL Advanced]**&#x200B;选项卡。 确保&#x200B;**[!UICONTROL Content editing mode]**&#x200B;字段配置为&#x200B;**[!UICONTROL AEM]**，并在&#x200B;**[!UICONTROL AEM account]**&#x200B;字段中输入您的AEM实例详细信息。

   ![突出显示“同步”按钮的Campaign电子邮件投放工具栏](assets/aem_authoring_8.png)

1. Select之前在[!DNL Adobe Experience Manager]中创建的AEM投放，然后单击&#x200B;**[!UICONTROL Ok]**&#x200B;进行确认。

   ![与AEM内容同步对话框列出了已批准的AEM电子邮件，并选择了新闻稿行](assets/aem_authoring_11.png)

1. 请确保在对AEM投放做出修改时单击&#x200B;**[!UICONTROL Refresh content]**&#x200B;按钮。

   ![已同步电子邮件投放，突出显示“刷新内容”按钮和“取消同步”按钮](assets/aem_authoring_12.png)

1. 要删除Experience Manager与Campaign之间的关联，请单击&#x200B;**[!UICONTROL Desynchronize]**。

您的电子邮件现已准备就绪，可发送给受众。

## 从Adobe Experience Manager Assets库导入资源 {#assets-library}

在Adobe Campaign中编辑电子邮件或登陆页面时，您也可以直接从[!DNL Adobe Experience Manager Assets Library]插入资源。 [Adobe Experience Manager Assets文档](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=zh-Hans){target="_blank"}中详细介绍了此功能。

来自Adobe Experience Manager的&#x200B;**：**

1. 导航到您的[!DNL Adobe Experience Manager]创作实例，然后单击页面左上角的Adobe Experience 。 从菜单中选择&#x200B;**[!UICONTROL Assets]** `>` **[!UICONTROL Files]**。

   ![AEM Assets导航菜单，其中的“文件”选项突出显示](assets/aem_assets_1.png)

1. 单击&#x200B;**创建**，然后单击&#x200B;**文件**，将您的资源导入到&#x200B;**Adobe Experience Manager Assets库**。 请参阅[Adobe Experience Manager文档](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=zh-Hans#uploading-assets){target="_blank"}以了解详情。

   打开“创建”菜单并选择“文件”上传资源时，![AEM Assets文件视图](assets/aem_assets_2.png)

1. 根据需要重命名您的资产，然后选择&#x200B;**上传**。

您的资产现已上传到&#x200B;**Adobe Experience Manager Assets库**。

来自Adobe Campaign的&#x200B;**：**

1. 在Adobe Campaign中，通过浏览到&#x200B;**营销活动**&#x200B;选项卡，单击&#x200B;**投放**，然后单击现有投放列表上方的&#x200B;**创建**&#x200B;按钮来创建新投放。

   “营销活动”选项卡上的![营销活动投放列表，其中突出显示“创建”按钮](assets/aem_assets_3.png)

1. Select **投放模板**，然后命名您的投放。

1. 定义消息内容并使其个性化。 [了解详情](../send/email.md)

1. 要使用&#x200B;**Adobe Experience Manager Assets库**，请访问AEM投放的&#x200B;**[!UICONTROL Properties]**，然后选择&#x200B;**[!UICONTROL Advanced]**&#x200B;选项卡。

   选择您的&#x200B;**AEM帐户**&#x200B;并启用&#x200B;**[!UICONTROL Use above AEM instance as shared asset library]**&#x200B;选项。

   ![启用了AEM帐户集和共享资产库选项的投放属性“高级”选项卡](assets/aem_authoring_9.png)

1. 从&#x200B;**图像**&#x200B;图标，访问&#x200B;**[!UICONTROL Select a shared asset]**&#x200B;菜单。

   ![Select的Campaign电子邮件编辑器图像菜单高亮显示共享资源](assets/aem_assets_4.png)

1. 从选择窗口中，从&#x200B;**Adobe Experience Manager Assets库**&#x200B;中选择图像，然后选择&#x200B;**Select**。

   ![Select共享资源窗口，其中列出已选择jogging-newsletter.jpg的AEM Assets库文件](assets/aem_assets_5.png)

您的资产现已上传至您的电子邮件投放。 您现在可以指定目标受众，确认投放，然后继续发送。
