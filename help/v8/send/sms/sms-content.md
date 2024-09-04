---
title: 短信定义内容
description: 了解如何设置短信投放的内容
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="有限发布版" type="Informative"
source-git-commit: a184a29301f2bd739bc3fd1373fc8cfad58f0393
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---


# 短信内容 {#sms-content}

配置短信投放的内容：

1. 在&#x200B;**[!UICONTROL Text content]**&#x200B;向导中输入消息的内容

   ![](assets/sms_content.png){zoomable="yes"}

1. 您可以通过插入个性化字段（例如添加名字）或插入预定义的个性化块（例如添加问候语）来对消息进行个性化设置。 您可以单击个性化按钮以添加以下内容：

   ![](assets/sms_perso.png){zoomable="yes"}

   单击&#x200B;**[!UICONTROL Recipient]** > **[!UICONTROL First name]**&#x200B;后，您将进行如下个性化设置：

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. 您可以预览投放，方法是进入&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL Test personalization]**&#x200B;下拉列表，然后在&#x200B;**[!UICONTROL Recipient]**&#x200B;表中选择收件人。

   ![](assets/sms_preview.png){zoomable="yes"}

   您将获得带有个性化的短信预览：

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* 如果使用Latin-1 (ISO-8859-1)代码页，SMS消息长度限制为160个字符。 如果消息使用Unicode编写，则不能超过70个字符。 某些特殊字符可能会影响消息长度。 有关消息长度的详细信息，请参阅[短信字符音译](smpp-external-account.md#smpp-channel-settings)部分。
>
>* 当存在个性化字段或条件内容字段时，消息的大小因收件人而异。 进行个性化时必须评估消息的长度。
>
>*启动分析时，将检查消息长度，并在发生溢出时显示警告。

创建投放内容后，您可以[选择受众](sms-audience.md)。