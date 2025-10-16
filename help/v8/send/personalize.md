---
title: 个性化入门
description: 了解如何个性化消息内容
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 48%

---

# 个性化入门 {#personalize-content}

为了充分利用每一个营销活动，Adobe Campaign为您提供了一种方法，可向您提供与客户级别相关的自定义内容。 根据用户档案数据，利用个性化功能为不同的组和个人创建自定义体验：利用您拥有的关于每个特定收件人的数据和信息，您可以根据他们来调整消息。 这可以是他们的名字、兴趣、居住地、购买的内容等等。

Adobe Campaign简化了个性化：您可以使用单个[消息模板](create-templates.md)显示为每个收件人自定义的不同类型的内容。 在事务型消息（如购买确认或购物车放弃电子邮件）中，将每个人的产品列表信息包含在单个电子邮件模板中。


## Personalization策略 {#personalization-strategy}

使用 Campaign 创建动态内容并发送个性化消息。可以结合个性化功能来改进您的消息并创建自定义用户体验。

可以通过以下方式个性化邮件内容：

* 插入动态&#x200B;**个性化字段**

  个性化字段用于邮件的第一级个性化。您可以从个性化编辑器中选择数据库中可用的任何字段。对于投放，您可以选择与收件人、邮件或投放相关的任何字段。可将这些个性化属性插入邮件的主题行或正文中。[了解详情](personalization-fields.md)。

  以下语法可在您的内容中插入收件人的城市：&lt;%= recipient.location.city %>。

* 插入预定义的&#x200B;**内容块**

  Campaign 附带了一组个性化块，其中包含可插入投放中的特定渲染。例如，您可以添加徽标、问候邮件或指向邮件的镜像页面的链接。可以从个性化编辑器的专用条目中获得内容块。[了解详情](personalization-blocks.md)。

* 创建&#x200B;**条件内容**

  例如，配置条件内容以根据收件人的轮廓添加动态个性化内容。满足特定条件时可插入文本块和/或图像。[了解详情](conditions.md)。

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## 护栏和建议{#perso-guardrails}

### Personalization超时 {#perso-timeout}

要改进投放保护，您可以为个性化阶段设置超时期限。

在&#x200B;**[!UICONTROL Delivery]**&#x200B;的&#x200B;**[!UICONTROL Delivery properties]**&#x200B;选项卡中，为&#x200B;**[!UICONTROL Maximum personalization run time]**&#x200B;选项选择最大值（以秒为单位）。

在预览或发送期间，如果个性化阶段超过了您在此字段中设置的最大时间，则流程会中止，并出现错误消息，投放会失败。

默认值为5秒。

如果将此选项设置为0，则个性化阶段将没有时间限制。


### 内部变量{#internal-variables}

以下变量是可用于个性化但不得修改的内部变量：**投放**、**消息**、**数据源**、**targetData**、**提供程序**、**优惠券**、**优惠券值**、**建议**。


## 教程视频 {#personalization-video}

了解不同类型的动态内容，并了解如何创建个性化块和条件语句并将它们应用到投放中。


>[!VIDEO](https://video.tv.adobe.com/v/3452878?captions=chi_hans&quality=12)
