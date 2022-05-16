---
title: 了解Campaign流程和组件
description: 了解Campaign流程和组件
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---

# 了解Campaign流程和组件 {#components-and-processes}

Adobe Campaign是一个跨渠道营销解决方案，可自动执行电子邮件、移动设备、社交和离线促销活动。 Adobe Campaign提供了一个访问客户数据和用户档案的中心位置。 使用Adobe Campaign为客户编排一致的体验，设计、执行和个性化跨渠道的营销，同时改善每个设备和接触点上的客户体验。 借助Adobe Campaign，您可以通过拖放可视化工作流界面管理多个数据源、定义受众区段，以及规划和执行多步跨渠道营销活动。

进一步了解 [本页](../start/get-started.md).

## 营销活动组件 {#ac-components}

Adobe Campaign组件和全局架构如下所述。

![](assets/ac-components.png)

### 表示图层{#presentation-layer}

您可以通过富客户端、瘦客户端或API集成访问Adobe Campaign。

* 富客户端

   Campaign富客户端是一个本机应用程序，它通过标准的Internet协议（如SOAP和HTTP）与Adobe Campaign应用程序服务器进行通信。

   Campaign客户端控制台集中了所有功能和设置，并且由于依赖于本地缓存，因此需要最小的带宽。 Campaign客户端控制台专为轻松部署而设计，可从Internet浏览器进行部署，并自动更新，且不需要任何特定的网络配置，因为它只生成HTTP(S)流量。

   ![](../assets/do-not-localize/glass.png) [了解关于 Campaign 客户端控制台的更多信息](../start/connect.md)。

* 瘦客户端

   Adobe Campaign Web访问功能允许您使用Web浏览器通过HTML用户界面访问Campaign功能的子集。 使用此Web界面访问报表、控制和验证消息、访问监控功能板等。

   ![](../assets/do-not-localize/glass.png) [了解关于 Campaign Web Access 的更多信息](../start/connect.md)。

* 具有API的外部应用程序

   在某些情况下，可以使用通过SOAP协议公开的Web服务API从外部应用程序调用系统。

   ![](../assets/do-not-localize/glass.png) [进一步了解Campaign API](../dev/api.md).

### 持久层{#persistance-layer}

Campaign数据库用作持久层，包含几乎所有由Adobe Campaign管理的信息和数据。 这包括：功能数据，如用户档案、订阅、内容；技术数据，如投放作业和日志、跟踪日志；和工作数据（购买、商机）。

数据库的可靠性至关重要，因为大多数Adobe Campaign组件都需要访问数据库以执行其任务（重定向模块除外）。

### 逻辑应用层{#logical-app-layer}

Campaign逻辑应用程序层可轻松配置以满足复杂的业务需求。 您可以将Campaign用作具有不同应用程序的单一平台，这些应用程序结合在一起可创建开放且可扩展的架构。 每个Campaign实例是应用程序层中的流程集合，其中一些流程是共享的，一些流程是专用的。

## Campaign Managed Services{#ac-managed-services}

Adobe Campaign v8已部署as a Managed Service:Adobe Campaign的所有组件（包括用户界面、执行管理引擎和Campaign数据库）都由Adobe完全托管，包括电子邮件执行、镜像页面、跟踪服务器以及面向外部的Web组件（如取消订阅页面/首选项中心和登陆页面）。

## 营销活动流程

Campaign Web服务器控制对Campaign Web进程的访问。 Javascript是用于核心产品功能和自定义的服务器端语言。 Tomcat是后端引擎，作为Web过程的一部分嵌入到Campaign产品中。 例如，在JSP或JSSP页中使用Javascript来呈现动态内容。

![](assets/ac-processes.png)

Campaign客户端控制台使用SOAP XML通过HTTP连接到Web服务器。 Web服务器提供安全层，使用Javascript将请求传递到应用程序层，Campaign内部进程使用SQL访问数据库。

以下独立部署图描述了Campaign流程之间的整体通信：所有Campaign组件都安装在同一台计算机中。

![](assets/ac-standalone.png)

用户使用HTTP连接到Campaign应用程序服务器。 所有数据和信息都在Campaign数据库中管理。 如果Campaign开发人员执行任何配置更改，则会在数据库中捕获该配置。 如果营销人员创建新营销活动，则与该新营销活动相关的所有信息和数据也会在数据库中进行管理。 营销人员执行营销活动时，会通过SMTP服务器将电子邮件投放从Campaign服务器发送到用户档案。 当用户档案与电子邮件投放进行交互（如打开电子邮件）时，该跟踪数据会发送回跟踪服务器。

![](../assets/do-not-localize/glass.png) [进一步了解Campaign流程](../dev/general-architecture.md#dev-env).
