---
title: 使用Campaign和Adobe Experience Platform
description: 了解如何使用Campaign和Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# 使用Campaign和Adobe Experience Platform

Adobe Campaign托管Cloud Service目标和源连接器允许Adobe Campaign与Adobe Experience Platform之间的无缝集成。

* 使用Adobe Campaign Managed Cloud Services **目标连接** 要将Experience Platform区段发送到Adobe Campaign以进行激活，请执行以下操作：

  为此，请配置新的Adobe Campaign Managed Cloud Services **目标连接** 以激活区段/受众，并将该数据发送到Adobe Campaign。 提供要使用的Campaign实例的详细信息，选择要为目标激活的区段，然后配置要导出到Campaign的属性。 [了解如何创建Adobe Campaign Managed Cloud Services目标连接](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* 使用Adobe Campaign Managed Cloud Services **源连接** 要将Adobe Campaign投放和跟踪日志发送到Adobe Experience Platform，请执行以下操作：

  为此，请配置新的Adobe Campaign Managed Cloud Services **源连接** 将Campaign事件摄取到AdobeExperience Platform。 提供有关Campaign实例和要使用的架构的详细信息，选择应在其中摄取数据的数据集，然后配置要检索的字段。 [了解如何创建Adobe Campaign Managed Cloud Services源连接](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
