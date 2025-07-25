---
title: 短信渠道特征
description: 了解短信渠道的特征
feature: SMS
role: User
level: Intermediate
exl-id: abab6f15-43ea-42fc-817b-8dbd88df82f7
source-git-commit: 5c5d19c9b9b413bb630a4e5738c6697d2341665a
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 1%

---

# 短信渠道特征 {#sms-channel}

>[!AVAILABILITY]
>
>此功能适用于所有Campaign FDA环境。 **不**&#x200B;可用于Campaign FFDA部署。 本文档适用于Adobe Campaign v8.7.2及更高版本。 要从旧版短信连接器切换到新版短信连接器，请参阅此[技术说明](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>对于旧版本，请阅读[Campaign Classic v7文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}。

## 短信类型 {#sms-types}

通过短信提供商发送短信时，您会遇到3种不同的短信：

* **SMS MT（已终止移动设备）**：这是Adobe Campaign通过SMPP提供商向手机发出的短信。
* **SMS MO （发起移动设备）**：这是移动设备通过SMPP提供商向Adobe Campaign发送的短信。
* **SMS SR（状态报告）或DR或DLR（投放回执）**：这是移动设备通过SMPP提供商发送给Adobe Campaign的回执，表明已成功接收短信。 Adobe Campaign还可能会收到指示无法投放消息的SR，通常包含错误描述。

您需要区分确认（RESP PDU，SMPP协议的一部分）和SR。 SR是通过网络端到端发送的一种SMS，而确认只是确认一次传输成功。

确认和SR都可以触发错误，区分二者将有助于进行故障排除。

### 短信携带的信息  {#sms-info}

短信携带的信息比文本多。 此处列出您希望在短信中找到的内容：

* 文本，长度限制为140字节，这意味着根据编码方式，长度介于70到160个字符之间。 有关详细信息和限制，请参阅下面的[短信文本编码](#sms-text-encoding)。
* 收件人地址，有时称为ADC或MSISDN（“电话号码”的技术名称）。 这是将接收短信的移动设备的号码。
* 发件人地址，可以称为oADC，有时也可以称为发件人ID。 这可以是电话号码（日常使用）、短代码（通过提供商发送时）或名称（这是一个可选功能，在这种情况下，您无法回复短信）。
* 用于指示消息是否为闪存消息的标志（闪存消息是未存储在内存中的弹出窗口）
* 用于指示是否需要SR的标志。
* 一个有效日期，在此日期之后，不允许任何网络设备重试（并不总是存在或遵循）。
* 一个data_coding字段，它指示文本的编码。

## 短信文本编码 {#sms-text-encoding}

>[!IMPORTANT]
>
>短信编码是一个庞大而复杂的主题，有许多陷阱和不合规的实施！

第一个规则是&#x200B;**如果出现编码问题，请始终与SMPP提供程序联系**。 只有用户才精确了解他们支持的编码方式，以及由于其技术平台的限制而可能适用的特殊规则。 让他们检查您发送给他们的内容以及他们发送给您的内容，这是成功且稳定互连的唯一途径。

SMS消息使用特殊的7位编码，通常称为GSM7编码。  维基百科有[篇关于它的好文章（英文GSM 03.38）](https://en.wikipedia.org/wiki/GSM_03.38)。

在SMPP协议中，GSM7文本将扩展为每个字符8位，可促进故障排除。 SMSC会将其打包成每个字符7位，然后再发送到移动设备。 这意味着SMS的short_message字段在SMPP帧中可能长达160字节，而在移动网络上发送时限制为140字节（最高有效位被简单地丢弃）。

如果出现编码问题，请检查以下重要事项：
* 首先，确保您知道哪些字符属于哪种编码。 GSM7由于其部分支持变音符号（重音符号）而臭名昭著。 尤其是在法语中，é和è是GSM7的一部分，但ê、â或ï不是。 西班牙语也是如此。
* 带有cedilla (c)的C在GSM7字母表中仅以大写形式出现，但有些手机以小写或“智能”大小写呈现：一般建议是完全避免这种情况并移除cedilla（法语仍然可读）或切换到UCS-2。
* **请勿在短信中使用ASCII！**，除非SMPP提供商明确要求：此编码会浪费空间，因为它有8位字符且覆盖范围比GSM7少。 CDMA网络（用于北美）可能需要此编码。
* 并非始终支持Latin-1。 在尝试使用Latin-1之前，请检查与您的SMPP提供商的兼容性。
* Adobe Campaign连接器不支持国家语言转换表。 必须改用UCS-2或其他data_coding。
* UCS-2和UTF-16经常被手机混合使用。 对于发送表情符号和其他UCS-2中不存在的少见字符的人来说，这是一个问题。
* 仅旧款手机没有所有UCS-2字符的字体字形。 最新款智能手机往往能够轻松显示稀有字符，旧款智能手机通常缺少许多表情符号，而老款功能手机的支持范围通常仅限于购买时所在国家的母语有用的内容。 如果你想使用某种表情符号或ASCII艺术，请在发送前在多种手机上测试一下。 促销活动预览不会模拟缺少的字形，将显示显示预览的Web浏览器上可用的任何符号。

*data_coding*&#x200B;字段用于告知使用哪种编码。 主要问题是，值0表示规范中的&#x200B;*默认SMSC编码*，通常它表示GSM7，但情况并非总是如此。 与SMPP提供商核实，其编码与data_coding = 0关联。 其他data_coding值倾向于遵循规范，但唯一确定的方法是与SMPP提供商核实。

消息的大小上限取决于其编码。 下表总结了所有相关信息：

| 编码 | 常用数据编码 | 消息大小（字符） | 多部分短信的部分大小 | 可用字符 |
|:-:|:-:|:-:|:-:|:-:|  
| GSM7 | 0 | 160 | 152 | GSM7基本字符集+扩展（扩展字符占2个字符） |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode（因手机而异） |

## 多部分SMS（长短信） {#multipart-sms}

多部分SMS（通常称为长SMS）是以多个部分发送的短信。 由于移动网络协议中的技术限制，短信不能大于140字节（请参阅下面的短信文本编码部分以了解短信中可以容纳的字符数），因此需要拆分较长的消息。

长消息的每个部分都是单独的短信。 这些部件在网络上独立运行，并由接收手机组装。 为了适当地处理重试和连接问题，Campaign以相反顺序发送各个部分，并且仅在消息的第一部分（最后发送的部分）请求SR；由于手机仅在收到其第一部分时显示消息，因此对其他部分的重试不会在手机上产生重复项。

可以使用投放模板中的每条消息的最大短信数设置设置每次投放的最大短信数。 超过此限制的消息在发送期间将失败，并且短信失败原因过长。

有2种方法可发送长短信：

* UDH
* message_payload

UDH是发送长消息的默认和推荐方式。 在此模式下，连接器会将消息拆分为多个SUBMIT_SM PDU，其中包含UDH信息。 该协议是手机本身使用的协议，这意味着Campaign对消息生成具有最大控制权，能够准确计算发送了多少部分以及它们是如何拆分的。

*message_payload*&#x200B;是一种在单个SUBMIT_SM PDU中发送整个长消息的方法。 提供商必须拆分该部分，这意味着Campaign无法确切知道发送了多少个部件。 某些提供商需要此模式，仅当它们不支持UDH时才使用它。

有关协议和格式的更多详细信息，请参阅上述SUBMIT_SM PDU的esm_class、short_message和message_payload字段的说明。

>[!NOTE]
>
>虽然Adobe Campaign支持UDH和message_payload进行发送，但传入的SMS (MO)仅支持message_payload。
