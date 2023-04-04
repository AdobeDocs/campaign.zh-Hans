---
title: 使用个性化块
description: 了解如何在消息内容中使用内置个性化块
feature: Personalization
role: User
level: Beginner
source-git-commit: badcbb83c4bd0cf509c156557f5ea6f7cf7ae771
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 2%

---


# 使用个性化块{#personalization-blocks}

个性化块是动态内容，其中包含可插入投放的特定渲染。 例如，您可以添加徽标、问候语消息或指向镜像页面的链接。

要访问个性化内容块，请浏览到 **[!UICONTROL Resources > Campaign Management > Personalization blocks]** 资源管理器的节点。 中列出了内置个性化块 [此部分](#ootb-personalization-blocks).

您还可以定义新块以优化投放个性化。 [了解详情](#create-custom-personalization-blocks)。

## 插入个性化块 {#insert-personalization-blocks}

要在消息中插入个性化块，请执行以下步骤：

1. 在投放向导的内容编辑器中，单击个性化图标，然后选择 **[!UICONTROL Include]** 菜单。
1. 从列表中选择个性化块，或单击 **[!UICONTROL Other...]** 菜单访问完整列表。

   ![](assets/perso-content-block.png)

1. 然后，个性化块将作为脚本插入。 在生成个性化时，会自动将其调整为收件人用户档案。
1. 浏览到 **[!UICONTROL Preview]** 选项卡，然后选择收件人以查看此块中特定收件人的内容。

您可以在投放内容中包含个性化块的源代码。 要执行此操作，请选择 **[!UICONTROL Include the HTML source code of the block]** 选择它时。

## 内置个性化块 {#ootb-personalization-blocks}

内置个性化块包括：

* **[!UICONTROL Enabled by Adobe Campaign]**:插入“Enabled by Adobe Campaign”徽标。
* **[!UICONTROL Formatting function for proper nouns]**:生成 **[!UICONTROL toSmartCase]** Javascript函数，该函数将每个单词的第一个字母更改为大写。
* **[!UICONTROL Greetings]**:插入带有收件人全名的问候语，后跟逗号。 示例：“你好，无名氏”。
* **[!UICONTROL Insert logo]**:插入在实例设置中定义的徽标。
* **[!UICONTROL Link to mirror page]**:插入指向的链接 [镜像页面](mirror-page.md). 默认格式为：“如果您无法正确查看此消息，请单击此处”。
* **[!UICONTROL Mirror page URL]**:插入镜像页面URL，使交付设计人员能够检查该链接。
* **[!UICONTROL Offer acceptance URL in unitary mode]**:插入一个URL，以便将选件设置为 **[!UICONTROL Accepted]**. （如果启用了交互模块，则此块可用）
* **[!UICONTROL Registration confirmation]**:插入用于确认订阅的链接。
* **[!UICONTROL Registration link]**:插入订阅链接。 此链接在实例设置中定义。 默认内容为：“若要注册，请单击此处。”
* **[!UICONTROL Registration link (with referrer)]**:插入订阅链接，以识别访客和投放。 此链接在实例设置中定义。
* **[!UICONTROL Registration page URL]**:插入订阅URL
* **[!UICONTROL Style of content emails]** 和 **[!UICONTROL Notification style]**:生成使用预定义的HTML样式设置电子邮件格式的代码。
* **[!UICONTROL Unsubscription link]**:插入一个链接，以取消所有投放的订阻止列表阅()。 默认关联内容为：“您收到此邮件是因为您与 ***您的组织名称*** 或关联。 不再从接收消息 ***您的组织名称*** 单击此处。”

## 创建自定义个性化块 {#create-custom-personalization-blocks}

您可以定义要从个性化图标插入的新个性化内容块。

要创建个性化块，请执行以下步骤：

1. 浏览到 **[!UICONTROL Resources > Campaign Management > Personalization blocks]** Campaign资源管理器的文件夹。
1. 在内置块列表的上方，单击 **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. 填写个性化块的设置：

   ![](assets/perso-custom-block.png)

   * 输入块的标签。 此标签显示在个性化字段插入窗口中。
   * 选择 **投放** 内容类型。
   * 启用 **[!UICONTROL Visible in the customization menus]** 用于使此块可从个性化字段插入图标访问的选项。
   * 如有必要，请启用 **[!UICONTROL The content of the personalization block depends upon the format]** 选项，为HTML和文本电子邮件定义两个不同的块。
   * 输入内容(HTML、文本、JavaScript等) ，然后单击 **[!UICONTROL Save]**.

保存后，新的个性化块即可在投放编辑器中使用。

## 教程视频 {#personalization-blocks-video}

通过以下视频了解如何创建动态内容块以及如何使用这些块将电子邮件投放的内容个性化。

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)


