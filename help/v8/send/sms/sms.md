---
title: 使用Adobe Campaign发送短信
description: Campaign短信入门
feature: SMS
role: User, Developer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
TQID: https://experienceleague.adobe.com/7ChOYJmYScxaAoqnruyMv-8n0AkXgYAIlt1783hTjvY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 12%

---

# 短信入门 {#gs-sms-channel}

使用Adobe Campaign向客户在其移动设备上发送短信。 您可以通过短信编辑器以文本格式创建、个性化和预览消息。

要使用Adobe Campaign向移动设备发送短信，您需要：

* 在&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;渠道上配置的外部帐户。 了解如何在您的[中间源基础架构](sms-mid-sourcing.md)上配置短信渠道。 对于此配置，您需要了解[SMPP外部帐户参数](smpp-external-account.md)和[短信渠道特征](sms-channel.md)。
完成此设置后，请检查您的SMPP连接，并了解如何根据需要对其进行故障排除。 [了解详情](smpp-connection.md)。

* 正确链接到此外部帐户的短信投放模板。

Adobe Campaign支持使用两个SMS连接器向客户发送SMS消息。 [了解详情](sms-connectors.md)。

>[!NOTE]
>
>您还可以使用Adobe Campaign将[推送通知](../push.md)和[LINE](../line/line.md)消息发送到移动设备。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="创建短信" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>创建短信投放</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="短信内容" src="../../assets/do-not-localize/sms-create.jpeg">
</a>
<div>
<a href="sms-content.md"><strong>定义短信内容</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="短信受众" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>选择受众</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="短信配置" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>配置短信渠道</strong></a>
</div>
<p>
</td>
</tr></table>
