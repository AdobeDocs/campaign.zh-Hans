---
title: 使用Campaign和Adobe Experience Platform
description: 了解如何使用Campaign和Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 27705fc85794611d1207fe7f3eac3010601b0dc5
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# 使用Campaign和Adobe Experience Platform

Adobe Campaign托管Cloud Service目标和源连接器允许在Adobe Campaign和Adobe Experience Platform之间无缝集成：

* 使用 **Adobe Campaign Managed Cloud Services** 目标连接，以将Experience Platform区段通过Adobe Campaign进行激活，

   ![](assets/aep-destination.png)

* 使用 **Adobe Campaign Managed Cloud Services** 源连接，以将Adobe Campaign投放和跟踪日志发送到Adobe Experience Platform。

   ![](assets/aep-logs.png)

在Adobe Experience Platform中配置此集成的步骤如下所示：

1. 配置新的Adobe Campaign Managed Cloud Services目标连接以激活区段/受众，并将该数据发送到Adobe Campaign。

   提供有关要使用的Campaign实例的详细信息，选择要为目标激活的区段，然后配置要导出到Campaign的属性。

   [了解如何创建Adobe Campaign Managed Cloud Services目标连接](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. 配置新的Adobe Campaign Managed Cloud Services源连接，以将Campaign事件摄取到Adobe体验平台。

   提供有关Campaign实例和要使用的架构的详细信息，选择应摄取数据的数据集，然后配置要检索的字段。

   [了解如何创建Adobe Campaign Managed Cloud Services源连接](https://www.adobe.com/go/sources-campaign-ui-en)
