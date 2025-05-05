---
title: 条件内容
description: 了解如何创建条件内容
feature: Personalization
role: User
level: Beginner
exl-id: bcbf3101-d43c-4ed3-ab02-a9936ec55b71
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 10%

---

# 创建条件内容{#conditional-content}

通过配置条件内容字段，您可以创建高级个性化。满足特定条件时可替换完整的文本块和/或图像。


## 在电子邮件中使用条件 {#conditions-in-an-email}

在以下示例中，了解如何创建消息，并根据收件人的城市和兴趣动态进行个性化。

* 根据收件人的城市更改邮件，
* 根据收件人的兴趣将优惠内容个性化。

要根据字段值创建条件内容，请应用以下步骤：

1. 打开现有投放或创建新电子邮件投放。
1. 在电子邮件内容编辑器中，单击个性化图标并选择&#x200B;**[!UICONTROL Conditional content > If]**。

   ![插入条件](assets/condition-insert.png)

   个性化元素将插入到消息正文中。 您现在必须配置它们。

1. 填写&#x200B;**if**&#x200B;表达式的参数。

   * 选择表达式的第一个元素&#x200B;**`<FIELD>`**，然后单击个性化图标以将其替换为测试字段。
   * 将&#x200B;**`<VALUE>`**&#x200B;替换为将满足条件的字段的值。 此值必须在引号中。
   * 指定满足条件时要插入的内容。 这可以是文本、图像、表单、超文本链接等。

   电子邮件中的![条件](assets/condition-in-email.png)

1. 单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡以根据投放收件人查看消息的内容。 选择条件为true的收件人以检查内容。 然后选择另一个为false的收件人，并再次检查。

您可以添加其他案例，并根据一个或多个字段的值定义不同的内容。 为此，请使用&#x200B;**[!UICONTROL Conditional content > Else]**&#x200B;和&#x200B;**[!UICONTROL Conditional content > Else if]**。 这些表达式的配置方式与&#x200B;**if**&#x200B;表达式相同。

>[!CAUTION]
>
>添加&#x200B;**Else**&#x200B;和&#x200B;**Else if**&#x200B;条件后，必须删除&#x200B;**%> &lt;%**&#x200B;字符。


## 用例：创建多语言电子邮件 {#creating-multilingual-email}

在以下示例中，了解如何创建多语言电子邮件。 根据收件人的首选语言，内容将以一种或另一种语言显示。

1. 创建电子邮件并选择目标群体。 在此示例中，显示一个版本或另一个版本的条件将基于收件人配置文件的&#x200B;**语言**&#x200B;值。 这些值设置为&#x200B;**EN**、**FR**、**ES**。
1. 在电子邮件HTML内容中，单击&#x200B;**[!UICONTROL Source]**&#x200B;选项卡并粘贴以下代码：

   ```
   <% if (language == "EN" ) { %>
   <DIV id=en-version>Hello <%= recipient.firstName %>,</DIV>
   <DIV>Discover your new offers!</DIV>
   <DIV><a href="https://www.adobe.com/products/en">www.adobe.com/products/en</A></FONT></DIV><%
    } %>
   <% if (language == "FR" ) { %>
   <DIV id=fr-version>Bonjour <%= recipient.firstName %>,</DIV>
   <DIV>Découvrez nos nouvelles offres !</DIV>
   <DIV><a href="https://www.adobe.com/products/fr">www.adobe.com/products/fr</A></DIV><%
    } %>
    <% if (language == "ES" ) { %>
   <DIV id=es-version><FONT face=Arial>
   <DIV>Olà <%= recipient.firstName %>,</DIV>
   <DIV>Descubra nuestros nuevas ofertas !</DIV>
   <DIV><a href="https://www.adobe.com/products/es">www.adobe.com/products/es</A></DIV>
   <% } %>
   ```

1. 通过选择具有不同首选语言的收件人，在&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡中测试电子邮件内容。

   >[!NOTE]
   >
   >由于电子邮件内容中未定义替代版本，请确保在发送电子邮件之前筛选目标群体。

## 教程视频 {#conditionnal-content-video}

了解如何在多语言新闻稿的示例中向投放添加条件内容。

>[!VIDEO](https://video.tv.adobe.com/v/3446721?quality=12&captions=chi_hans)
