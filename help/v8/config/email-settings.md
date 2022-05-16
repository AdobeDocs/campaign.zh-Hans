---
title: Campaign电子邮件渠道设置
description: Campaign电子邮件渠道设置
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 6%

---

# Campaign电子邮件渠道设置

## 电子邮件密送

您可以配置Adobe Campaign以保留从您的平台发送的电子邮件副本。

>[!NOTE]
>电子邮件密送功能是可选的。 请核实您的许可协议。

Adobe Campaign本身不管理已存档的文件。 它确实允许您将您选择的消息发送到专用地址，从中可以使用外部系统处理和存档这些消息。

为此，与已发送电子邮件对应的.eml文件会被传输到远程服务器，如SMTP电子邮件服务器。 存档目标是您必须指定的密件抄送电子邮件地址（投放收件人不可见）。

请注意：

* 您只能使用 **one** 密送电子邮件地址。

* 只有成功发送的电子邮件才会被考虑在内，而退回则不会。

![](../assets/do-not-localize/speech.png)  作为托管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support) 以在Campaign中激活电子邮件密送。 您选择的密件抄送电子邮件地址必须提供给Adobe团队，由团队为您进行配置。

配置电子邮件密件抄送后，请确保在投放模板或通过 **电子邮件密送** 选项。

![](assets/email-bcc.png)


**Campaign Classic v7 文档**&#x200B;中的相关主题：


* [生成镜像页面](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [选择电子邮件格式](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [选择字符编码](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [设置退回电子邮件地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [使用电子邮件投放模板](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hans){target=&quot;_blank&quot;}

* [了解投放失败](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
