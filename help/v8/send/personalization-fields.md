---
title: 添加个性化字段
description: 了解如何在消息内容中插入个性化数据
feature: Personalization
role: User
level: Beginner
exl-id: 14a741dd-794e-4760-bfa3-bafbe993a3f7
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 4%

---

# 添加个性化字段{#personalization-fields}

使用个性化字段，根据您为每个收件人设置的规则，一对一地提供个性化内容。

个性化字段是对特定收件人的投放进行个性化时使用的单个数据字段引用。 实际数据值在投放分析阶段插入。

![消息个性化示例](assets/perso-name-sample.png)

## 语法

个性化标记始终使用以下语法： `<%=table.field%>`。

例如，要插入存储在收件人表中的收件人名称，个性化字段使用`<%= recipient.lastName %>`语法。

>[!CAUTION]
>
>个性化字段内容不能超过1024个字符。

## 插入个性化字段 {#insert-a-personalization-field}

要插入个性化字段，请单击可从任何标题、主题或邮件正文字段访问的下拉图标。

![插入个性化字段](assets/perso-field-insert.png)

个性化字段已插入，可由Adobe Campaign解释：在消息准备期间，字段将被替换为给定收件人的值。

电子邮件中的![个性化字段](assets/perso-fields-in-msg.png)

然后，可以在&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡中测试此替换。

<!--Learn more about message preview in [this page]().-->

## 用例：个性化电子邮件主题 {#personalization-fields-uc}

在下面的用例中，了解如何使用收件人数据个性化电子邮件主题和正文：

1. 创建新投放或打开现有的电子邮件投放。
1. 浏览到&#x200B;**[!UICONTROL Subject]**&#x200B;链接以编辑邮件的主题。
1. 输入“**的**&#x200B;特殊优惠”并使用工具栏中的按钮插入个性化字段。 选择 **[!UICONTROL Recipients>Title]**。
1. 重复操作以插入收件人的名称。 在所有个性化字段之间插入空格。
1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;进行验证。
1. 在消息正文中插入个性化设置。 要执行此操作，请单击消息内容，然后单击字段插入按钮。
1. 选择 **[!UICONTROL Recipient>Other...]**。
1. 选择要显示信息的字段，然后单击&#x200B;**[!UICONTROL OK]**。
1. 单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡以查看个性化结果。 您必须选择一个收件人以显示该收件人的消息。



## 教程视频 {#personalization-field-video}

请在以下视频中了解如何将个性化字段添加到主题行以及电子邮件投放的内容。

>[!VIDEO](https://video.tv.adobe.com/v/27467?quality=12&captions=chi_hans)
