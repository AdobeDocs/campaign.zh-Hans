---
title: 条件内容
description: 了解如何创建条件内容
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 9%

---


# 创建条件内容{#conditional-content}

通过配置条件内容字段，您可以创建高级个性化。满足特定条件时可替换完整的文本块和/或图像。


## 在电子邮件中使用条件 {#conditions-in-an-email}

在以下示例中，了解如何创建根据收件人的城市和兴趣动态个性化的消息。

* 根据收件人所在的城市更改消息，
* 根据收件人的兴趣将选件的内容个性化。

要根据字段的值创建条件内容，请应用以下步骤：

1. 打开现有投放或创建新电子邮件投放。
1. 在电子邮件内容编辑器中，单击个性化图标，然后选择 **[!UICONTROL Conditional content > If]**.

   ![插入条件](assets/condition-insert.png)

   个性化元素会插入到消息正文中。 您现在必须配置它们。

1. 填写 **if** 表达式。

   * 选择表达式的第一个元素， **`<FIELD>`**，然后单击个性化图标以将其替换为测试字段。
   * 替换 **`<VALUE>`** ，其中字段的值将满足条件。 此值必须用引号表示。
   * 指定满足条件时要插入的内容。 这可以是文本、图像、表单、超文本链接等。

   ![电子邮件中的条件](assets/condition-in-email.png)

1. 单击 **[!UICONTROL Preview]** 选项卡，以根据投放收件人查看消息的内容。 选择条件为true的收件人以检查内容。 然后，选择其为false的其他收件人，并再次检查。

您可以添加其他大小写，并根据一个或多个字段的值定义不同的内容。 为此，请使用 **[!UICONTROL Conditional content > Else]** 和 **[!UICONTROL Conditional content > Else if]**. 这些表达式的配置方式与 **if** 表达式。

>[!CAUTION]
>
>的 **%> &lt;%** 添加后必须删除字符 **Else** 和 **如果** 条件。


## 用例：创建多语言电子邮件 {#creating-multilingual-email}

在以下示例中，了解如何创建多语言电子邮件。 内容以一种或另一种语言显示，具体取决于收件人的首选语言。

1. 创建电子邮件并选择目标群体。 在此示例中，用于显示一个版本或另一个版本的条件将基于 **语言** 收件人用户档案的值。 这些值将设置为 **EN**, **FR**, **ES**.
1. 在电子邮件HTML内容中，单击 **[!UICONTROL Source]** 选项卡，并粘贴以下代码：

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

1. 在 **[!UICONTROL Preview]** 选项卡，方法是选择使用不同首选语言的收件人。

   >[!NOTE]
   >
   >由于电子邮件内容中未定义任何替代版本，因此请确保在发送电子邮件之前过滤目标群体。

## 教程视频 {#conditionnal-content-video}

了解如何在多语言新闻稿的示例中向投放添加条件内容。

>[!VIDEO](https://video.tv.adobe.com/v/335682?quality=12)

