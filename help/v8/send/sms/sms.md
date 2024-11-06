---
title: 使用Adobe Campaign发送短信
description: Campaign短信入门
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: bb77b915f50b31d8d91e25da6fa86aa15b03bba4
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---

# 短信入门 {#gs-sms-channel}

Adobe Campaign允许您在手机上发送个性化的短信。

对于短信消息，您可以仅以文本格式创建、修改和个性化消息。您还可以在发送短信消息之前进行预览。

>[!NOTE]
>
>您还可以使用Adobe Campaign发送[LINE](../../send/line.md)消息，其中包含文本和/或图像和链接。

要使用Adobe Campaign将短信发送到手机，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 渠道或 **[!UICONTROL LINE]** 渠道上配置外部帐户。
* 正确链接到此外部帐户的短信投放模板。

您可以在此文档中查看配置、发送和监控SMS投放的步骤：

* **配置短信渠道**

首先，您需要在[中间源基础结构](sms-mid-sourcing.md)上配置短信渠道。

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

对于此配置，您需要了解[SMPP外部帐户参数](smpp-external-account.md)和[短信渠道特征](sms-channel.md)。

完成此设置后，请检查您的[SMPP连接，并了解如何在需要时对其进行故障排除](smpp-connection.md)。

* **创建您的第一个短信投放**

要开始配置短信投放，请执行以下操作：

1. 创建您的投放，并填写[SMS投放设置](sms-delivery-settings.md)，

1. [定义投放的内容](sms-content.md)，

1. [选择受众](sms-audience.md)。

定义受众的步骤详见[此页面](../../audiences/create-audiences.md)。

* **验证并发送短信**

创建投放后：

1. [发送校样](sms-proofs.md)以验证渲染和内容，

1. 然后，[发送给最终受众](sms-send.md)。

* **监控和跟踪SMS**

发送后，[了解如何监视和跟踪你的短信](sms-monitor.md)。
