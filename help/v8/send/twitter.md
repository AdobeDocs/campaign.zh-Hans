---
title: 使用Adobe Campaign在X (Twitter)上发布消息
description: 了解如何使用Adobe Campaign社交营销模块在X（以前称为Twitter）上发布消息并向关注者发送直邮
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 4%

---


# 使用Adobe Campaign在X (Twitter)上发布消息 {#post-tw-messages}

Adobe Campaign附带&#x200B;**社交营销**&#x200B;模块，可让您通过X（以前称为Twitter）与客户和潜在客户进行交互。

配置集成后，您可以：

* 向关注者发送私信
* 在您的X帐户上发帖
* 通过恢复用户档案数据来收集新联系人，这使您能够执行定向活动，并在可能的情况下实施跨渠道策略。 此操作需要用户同意。


[本页](../connect/ac-tw.md)介绍了将X帐户与Adobe Campaign集成的配置步骤。

## 创建和发布X帖子 {#publish-on-tw}

请按照以下步骤在X帐户上张贴邮件：

1. 创建X投放

   基于&#x200B;**[!UICONTROL Tweet (twitter)]**&#x200B;投放模板创建新投放。

   ![](assets/tw-new-delivery.png)

1. 选择主目标

   选择要向其发送帖子的帐户。

   ![](assets/tw-define-target.png)

   1. 单击 **[!UICONTROL To]** 链接。
   1. 单击 **[!UICONTROL Add]** 按钮。
   1. 选择 **[!UICONTROL A Twitter account]**。
   1. 在&#x200B;**[!UICONTROL Folder]**&#x200B;字段中，选择包含X帐户的服务文件夹。 然后，选择要将您的推文发送到的X帐户。

1. 选择验证目标

   **[!UICONTROL Target of the proofs]**&#x200B;选项卡允许您定义在最终投放之前用于测试投放的X帐户。

   正如[配置步骤](../connect/ac-tw.md#tw-test-account)中详述的那样，您必须创建一个专用于发送校样的专用测试X帐户。

   >[!NOTE]
   >
   >如果您对所有投放使用相同的X测试帐户，则可以在&#x200B;**[!UICONTROL Tweet]**&#x200B;投放模板（通过&#x200B;**[!UICONTROL Resources > Templates > Delivery templates]**&#x200B;节点访问）中保存验证目标。 默认情况下，每次新投放都将输入验证目标。

1. 定义帖子的内容

   在&#x200B;**[!UICONTROL Content]**&#x200B;选项卡中输入帖子内容。

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >在X上发布时，限制适用：
   >
   >* 消息不能超过140个字符。
   >* 不支持HTML格式。
   >

1. 预览您的帖子

   浏览&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡以检查帖子的呈现。

   ![](assets/tw-delivery-preview.png)

   1. 单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡。
   1. 单击&#x200B;**[!UICONTROL Test personalization]**&#x200B;下拉菜单并选择&#x200B;**[!UICONTROL Service]**。
   1. 在&#x200B;**[!UICONTROL Folder]**&#x200B;字段中，选择包含您的X帐户的服务文件夹。

1. 发送校样

   在发布推文之前，请确保通过发送出版物的证明来验证推文：然后，您可以在专用X测试页面上获得出版物的精确呈现版本。

1. 发布消息

   1. 内容获得批准后，单击&#x200B;**[!UICONTROL Send]**&#x200B;按钮。
   1. 选择&#x200B;**[!UICONTROL Deliver as soon as possible]**&#x200B;并单击&#x200B;**[!UICONTROL Analyze]**&#x200B;按钮。
   1. 分析完成后，检查结果。
   1. 单击&#x200B;**[!UICONTROL Confirm delivery]**，然后单击&#x200B;**[!UICONTROL Yes]**。

## 向关注者发送私信 {#direct-tw-messages}

**[!UICONTROL Synchronize Twitter accounts]**&#x200B;技术工作流可恢复X关注者的列表，以便您可以向他们发送私信。 [了解详情](../connect/ac-tw.md#synchro-tw-accounts)

要向关注者发送私信，请执行以下步骤：

1. 根据&#x200B;**[!UICONTROL Tweet (Direct Message)]**&#x200B;内置投放模板创建X投放。

1. 选择主目标

   ![](assets/tw-dm-define-target.png)

   1. 选择&#x200B;**[!UICONTROL To]**&#x200B;链接和&#x200B;**[!UICONTROL Add]**&#x200B;按钮。

   1. 选择定位类型

      * 选择&#x200B;**[!UICONTROL Twitter subscribers]**&#x200B;向所有关注者发送私信。

      * 选择&#x200B;**[!UICONTROL Filter conditions]**&#x200B;以定义查询并查看其结果。 在[本节](../audiences/create-filters.md#advanced-filters)中了解如何创建筛选器。

1. 从&#x200B;**[!UICONTROL Target of the proofs]**&#x200B;选项卡中选择验证目标：此帐户将收到您的私信的验证。

   正如[配置步骤](../connect/ac-tw.md#tw-test-account)中详述的那样，您必须创建一个专用于发送校样的专用测试X帐户。


   >[!NOTE]
   >
   >如果要将所有直接消息校对发送到同一X帐户，可以将校对目标保存在&#x200B;**[!UICONTROL Tweet (Direct Message)]**&#x200B;投放模板中，可通过&#x200B;**[!UICONTROL Resources > Templates > Delivery templates]**&#x200B;节点访问。

1. 在&#x200B;**[!UICONTROL Content]**&#x200B;选项卡中输入消息的内容。

   ![](assets/tw-dm-content.png)

   个性化字段的用法可与电子邮件投放相同，例如，在消息正文中添加关注者的姓名。 可在[此部分](../send/personalize.md)中了解详情。

1. 预览消息

   浏览&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡以检查帖子的呈现。

   ![](assets/tw-dm-preview.png)

   1. 单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡。
   1. 单击&#x200B;**[!UICONTROL Test personalization]**&#x200B;下拉菜单并选择&#x200B;**[!UICONTROL Visitor Subscription]**。
   1. 选择要用于测试预览的X帐户。

1. 发送校样

   在发送邮件之前，请确保通过[向测试帐户发送校样来验证邮件](../send/preview-and-proof.md)：然后，你可以在私有X帐户上获得邮件的精确呈现并检查内容和个性化。

1. 发送私信

   1. 内容获得批准后，单击&#x200B;**[!UICONTROL Send]**&#x200B;按钮。
   1. 选择&#x200B;**[!UICONTROL Deliver as soon as possible]**&#x200B;并单击&#x200B;**[!UICONTROL Analyze]**&#x200B;按钮。
   1. 分析完成后，检查结果。
   1. 单击&#x200B;**[!UICONTROL Confirm delivery]**，然后单击&#x200B;**[!UICONTROL Yes]**。

>[!CAUTION]
>
>您每天发送的私信不能超过250条。 要避免超过此阈值，您可以分批次发送。 有关更多信息，请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=zh-Hans#sending-using-multiple-waves){target="_blank"}。


## 访问跟踪数据 {#tw-tracking}

在内置&#x200B;**[!UICONTROL Tweet]**&#x200B;投放模板中，默认情况下启用跟踪。

可在投放报告以及投放和服务的&#x200B;**[!UICONTROL Edit > Tracking]**&#x200B;选项卡中查看跟踪数据。

跟踪配置与电子邮件投放相同。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans){target="_blank"}以了解详情。

