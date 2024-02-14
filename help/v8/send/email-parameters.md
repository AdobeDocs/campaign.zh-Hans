---
title: Adobe Campaign中的电子邮件参数
description: 了解Adobe Campaign中特定于电子邮件投放的选项和设置。
feature: Email
role: User
level: Beginner
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: 87c971ac6cf4abb6b04d52ce60ac2036055e1e02
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 10%

---

# 电子邮件参数 {#email-parameters}

此部分介绍投放属性中特定于电子邮件投放的可用选项和参数。

## 使用电子邮件密送 {#email-bcc}

您可以配置Adobe Campaign以保留从您的平台发送的电子邮件副本。 有关此选项的详情，请参阅 [此页面](email-bcc.md).

## 选择消息格式 {#selecting-message-formats}

您可以更改已发送电子邮件的格式。 为此，请编辑投放属性并单击 **[!UICONTROL Delivery]** 选项卡。

![](assets/email-message-format.png)

在窗口的下半部分选择电子邮件的格式：

* **[!UICONTROL Use recipient preferences]** （默认模式）

  根据收件人用户档案中存储的数据(默认存储在 **[!UICONTROL email format]** 字段(@emailFormat)。 如果收件人希望以特定格式接收消息，则会将该格式用于发送的邮件。如果未填写该字段，则会发送multipart-alternative消息（请参阅下文）。

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  该消息包含两种格式：文本和HTML。 接收时显示的格式取决于收件人邮件软件的配置(multipart-alternative)。

  >[!IMPORTANT]
  >
  >此选项包括文档的两个版本。 因此，它会降低投放吞吐量，因为消息大小更大。

* **[!UICONTROL Send all messages in text format]**

  消息以文本格式发送。 不会发送HTML格式，但仅当收件人单击消息时，才会将其用于镜像页面。

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## 设置字符编码 {#character-encoding}

在 **[!UICONTROL SMTP]** 选项卡中， **[!UICONTROL Character encoding]** 部分允许您设置特定的编码。

默认编码为UTF-8。 如果某些收件人的电子邮件提供商不支持UTF-8标准编码，您可能需要设置特定编码以正确向电子邮件的收件人显示特殊字符。

例如，您希望发送包含日语字符的电子邮件。 为确保向日本的收件人正确显示所有字符，您可能需要使用支持日语字符的编码而不是标准UTF-8。

要执行此操作，请选择 **[!UICONTROL Force the encoding used for messages]** 中的选项 **[!UICONTROL Character encoding]** 部分，并从显示的下拉列表中选择编码。

![](assets/email-smtp-encoding.png)

## 管理退回电子邮件 {#managing-bounce-emails}

此 **[!UICONTROL SMTP]** 通过“投放”属性的“选项卡”，还可以配置退回邮件的管理。

* **[!UICONTROL Errors-to-address]**：默认情况下，平台的默认错误框中会收到退回的电子邮件，但您可以为投放定义特定的错误地址。

* **[!UICONTROL Bounce address]**：您还可以定义将未处理的退回电子邮件转发到的其他地址。 利用此地址，可调查应用程序无法自动限定电子邮件时退回的原因。

其中每个字段都可以使用专用图标进行个性化。 了解中个性化字段的更多信息 [本节](personalization-fields.md).

![](assets/email-smtp-bounce.png)

有关退回邮件管理的更多信息，请参阅 [本节](delivery-failures.md#bounce-mail-management).

## 添加SMTP标头 {#adding-smtp-headers}

可以将SMTP标头添加到投放。 要实现此目的，请使用 **[!UICONTROL SMTP]** 选项卡。

在此窗口中输入的脚本必须引用以下格式中每行一个标头： **name：value**.

如有必要，将自动对值进行编码。

>[!IMPORTANT]
>
>高级用户可随时添加脚本以插入其他SMTP标头。
>
>此脚本的语法必须符合此内容类型的要求：没有未使用的空格，没有空行等。

![](assets/email-smtp-headers.png)


## 生成镜像页面 {#generating-mirror-page}

镜像页面是可通过 Web 浏览器在线访问的 HTML 页面。其内容与电子邮件的内容相同。如果收件人尝试在收件箱中查看电子邮件时遇到渲染问题或图像损坏，此功能会很有用。

了解如何在中插入指向镜像页面的链接 [本节](mirror-page.md)
