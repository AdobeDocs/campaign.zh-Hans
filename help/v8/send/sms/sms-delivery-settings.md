---
title: 短信投放设置
description: 了解如何设置短信投放
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="有限发布版" type="Informative"
exl-id: c4d500ef-2339-491f-9ae2-9bfaf72088a9
source-git-commit: 826abd5c5f8b191d34abf724b91c5a82665d00a2
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 0%

---

# 短信投放设置 {#sms-settings}

>[!IMPORTANT]
>
>本文档适用于Adobe Campaign v8.7.2及更高版本。
>
>对于旧版本，请阅读[Campaign Classicv7文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up)。

短信投放所需的技术设置包括：

* 邮件路由的SMPP外部帐户。 [了解详情](smpp-external-account.md#smpp-connection-settings)
* 配置短信选项卡。 [了解如何操作](#sms-tab)

您可以在投放模板中设置所有这些设置，以避免为每个短信投放创建进行设置。

## 配置短信选项卡 {#sms-tab}

![](assets/send_settings.png){zoomable="yes"}

以下是填写此表单所需的信息。 每个字段的说明如下：

* **[!UICONTROL Sender address]**

  此字段为可选字段。 它允许覆盖发件人地址(oADC)。 此字段的内容放在SUBMIT_SM PDU的&#x200B;*source_addr*&#x200B;字段中。

  根据SMPP规范，字段限制为21个字符，但某些提供程序可能允许较长的值。 另请注意，某些国家/地区可能会应用非常严格的限制（长度、内容、允许的字符……），因此您可能需要仔细检查您在此处放置的内容是否合法。 使用个性化字段时尤其要小心。

  如果此字段留空，将改用外部帐户中定义的Source编号字段的值。 如果两个值都为空，则&#x200B;*source_addr*&#x200B;字段将留空。

* **[!UICONTROL Service or program ID]**

  >[!NOTE]
  >
  >建议不要使用此功能。 可选的SMPP参数可提供更加灵活的实施。
  >
  >不能同时使用这两项功能。

  结合匹配的外部帐户设置，允许随每个MT发送一个可选参数。 此字段定义TLV的值部分。

* **[!UICONTROL Transmission mode]**

  此字段指示您要传输的SMS类型：普通消息或闪存消息，存储在移动设备或SIM卡上。 此设置在SUBMIT_SM PDU的dest_addr_subunit可选字段中传输。

   * **Flash**&#x200B;将该值设置为1。 它会发送一条在手机上弹出且未存储在内存中的闪存消息。
   * **Normal**&#x200B;将该值设置为0。 它会发送一条正常消息。
   * **Save on mobile**&#x200B;将该值设置为2。 它告知手机将短信存储在内存中。
   * **保存在终端**&#x200B;上将值设置为3。 它告知手机将短信存储在SIM卡中。

* **[!UICONTROL Priority, Communication type]**

  扩展SMPP连接器将忽略这些字段。

* **[!UICONTROL Maximum number of SMS per message]**

  此设置仅在禁用消息有效负载设置时才有效（有关详细信息，请参阅外部帐户设置中的）。 如果消息需要的短信数超过此值，则会触发错误。

  SMS协议将短信限制为255部分，但某些手机无法拼合长度超过10部分左右的消息（此限制取决于确切模型）。 如果您希望安全，请勿超过每条消息5部分。

  由于个性化消息在Adobe Campaign中的工作方式，消息的大小可能有所不同，因此发送大量超长消息可能会大幅增加发送成本：将此设置为合理的值有助于控制这些成本。

  指定0将禁用限制。

* **[!UICONTROL Optional SMPP parameters (TLV)]**
您可以指定要作为可选SMPP参数(TLV)发送的额外字段。 这些额外的字段与每个MT一起发送，而个性化的字段允许每个MT具有不同的值。
该表列出了随每条消息一起发送的可选参数。 列包含以下信息：
   * **标签**：这是可选的自由格式标签。 不会发送给提供商。 您可以提供参数的文本描述。
   * **标记**：标记值，以十进制格式(如12345)或带0x前缀的十六进制（如0x12ab）表示。 标记可以介于0和65535之间。 向SMPP服务提供商询问他们支持的标记。
   * **值**：要在可选参数中发送的值。 这是一个个性化字段。
   * **格式**：用于参数的编码。 您可以选择任何受支持的文本编码或最常见的二进制格式。 询问SMPP服务提供商所需的格式。
   * **最大长度**：此参数的最大字节数。 对于二进制字段，这将被忽略，因为二进制字段的大小是固定的。

* **[!UICONTROL Using binary formats for TLV]**

  Campaign支持以二进制格式发送TLV。 二进制文件仅限于发送数字。

  由于个性化字段始终输出文本，因此个性化字段必须包含数字的十进制表示形式（任何字符串只要仅包含数字就好了）。 值既可以为已签名也可以为未签名，个性化引擎仅将其转换为正确的二进制表示形式。

  使用二进制格式时，特殊值“”（空字符串）、“null”和“undefined”会完全禁用该字段，而不会引发错误。 在这三种特殊情况下，根本不传递标记。 这允许仅在个性化字段中使用精心编制的Javascript时，为某些消息传递特定的TLV。

  >[!NOTE]
  >
  >二进制格式始终以big-endian格式编码。

