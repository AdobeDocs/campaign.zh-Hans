---
title: 使用Adobe Campaign发送短信
description: Campaign短信入门
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 19c5a15a0f42285fc3b1a448f3cbf474d741e6e2
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 10%

---

# 短信入门 {#gs-sms-channel}

使用Adobe Campaign向客户在其移动设备上发送短信。 您可以通过短信编辑器以文本格式创建、个性化和预览消息。

要使用Adobe Campaign向移动设备发送短信，您需要：

* 在&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;渠道上配置的外部帐户。 了解如何在您的[中间源基础架构](sms-mid-sourcing.md)上配置短信渠道。 对于此配置，您需要了解[SMPP外部帐户参数](smpp-external-account.md)和[短信渠道特征](sms-channel.md)。
完成此设置后，请检查您的SMPP连接，并了解如何根据需要对其进行故障排除。 [了解详情](smpp-connection.md)。

* 正确链接到此外部帐户的短信投放模板。


>[!NOTE]
>
>您还可以使用Adobe Campaign发送[LINE](../../send/line.md)消息，其中包含文本和/或图像和链接。


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
<img alt="短信内容" src="../../assets/do-not-localize/sms.jpg">
</a>
<div>
<a href="sms-content.md"><strong>定义和个性化内容</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="受众" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>选择退出管理</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="配置" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>配置短信渠道</strong></a>
</div>
<p>
</td>
</tr></table>
