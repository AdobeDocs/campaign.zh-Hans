---
title: 短信连接器
description: 了解Adobe Campaign中的SMS连接器
feature: SMS
role: User, Admin
level: Intermediate
source-git-commit: e349e9f236c3eeb28ffe96bcc5ec72ab64c4c127
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%

---

# 关于SMS连接器类型 {#sms-connectors}

Adobe Campaign支持使用两个SMS连接器向客户发送SMS消息：

* **旧版SMS连接器**：在Campaign v7和更早版本的Campaign v8中使用的连接器的第一个版本。 [了解详情](#legacy-sms-connector)
* **SMS连接器v2**：从Campaign v8.9.1开始在GA中提供，此v2专用的SMS连接器已进行现代化改进，以提供改进的性能和可靠性。 [了解详情](#sms-connector-v2)

## 旧版SMS连接器 {#legacy-sms-connector}

旧版SMS连接器是在Adobe Campaign的早期版本中使用的基于MTA的SMS连接器。 现有实施仍支持此连接器，但Adobe强烈建议升级到v8.9.1或更高版本，以从v2连接器的改进和可靠性中获益。

要了解如何从v2连接器受益，请参阅[激活](#activation)部分。

有关旧版SMS连接器配置和用法的详细信息，请参阅[Campaign Classic文档](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}。

## SMS连接器v2 {#sms-connector-v2}

从v8.9.1开始的GA中提供的v2连接器支持收发器模式SMPP连接、持久SMPP连接，并确保更好的兼容性。 专用短信外部帐户可用于使用v2连接器的所有短信实施。

对于新安装，v2连接器默认处于启用状态。 如果您使用旧版连接器从以前的版本升级，则需要联系Adobe代表以切换到v2连接器。 请参阅[激活](#activation)部分。

要了解如何在Campaign v8中使用SMS连接器v2，请参阅[SMS文档](sms.md)。

>[!NOTE]
>
>v2连接器也可在以下内部版本中使用，但有一些限制：
>* 8.8.1：所有Campaign FDA环境的版本。 不适用于Campaign FFDA部署。
>* 8.8.2：适用于所有部署类型（包括FFDA）的版本。 已在有限可用性(LA)中发布。

## 激活 {#activation}

### 为何切换到v2连接器 {#why-switch-v2}

专用SMS过程引入对SMPP收发器模式的支持，减少连接计数并提高资源效率，同时如果需要，仍支持发送器/接收器设置。 它提供了显着增强的稳定性，能够更快地从错误中恢复，保持连接，并且不依赖本地文件或进程间通信。 性能也得到改善，具有更低的延迟、更高的吞吐量和智能微批处理，以平衡速度和可靠性。 此外，SMS过程的隔离简化了故障排除并最大限度地减少了跨渠道影响。 这些增强功能使专用连接器成为短信投放的一个更强健、可扩展的解决方案。

### 配置 {#configuration}

使用Adobe Campaign Managed Cloud Services时，服务器配置和SMS连接器迁移由Adobe管理。 此技术过程需要直接访问服务器配置文件和数据库操作。

要激活并开始使用SMS连接器v2，您首先需要升级到v8.9.1或更高版本。 请联系您的Adobe代表或Adobe客户关怀。 他们将为您的实例计划和执行必要的更新。