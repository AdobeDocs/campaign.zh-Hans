---
title: Campaign电子邮件渠道设置
description: Campaign电子邮件渠道设置
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 5%

---

# Campaign电子邮件渠道设置

## 电子邮件密件抄送 {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

您可以配置Adobe Campaign以保留从您的平台发送的电子邮件副本。

Adobe Campaign本身不会管理存档文件。 它使您能够将您选择的邮件发送到专用的密件抄送（密件抄送）电子邮件地址，从中可以使用外部系统处理和存档这些邮件。 然后，对应于所发送电子邮件的.eml文件可以传送到远程服务器，如SMTP电子邮件服务器。

>[!CAUTION]
>
>出于隐私原因，密件抄送电子邮件必须由能够安全存储个人身份信息(PII)的归档系统处理。

存档目标是您选择的密件抄送电子邮件地址，该地址对投放收件人保持不可见。

![](../assets/do-not-localize/speech.png)  作为托管Cloud Service用户， [联系人Adobe](../start/campaign-faq.md#support){target="_blank"} 用于传达要用于归档的密件抄送电子邮件地址。

定义密件抄送电子邮件地址后，必须在投放级别启用专用选项。

>[!CAUTION]
>
>创建新投放或投放模板时， **[!UICONTROL Email BCC]** 默认不启用。 您需要在电子邮件投放或投放模板中手动启用它。


为此请执行以下操作步骤：

1. 转到 **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**，或 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 选择您选择的投放或复制现成的投放内容 **[!UICONTROL Email delivery]** 模板，然后选择复制的模板。
1. 单击 **[!UICONTROL Properties]** 按钮。
1. 选择 **[!UICONTROL Delivery]** 选项卡。
1. 勾选 **[!UICONTROL Email BCC]** 选项。

   ![](assets/email-bcc.png)

1. 选择 **[!UICONTROL Ok]**。

基于此模板每次投放的所有已发送消息的副本将发送到已配置的电子邮件密件抄送地址。

请注意以下具体情况和建议：

* 您只能使用一个密件抄送电子邮件地址。

* 确保密件抄送地址有足够的接收容量来存档发送的所有电子邮件。

* 电子邮件密送 <!--with Enhanced MTA--> 在发送给收件人之前发送给密件抄送电子邮件地址，这可能会导致即使原始投放可能已退回，仍发送密件抄送消息。 有关退回的详细信息，请参阅 [了解投放失败](../send/delivery-failures.md).

* 如果发送到密件抄送地址的电子邮件被打开并单击通过，则中会考虑这一点 **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** ，这可能会导致某些计算错误。

<!--Only successfully sent emails are taken in account, bounces are not.-->

**了解详情**

在以下部分中：

* [使用电子邮件投放模板](../send/create-templates.md)

* [了解投放失败](../send/delivery-failures.md)


在Campaign Classicv7文档中：

* [选择电子邮件格式](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [选择字符编码](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [设置退回电子邮件地址](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

