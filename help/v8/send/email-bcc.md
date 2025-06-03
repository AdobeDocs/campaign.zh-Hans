---
title: 将邮件副本发送到密件抄送地址
description: 了解如何在Adobe Campaign中激活电子邮件密送
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# 将邮件副本发送到密件抄送地址 {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## 关于电子邮件密送 {#gs-bcc}

您可以配置Adobe Campaign以保留从您的平台发送的电子邮件副本。 此选项允许您使用专用的密件抄送（密件抄送）电子邮件地址发送邮件，可以从此处使用外部系统处理和存档邮件。

>[!CAUTION]
>
>出于隐私原因，密件抄送电子邮件必须由能够安全存储个人身份信息(PII)的归档系统处理。

Adobe Campaign本身不会管理存档文件。 然后，对应于所发送电子邮件的.eml文件可以传送到远程服务器，如SMTP电子邮件服务器。

存档目标是您选择的密件抄送电子邮件地址，该地址对投放收件人保持不可见。 定义密件抄送电子邮件地址后，必须在[投放模板](create-templates.md)级别启用专用选项。

>[!NOTE]
>
>作为托管Cloud Services用户，[联系Adobe](../start/campaign-faq.md#support){target="_blank"}以传达要用于归档的密件抄送电子邮件地址。

## 启用电子邮件密送 {#enable-bcc}

要为特定[投放模板](create-templates.md)启用密件抄送，请执行以下步骤：

1. 在Campaign资源管理器中，浏览到投放模板文件夹。 默认情况下，投放模板存储在&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;文件夹中。
1. 编辑要通过密送更新的投放模板。
1. 单击 **[!UICONTROL Properties]** 按钮。
1. 在&#x200B;**[!UICONTROL Delivery]**&#x200B;选项卡中，选中&#x200B;**[!UICONTROL Email BCC with enhanced Momentum]**&#x200B;选项。

   ![](assets/email-bcc.png)

1. 单击 **[!UICONTROL Ok]** 确认。

基于此模板的每个投放的所有已发送消息的副本将发送到为您的平台配置的电子邮件密件抄送地址。

## 护栏和建议 {#recommendations-bcc}

将电子邮件密送与Adobe Campaign结合使用时，以下护栏和推荐适用：

* 您只能使用一个密件抄送电子邮件地址。

* 确保密件抄送地址有足够的接收容量来存档发送的所有电子邮件。

* 电子邮件密件抄送<!--with Enhanced MTA-->在发送给收件人之前会发送给密件抄送电子邮件地址，这可能导致密件抄送邮件被发送，即使原始投放可能已退回。 有关退回的详细信息，请参阅[了解投放失败](delivery-failures.md)。

* 发送到密件抄送地址的电子邮件不应打开和点进，因为发送分析的&#x200B;**[!UICONTROL Total opens]**&#x200B;和&#x200B;**[!UICONTROL Clicks]**&#x200B;中考虑了这些活动，这可能会导致计算错误。

<!--Only successfully sent emails are taken in account, bounces are not.-->
