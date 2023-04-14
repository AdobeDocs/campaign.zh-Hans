---
title: 个性化入门
description: 了解如何个性化邮件内容
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 7%

---

# 个性化入门 {#personalize-content}

为了充分利用每个营销活动，Adobe Campaign为您提供了一种方式，以在客户级别为客户提供自定义内容。 基于用户档案数据，为不同群组和个人创建自定义体验的个性化功能：您可以利用您拥有的关于每个特定收件人的数据和信息，将消息调整为每个特定收件人。 这可以是他们的名字、兴趣、住处、购买的东西等等。

Adobe Campaign简化了个性化：您可以使用单个 [电子邮件模板](create-templates.md). 在事务型消息（如购买确认或购物车放弃电子邮件）中，在单个电子邮件模板中包含每个人的产品清单信息。


## 个性化策略 {#personalization-strategy}

使用Campaign创建动态内容并发送个性化消息。 可以结合个性化功能来改进消息并创建自定义用户体验。

您可以通过以下方式个性化消息内容：

* 插入动态 **个性化字段**

   个性化字段用于消息的一级个性化。 您可以从个性化编辑器中选择数据库中可用的任何字段。 对于投放，您可以选择与收件人、消息或投放相关的任何字段。 这些个性化属性可插入到邮件的主题行或正文中。 [了解详情](personalization-fields.md)。

   以下语法可在内容中插入收件人的城市：&lt;%= recipient.location.city %>。

* 插入预定义 **内容块**

   Campaign附带一组个性化块，其中包含可插入投放的特定渲染。 例如，您可以添加徽标、问候语消息或指向消息镜像页面的链接。 内容块可从个性化编辑器中的专用条目中使用。 [了解详情](personalization-blocks.md)。

* 创建 **条件内容**

   例如，配置条件内容以根据收件人的用户档案添加动态个性化。 当特定条件为true时，会插入文本块和/或图像。 [了解详情](conditions.md)。

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## 护栏和建议{#perso-guardrails}

### 个性化超时{#perso-timeout}

要改进投放保护，您可以为个性化阶段设置超时期限。

在 **[!UICONTROL Delivery]** 选项卡 **[!UICONTROL Delivery properties]**，选择 **[!UICONTROL Maximum personalization run time]** 选项。

在预览或发送期间，如果个性化阶段超过了您在此字段中设置的最长时间，则该过程将中止，并显示一条错误消息，且投放将失败。

默认值为5秒。

如果将此选项设置为0，则个性化阶段将没有时间限制。


### 内部变量{#internal-variables}

以下变量是可用于个性化但不得修改的内部变量： **投放**, **消息**, **dataSource**, **targetData**, **提供程序**, **优惠券**, **couponValue**, **命题**.


## 教程视频 {#personalization-video}

了解不同类型的动态内容，并了解如何创建个性化块和条件语句并将它们应用到投放中。


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
