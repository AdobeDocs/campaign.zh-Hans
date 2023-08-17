---
title: 使用个性化块
description: 了解如何在消息内容中使用内置个性化块
feature: Personalization
role: User
level: Beginner
exl-id: 214ad693-d456-47ec-a9c8-199ba23c3d9c
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 17%

---

# 使用个性化块{#personalization-blocks}

个性化块是动态内容，其中包含您可以插入到投放中的特定渲染。 例如，您可以添加徽标、问候语消息或指向镜像页面的链接。

要访问个性化的内容块，请浏览 **[!UICONTROL Resources > Campaign Management > Personalization blocks]** 资源管理器节点。 中列出了内置个性化块 [本节](#ootb-personalization-blocks).

您还可以定义新块以优化投放个性化。 [了解详情](#create-custom-personalization-blocks)。

## 插入个性化块 {#insert-personalization-blocks}

要在消息中插入个性化块，请执行以下步骤：

1. 在投放向导的内容编辑器中，单击个性化图标并选择 **[!UICONTROL Include]** 菜单。
1. 从列表中选择个性化块，或单击 **[!UICONTROL Other...]** 菜单以访问完整列表。

   ![](assets/perso-content-block.png)

1. 个性化块随后将作为脚本插入。 当生成个性化时，它自动适应收件人用户档案。
1. 浏览至 **[!UICONTROL Preview]** 选项卡并选择收件人，以查看特定收件人的此块的内容。

您可以在投放内容中包含个性化块的源代码。 要执行此操作，请选择 **[!UICONTROL Include the HTML source code of the block]** 选择时。

## 内置个性化块 {#ootb-personalization-blocks}

内置个性化块包括：

* **[!UICONTROL Enabled by Adobe Campaign]**：插入“由Adobe Campaign启用”徽标。
* **[!UICONTROL Formatting function for proper nouns]**：生成 **[!UICONTROL toSmartCase]** Javascript函数可将每个单词的第一个字母更改为大写。
* **[!UICONTROL Greetings]**：插入问候语，其中显示收件人的全名，后跟逗号。 示例：“Hello John Doe,”。
* **[!UICONTROL Insert logo]**：插入在实例设置中定义的徽标。
* **[!UICONTROL Link to mirror page]**：插入指向以下内容的链接： [镜像页面](mirror-page.md). 默认格式为：“如果您无法正确查看此邮件，请单击此处”。
* **[!UICONTROL Mirror page URL]**：插入镜像页面URL，以便投放设计人员能够检查链接。
* **[!UICONTROL Offer acceptance URL in unitary mode]**：插入用于将选件设置为的URL **[!UICONTROL Accepted]**. （如果启用了交互模块，则此块可用）
* **[!UICONTROL Registration confirmation]**：插入用于确认订阅的链接。
* **[!UICONTROL Registration link]**：插入订阅链接。 在实例设置中定义此链接。默认内容为：“单击此处以注册”。
* **[!UICONTROL Registration link (with referrer)]**：插入订阅链接，用于识别访客和投放。 在实例设置中定义此链接。
* **[!UICONTROL Registration page URL]**：插入订阅URL
* **[!UICONTROL Style of content emails]** 和 **[!UICONTROL Notification style]**：生成代码，该代码使用预定义的HTML样式来格式化电子邮件。
* **[!UICONTROL Unsubscription link]**&#x200B;列入阻止列表 ：插入链接以取消订阅所有投放()。 默认关联内容为：“您之所以收到这封邮件，是因为您一直与&#x200B;***您的组织名称***&#x200B;或关联公司有联系。要不再接收来自&#x200B;***您的组织名称***&#x200B;的邮件，请单击此处。”

## 创建自定义个性化块 {#create-custom-personalization-blocks}

您可以定义要从个性化图标插入的新个性化内容块。

要创建个性化块，请执行以下步骤：

1. 浏览至 **[!UICONTROL Resources > Campaign Management > Personalization blocks]** Campaign资源管理器的文件夹。
1. 在内置块列表上方，单击 **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. 填写个性化块的设置：

   ![](assets/perso-custom-block.png)

   * 输入块的标签。 此标签显示在个性化字段插入窗口中。
   * 选择 **投放** 内容类型。
   * 启用 **[!UICONTROL Visible in the customization menus]** 选项可通过个性化字段插入图标访问此块。
   * 如有必要，请启用 **[!UICONTROL The content of the personalization block depends upon the format]** 选项，为HTML和文本电子邮件定义两个不同的块。
   * 输入内容(HTML、文本、JavaScript等) 的页面名称，然后单击 **[!UICONTROL Save]**.

保存后，投放编辑器中即可使用新的个性化块。

## 教程视频 {#personalization-blocks-video}

请在以下视频中了解如何创建动态内容块以及如何使用动态内容块将电子邮件投放内容个性化。

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)
