---
title: 使用Adobe Campaign在X(Twitter)上发布消息
description: 了解如何使用Adobe Campaign社交营销模块在X(以前称为Twitter)上发布消息并向关注者发送直邮
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 3%

---


# 使用Adobe Campaign在X(Twitter)上发布消息 {#post-tw-messages}

Adobe Campaign附带 **社交媒体营销** 通过X (以前称为Twitter)与客户和潜在客户进行交互的模块。

配置集成后，您可以：

* 向关注者发送私信
* 在您的X帐户上发帖
* 通过恢复用户档案数据来收集新联系人，这使您能够执行定向活动，并在可能的情况下实施跨渠道策略。 此操作需要用户同意。


有关将X帐户与Adobe Campaign集成的配置步骤，请参见 [此页面](../connect/ac-tw.md).

## 创建和发布X帖子 {#publish-on-tw}

请按照以下步骤在X帐户上张贴邮件：

1. 创建X投放

   根据以下内容创建新投放 **[!UICONTROL Tweet (twitter)]** 投放模板。

   ![](assets/tw-new-delivery.png)

1. 选择主目标

   选择要向其发送帖子的帐户。

   ![](assets/tw-define-target.png)

   1. 单击 **[!UICONTROL To]** 链接。
   1. 单击 **[!UICONTROL Add]** 按钮。
   1. 选择 **[!UICONTROL A Twitter account]**。
   1. 在 **[!UICONTROL Folder]** 字段中，选择包含X帐户的服务文件夹。 然后，选择要将您的推文发送到的X帐户。

1. 选择验证目标

   此 **[!UICONTROL Target of the proofs]** 选项卡允许您定义在最终投放之前用于测试投放的X帐户。

   如中所述 [配置步骤](../connect/ac-tw.md#tw-test-account)，则必须创建一个专用于发送校样的专用测试X帐户。

   >[!NOTE]
   >
   >如果您对所有投放使用相同的X测试帐户，则可以将验证目标保存在 **[!UICONTROL Tweet]** 投放模板，可通过访问 **[!UICONTROL Resources > Templates > Delivery templates]** 节点。 默认情况下，每次新投放都将输入验证目标。

1. 定义帖子的内容

   请在以下位置输入帖子内容 **[!UICONTROL Content]** 选项卡。

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >在X上发布时，限制适用：
   >
   >* 消息不能超过140个字符。
   >* 不支持HTML格式。
   >

1. 预览您的帖子

   浏览 **[!UICONTROL Preview]** 制表符，以检查帖子的渲染方式。

   ![](assets/tw-delivery-preview.png)

   1. 单击 **[!UICONTROL Preview]** 选项卡。
   1. 单击 **[!UICONTROL Test personalization]** 下拉菜单并选择 **[!UICONTROL Service]**.
   1. 在 **[!UICONTROL Folder]** 字段中，选择包含您的X帐户的服务文件夹。

1. 发送验证

   在发布推文之前，请确保通过发送出版物的证明来验证推文：然后，您可以在专用X测试页面上获得出版物的精确呈现版本。

1. 发布消息

   1. 内容获得批准后，单击 **[!UICONTROL Send]** 按钮。
   1. 选择 **[!UICONTROL Deliver as soon as possible]** 然后单击 **[!UICONTROL Analyze]** 按钮。
   1. 分析完成后，检查结果。
   1. 单击 **[!UICONTROL Confirm delivery]**，然后单击 **[!UICONTROL Yes]**.

## 向关注者发送私信 {#direct-tw-messages}

此 **[!UICONTROL Synchronize Twitter accounts]** 技术工作流可恢复X关注者的列表，以便您可以向他们发送私信。 [了解详情](../connect/ac-tw.md#synchro-tw-accounts)

要向关注者发送私信，请执行以下步骤：

1. 根据以下内容创建X投放 **[!UICONTROL Tweet (Direct Message)]** 内置投放模板。

1. 选择主目标

   ![](assets/tw-dm-define-target.png)

   1. 选择 **[!UICONTROL To]** 链接和 **[!UICONTROL Add]** 按钮。

   1. 选择定位类型

      * 选择 **[!UICONTROL Twitter subscribers]** 向所有关注者发送一条直接消息。

      * 选择 **[!UICONTROL Filter conditions]** 定义查询并查看其结果。 了解如何在中创建过滤器 [本节](../audiences/create-filters.md#advanced-filters).

1. 从中选择验证目标 **[!UICONTROL Target of the proofs]** 选项卡：此帐户将收到您的私信证明。

   如中所述 [配置步骤](../connect/ac-tw.md#tw-test-account)，则必须创建一个专用于发送校样的专用测试X帐户。


   >[!NOTE]
   >
   >如果您要将所有直接消息校样发送到同一X帐户，可以将校样目标保存在中 **[!UICONTROL Tweet (Direct Message)]** 投放模板，可通过访问 **[!UICONTROL Resources > Templates > Delivery templates]** 节点。

1. 在中输入消息的内容 **[!UICONTROL Content]** 选项卡。

   ![](assets/tw-dm-content.png)

   个性化字段的用法可与电子邮件投放相同，例如，在消息正文中添加关注者的姓名。 可在[此小节](../send/personalize.md)中了解详情。

1. 预览消息

   浏览 **[!UICONTROL Preview]** 制表符，以检查帖子的渲染方式。

   ![](assets/tw-dm-preview.png)

   1. 单击 **[!UICONTROL Preview]** 选项卡。
   1. 单击 **[!UICONTROL Test personalization]** 下拉菜单并选择 **[!UICONTROL Visitor Subscription]**.
   1. 选择要用于测试预览的X帐户。

1. 发送验证

   在发送消息之前，请确保通过以下方式验证消息： [向测试帐户发送验证](../send/preview-and-proof.md)：然后，您可以在私有X帐户上获取消息的精确呈现并检查内容和个性化。

1. 发送私信

   1. 内容获得批准后，单击 **[!UICONTROL Send]** 按钮。
   1. 选择 **[!UICONTROL Deliver as soon as possible]** 然后单击 **[!UICONTROL Analyze]** 按钮。
   1. 分析完成后，检查结果。
   1. 单击 **[!UICONTROL Confirm delivery]**，然后单击 **[!UICONTROL Yes]**.

>[!CAUTION]
>
>您每天发送的私信不能超过250条。 要避免超过此阈值，您可以分批次发送。 有关详细信息，请参见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target="_blank"}.


## 访问跟踪数据 {#tw-tracking}

内置的 **[!UICONTROL Tweet]** 投放模板，默认情况下启用跟踪。

跟踪数据可在投放报表中查看，也可在 **[!UICONTROL Edit > Tracking]** 投放和服务的选项卡。

跟踪配置与电子邮件投放相同。 了解详情，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans){target="_blank"}.

