---
solution: Campaign v8
product: Adobe Campaign
title: Campaign电子邮件渠道设置
description: Campaign电子邮件渠道设置
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 3%

---

# Campaign电子邮件渠道设置

## 电子邮件密送

您可以配置Adobe Campaign以保留从您的平台发送的电子邮件副本。

>[!NOTE]
>电子邮件密送功能是可选的。 请核实您的许可协议。

Adobe Campaign本身不管理已存档的文件。 它确实允许您将您选择的消息发送到专用地址，从中可以使用外部系统处理和存档这些消息。

为此，与已发送电子邮件对应的.eml文件会被传输到远程服务器，如SMTP电子邮件服务器。 存档目标是您必须指定的密件抄送电子邮件地址（投放收件人不可见）。

请注意：

* 您只能使用&#x200B;**一个**&#x200B;密送电子邮件地址。

* 只有成功发送的电子邮件才会被考虑在内，而退回则不会。

:speech_balloon:作为受管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support)以在Campaign中激活电子邮件密送。 您选择的密件抄送电子邮件地址必须提供给Adobe团队，由团队为您进行配置。

配置电子邮件密送后，请确保在投放模板或通过&#x200B;**电子邮件密送**&#x200B;选项在投放中启用该功能。

![](assets/email-bcc.png)


**相关** 主题Campaign Classicv7文档：

* [使用电子邮件投放模板](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* [发现电子邮件参数](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html)
* [了解投放失败](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html)
