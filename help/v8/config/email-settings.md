---
solution: Campaign
product: Adobe Campaign
title: 活动电子邮件渠道设置
description: 活动电子邮件渠道设置
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# 活动电子邮件渠道设置

## 密件抄送

您可以配置Adobe Campaign以保留从您的平台发送的电子邮件副本。

但是，Adobe Campaign本身不管理存档的文件。 它确实允许您将您选择的消息发送到专用地址，从此处可以使用外部系统处理和存档这些消息。

为此，与已发送电子邮件对应的.eml文件将传输到远程服务器，如SMTP电子邮件服务器。 存档目标是您必须指定的密件抄送电子邮件地址(对于投放收件人不可见)。

请注意：

* 只能使用一个密件抄送电子邮件地址。

* 只有成功发送的电子邮件才会被考虑在内，而不会被退回。

配置电子邮件密件抄送后，请通过&#x200B;**电子邮件密件抄送**&#x200B;选项确保在投放模板或投放中启用该功能。

:arrow_upper_right:有关详细信息，请参阅[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc)

**注意**:密件抄送功能是可选的。请核实您的许可协议。

:speech_balloon:作为受管Cloud Services用户，[联系Adobe](../start/support.md#support)以在活动中激活电子邮件密送。 您选择的密件抄送电子邮件地址必须提供给将为您配置该地址的Adobe团队。