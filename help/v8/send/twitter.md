---
title: 使用Adobe Campaign在Twitter上发布消息
description: 了解如何使用Adobe Campaign Social Marketing模块在Twitter上发布消息并收集联系数据
role: Data Engineer
level: Beginner
hidefromtoc: true
hide: true
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: da6e585a789749ae0302f048940d104a36e2b477
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 8%

---


# 使用Adobe Campaign在Twitter上发布消息 {#post-tw-messages}

Adobe Campaign **社交营销** 模块，让您可以通过Twitter与客户和潜在客户进行交互。

配置集成后，您可以：

* 在Twitter上发送消息：Adobe Campaign允许您将消息直接发布到twitter帐户。 您还可以向所有关注者发送私信。
* 收集新联系人：Adobe Campaign可以自动恢复用户档案数据，以便执行定位营销活动，并在可能时实施跨渠道策略。 此操作需要用户同意。


有关将Twitter帐户与Adobe Campaign集成的配置步骤，请参阅 [本页](../connect/ac-tw.md).

## 创建和发布Twitter帖子 {#publish-on-tw}

请按照以下步骤在您的Twitter帐户上发布消息：

1. 创建Twitter投放

   根据 **[!UICONTROL Tweet (twitter)]** 投放模板。

1. 选择主目标

   选择要将推文发送到的帐户。

   1. 单击 **[!UICONTROL To]** 链接。
   1. 单击 **[!UICONTROL Add]** 按钮。
   1. 选择 **[!UICONTROL A Twitter account]**。
   1. 在 **[!UICONTROL Folder]** 字段中，选择包含Twitter帐户的服务文件夹。 然后，选择要将推文发送到的Twitter帐户。

1. 选择校样目标

   的 **[!UICONTROL Target of the proofs]** 选项卡，可让您定义在最终投放之前用于测试投放的Twitter帐户。

   如 [配置步骤](../connect/ac-tw.md#tw-test-account)，则必须创建专用于发送校样的Twitter帐户。

   >[!NOTE]
   >
   >如果您对所有投放使用相同的Twitter测试帐户，则可以在 **[!UICONTROL Tweet]** 投放模板，通过 **[!UICONTROL Resources > Templates > Delivery templates]** 节点。 然后，将默认为每个新投放输入校样目标。

1. 定义帖子的内容

   在 **[!UICONTROL Content]** 选项卡。

   >[!CAUTION]
   >
   >在Twitter上发帖时，有以下限制：
   >
   >* 消息长度不能超过140个字符。
   >* HTML格式不受支持。


1. 预览帖子

   浏览 **[!UICONTROL Preview]** 选项卡来检查帖子的呈现。

   1. 单击 **[!UICONTROL Preview]** 选项卡。
   1. 单击 **[!UICONTROL Test personalization]** 下拉菜单，然后选择 **[!UICONTROL Service]**.
   1. 在 **[!UICONTROL Folder]** 字段中，选择包含您的Twitter帐户的服务文件夹。
   1. 选择要用于测试预览的Twitter帐户。

1. 发送验证

   在发布推文之前，请确保通过发送发布证明来验证推文：然后，您可以在专用Twitter测试页面上获取发布的确切呈现。

   有关创建专用Twitter帐户的更多信息，请参阅 [此部分](../connect/ac-tw.md#tw-test-account).

   ![](../assets/do-not-localize/book.png) [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hans){target=&quot;_blank&quot;}

1. 发布消息

   1. 内容获得批准后，单击 **[!UICONTROL Send]** 按钮。
   1. 选择 **[!UICONTROL Deliver as soon as possible]** ，然后单击 **[!UICONTROL Analyze]** 按钮。
   1. 分析完成后，检查结果。
   1. 单击 **[!UICONTROL Confirm delivery]**，然后单击 **[!UICONTROL Yes]**.


## 向关注者发送私信 {#direct-tw-messages}

的 **[!UICONTROL Synchronize Twitter accounts]** 技术工作流取回了Twitter关注者列表，以便您能够向他们发送私信。 [了解详情](../connect/ac-tw.md#synchro-tw-accounts)

要向关注者发送私信，请执行以下步骤：

1. 根据 **[!UICONTROL Tweet (Direct Message)]** 内置投放模板。

1. 选择主目标

1. 选择 **[!UICONTROL To]** 链接和 **[!UICONTROL Add]** 按钮。

1. 选择定位类型

   * 选择 **[!UICONTROL Twitter subscribers]** 向所有关注者发送私信。

   * 选择 **[!UICONTROL Filter conditions]** 定义查询并查看其结果。 此选项与电子邮件投放的选项相同。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/creating-queries/defining-filter-conditions.html){target=&quot;_blank&quot;}以了解详情。

1. 从 **[!UICONTROL Target of the proofs]** 选项卡上，选择将收到您私信校样的关注者。

   >[!NOTE]
   >
   >如果要将所有直接消息校样发送到同一Twitter关注者，可以在 **[!UICONTROL Tweet (Direct Message)]** 投放模板，通过 **[!UICONTROL Resources > Templates > Delivery templates]** 节点。

1. 在 **[!UICONTROL Content]** 选项卡。

   个性化字段的使用方式与电子邮件投放相同，例如，在消息正文中添加关注者的名称。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/about-personalization.html){target=&quot;_blank&quot;}以了解详情。

1. 预览消息

   浏览 **[!UICONTROL Preview]** 选项卡来检查帖子的呈现。

   1. 单击 **[!UICONTROL Preview]** 选项卡。
   1. 单击 **[!UICONTROL Test personalization]** 下拉菜单，然后选择 **[!UICONTROL Service]**.
   1. 在 **[!UICONTROL Folder]** 字段中，选择包含您的Twitter帐户的服务文件夹。
   1. 选择要用于测试预览的Twitter帐户。

1. 发送验证

   在发送消息之前，请确保通过向测试帐户发送校样来验证消息：然后，您可以在专用Twitter帐户上获取消息的精确渲染，并检查内容和个性化。

   有关创建专用Twitter帐户的更多信息，请参阅 [此部分](../connect/ac-tw.md#tw-test-account).

   ![](../assets/do-not-localize/book.png) [了解验证投放的关键步骤](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}

1. 发送私信

   1. 内容获得批准后，单击 **[!UICONTROL Send]** 按钮。
   1. 选择 **[!UICONTROL Deliver as soon as possible]** ，然后单击 **[!UICONTROL Analyze]** 按钮。
   1. 分析完成后，检查结果。
   1. 单击 **[!UICONTROL Confirm delivery]**，然后单击 **[!UICONTROL Yes]**.

>[!CAUTION]
>
>您每天不能发送超过250条私信。 为避免超出此阈值，您可以分批投放。 有关更多信息，请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en#sending-using-multiple-waves)。


## 访问跟踪数据 {#tw-tracking}

内置 **[!UICONTROL Tweet]** 投放模板时，默认情况下会启用跟踪。

可以在投放报表和 **[!UICONTROL Edit > Tracking]** 选项卡。

跟踪配置与电子邮件投放的相同。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans){target=&quot;_blank&quot;}以了解详情。

