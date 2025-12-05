---
title: 迁移至新的短信连接器v2
description: 了解如何迁移至新的短信连接器v2
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 30ab5a10f17baddfc455dc406a4f31f058ea05ba
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# 迁移至新的短信连接器v2

Adobe Campaign v8引入了新的&#x200B;**专用SMS进程连接器** (v2)，与基于MTA的旧版SMS连接器相比，该连接器提供了更好的性能和可靠性。

## 为何切换到v2连接器

专用SMS过程引入对SMPP收发器模式的支持，减少连接计数并提高资源效率，同时如果需要，仍支持发送器/接收器设置。 它提供了显着增强的稳定性，能够更快地从错误中恢复，保持连接，并且不依赖本地文件或进程间通信。 性能也得到改善，具有更低的延迟、更高的吞吐量和智能微批处理，以平衡速度和可靠性。 此外，SMS过程的隔离简化了故障排除并最大限度地减少了跨渠道影响。 这些增强功能使专用连接器成为短信投放的一个更强健、可扩展的解决方案。

## 配置

使用Adobe Campaign Managed Cloud Services时，服务器配置和SMS连接器迁移由Adobe管理。 此技术过程需要直接访问服务器配置文件和数据库操作。

如果您需要迁移到新的SMS连接器v2，请联系您的Adobe代表或Adobe客户关怀。 他们将为您的实例计划和执行必要的更新。

有关Campaign v8中短信渠道的更多信息，请参阅[短信文档](../../v8/send/sms/sms.md)。
