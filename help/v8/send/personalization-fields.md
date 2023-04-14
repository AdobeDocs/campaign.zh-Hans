---
title: 添加个性化字段
description: 了解如何在消息内容中插入个性化数据
feature: Personalization
role: User
level: Beginner
exl-id: 14a741dd-794e-4760-bfa3-bafbe993a3f7
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 4%

---

# 添加个性化字段{#personalization-fields}

根据您为每个收件人设置的规则，使用个性化字段以一对一的方式提供个性化内容。

个性化字段是在为特定收件人个性化投放时使用的单个数据字段引用。 在投放分析阶段期间插入实际数据值。

![消息个性化示例](assets/perso-name-sample.png)

## 语法

个性化标记始终使用以下语法： `<%=table.field%>`.

例如，要插入存储在收件人表中的收件人名称，个性化字段会使用 `<%= recipient.lastName %>` 语法。

>[!CAUTION]
>
>个性化字段内容不能超过1024个字符。

## 插入个性化字段 {#insert-a-personalization-field}

要插入个性化字段，请单击可从任何标题、主题或消息正文字段访问的下拉图标。

![插入个性化字段](assets/perso-field-insert.png)

将插入个性化字段，并准备由Adobe Campaign解释：在消息准备期间，这些字段会被替换为给定收件人的值。

![电子邮件中的个性化字段](assets/perso-fields-in-msg.png)

然后，可以在 **[!UICONTROL Preview]** 选项卡。

<!--Learn more about message preview in [this page]().-->

## 用例：个性化电子邮件主题 {#personalization-fields-uc}

在以下用例中，了解如何使用收件人数据个性化电子邮件主题和正文：

1. 创建新投放或打开现有电子邮件投放。
1. 浏览到 **[!UICONTROL Subject]** 链接以编辑消息的主题。
1. 输入“ **特别优惠** ”，然后使用工具栏中的按钮插入个性化字段。 选择 **[!UICONTROL Recipients>Title]**。
1. 重复操作以插入收件人的名称。 在所有个性化字段之间插入空格。
1. 单击 **[!UICONTROL OK]** 验证。
1. 在消息正文中插入个性化。 为此，请单击消息内容中的，然后单击字段插入按钮。
1. 选择 **[!UICONTROL Recipient>Other...]**。
1. 选择要显示的信息字段，然后单击 **[!UICONTROL OK]**.
1. 单击 **[!UICONTROL Preview]** 选项卡来查看个性化结果。 您必须选择一个收件人以显示该收件人的消息。



## 教程视频 {#personalization-field-video}

在以下视频中了解如何向主题行和电子邮件投放的内容添加个性化字段。

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)
