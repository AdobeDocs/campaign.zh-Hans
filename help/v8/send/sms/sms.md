---
title: 使用Adobe Campaign发送短信
description: Campaign短信入门
feature: SMS
role: User, Data Engineer
level: Beginner
badge: label="有限发布版" type="Informative"
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 4%

---

# 短信入门 {#gs-sms-channel}

使用Adobe Campaign发送个性化的短信消息。

>[!IMPORTANT]
>
>本文档适用于Adobe Campaign v8.7.2及更高版本。
>
>对于旧版本，请阅读[Campaign Classicv7文档](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up)。

>[!NOTE]
>
>Adobe Campaign还允许您通过其&#x200B;**Adobe Campaign移动应用程序渠道(NMAC)**&#x200B;选项在手机上提交推送通知。 可在[此部分](../push.md)中了解详情。

SMS的简单性和易用性使其成为非常宝贵的通信渠道，此外，它还具有数十亿终端的无与伦比的稳定性和兼容性。

发送短信主要有2种方式：

* 从手机手动发送。 这是你平常用来与人直接交流的方式。
* 从Internet发送。 这是Adobe Campaign用于发送消息的方式。 为此，您需要一家短信服务提供商，为从互联网到移动网络架起一座桥梁。

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
