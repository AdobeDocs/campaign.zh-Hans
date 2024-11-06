---
title: 定义短信内容并使其个性化
description: 了解如何定义和个性化短信投放内容
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
source-git-commit: 0ef082b49261d0d2de5a6891a4a7f0cf5aafa221
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 定义短信内容 {#sms-content}

配置短信投放的内容：

1. 在&#x200B;**[!UICONTROL Text content]**&#x200B;选项卡中输入消息的内容。

   ![](assets/sms_content.png){zoomable="yes"}

1. 您可以通过插入个性化字段（例如添加名字）或插入预定义的个性化块（例如添加问候语）来对消息进行个性化设置。 单击个性化按钮以添加以下内容：

   ![](assets/sms_perso.png){zoomable="yes"}

   例如，在单击&#x200B;**[!UICONTROL Recipient]** > **[!UICONTROL First name]**&#x200B;后，短信内容将更新为个性化字段，如下所示：

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   在[本节](../personalize.md)中了解有关Adobe Campaign中个性化的更多信息。

1. 您可以从&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡预览投放内容。 要检查您的个性化设置，请单击&#x200B;**[!UICONTROL Test personalization]**&#x200B;下拉列表，然后选择收件人。

   ![](assets/sms_preview.png){zoomable="yes"}

   您可以通过个性化检查短信预览：

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* 如果使用Latin-1 (ISO-8859-1)代码页，SMS消息长度限制为160个字符。 如果消息使用Unicode编写，则不能超过70个字符。 某些特殊字符可能会影响消息长度。 有关消息长度的详细信息，请参阅[短信字符音译](smpp-external-account.md#smpp-channel-settings)部分。
>
>* 当存在个性化字段或条件内容字段时，消息的大小因收件人而异。 进行个性化时必须评估消息的长度。
>
>*启动分析时，将检查消息长度，并在发生溢出时显示警告。

创建投放内容后，您可以[选择受众](sms-audience.md)。
