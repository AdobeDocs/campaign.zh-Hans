---
title: 了解Campaign组件和流程
description: 了解Campaign组件和流程
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 79d916c4d65c0c55ec20f2f5850fec40fe4e99a3
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# 了解Campaign组件和流程 {#components-and-processes}

Adobe Campaign是一款跨渠道营销解决方案，可自动执行电子邮件、移动设备、社交和离线营销活动。 Adobe Campaign提供了一个访问您的客户数据和配置文件的中心位置。 使用Adobe Campaign为客户编排一致的体验，跨渠道设计、执行和个性化您的营销，同时改进每个设备和接触点上的客户体验。 借助Adobe Campaign，您可以通过拖放式可视化工作流界面管理多个数据源、定义受众区段，以及规划和执行多步骤、跨渠道营销活动。

在中了解关于Campaign关键功能的更多信息 [此页面](../start/get-started.md).

## Campaign组件 {#ac-components}

Adobe Campaign组件和全局架构如下所述。

![](assets/do-not-localize//ac-components.png)



### 持久层{#persistance-layer}

Campaign数据库用作持久层，并包含Adobe Campaign管理的几乎所有信息和数据。 这包括：功能数据，例如用户档案、订阅、内容；技术数据，例如投放工作和日志、跟踪日志；以及工作数据（购买、商机）。

数据库的可靠性至关重要，因为大多数Adobe Campaign组件都需要访问数据库才能执行其任务（重定向模块除外）。

### 逻辑应用层{#logical-app-layer}

Campaign逻辑应用层可以方便地进行配置，以满足复杂的业务需求。 您可以将Campaign用作单个平台，其中具有不同的应用程序，这些应用程序会合并以创建开放且可伸缩的架构。 每个Campaign实例都是应用层中的流程集合，其中一些是共享的，另一些是专用的。

## Campaign托管的Cloud Service{#ac-managed-services}

Adobe Campaign v8是as a Managed Service部署的：Adobe Campaign的所有组件（包括用户界面、执行管理引擎和Campaign数据库）均完全由Adobe托管，包括电子邮件执行、镜像页面、跟踪服务器和面向外部的Web组件（例如取消订阅页面/首选项中心和登陆页面）。

## 营销活动流程

Campaign Web服务器控制对Campaign Web进程的访问。 Javascript是用于核心产品功能和自定义的服务器端语言。 Tomcat是后端引擎，作为Web流程的一部分嵌入到Campaign产品中。 例如，在JSP或JSSP页面中使用Javascript来呈现动态内容。

![](assets/do-not-localize/ac-processes.png)

Campaign客户端控制台通过HTTP使用SOAP XML连接到Web服务器。 Web服务器提供安全层，使用Javascript将请求传递到应用程序层，Campaign内部进程使用SQL访问数据库。

以下独立部署图说明了Campaign进程之间的整体通信：所有Campaign组件都安装在同一台计算机上。

![](assets/do-not-localize//ac-standalone.png)

用户使用HTTP连接到Campaign应用程序服务器。 所有数据和信息都在Campaign数据库中进行管理。 如果Campaign开发人员执行任何配置更改，则会将其捕获到数据库中。 如果营销人员创建新营销活动，则与此新营销活动相关的所有信息和数据也将在数据库中管理。 营销人员执行营销活动时，会通过SMTP服务器将电子邮件投放从Campaign服务器发送到用户档案。 当用户档案与电子邮件投放交互时（如打开电子邮件），跟踪数据会发送回跟踪服务器。

![](../assets/do-not-localize/glass.png) [了解关于Campaign流程的更多信息](../architecture/general-architecture.md#dev-env).
