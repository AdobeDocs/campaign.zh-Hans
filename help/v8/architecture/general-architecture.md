---
title: 一般架构
description: 详细了解 Adobe Campaign 架构和组件。详细了解使您的客户端控制台和环境个性化。
feature: Architecture
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: d791cb9afc51457e799ee62f8bb845fd888fecf2
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 7%

---

# 一般架构{#general-architecture}

典型的Adobe Campaign解决方案部署包含以下组件：

* **个性化客户端环境**

  直观的图形界面，用户可以在其中交流和跟踪营销优惠、创建营销活动、查看和管理所有营销活动、项目和计划（包括电子邮件、工作流和登陆页面）、创建和管理客户档案以及创建受众。

* **开发环境**

  根据用户界面中定义的规则和工作流，通过选定的通信渠道（包括电子邮件、短信、推送通知、直邮、Web或社交）执行营销活动的服务器端软件。

* **数据库容器**

  Adobe Campaign云数据库基于关系数据库技术，将所有信息、活动组件、选件、工作流和活动结果存储在数据库容器中。

## 个性化客户端环境 {#client-env}

可以通过不同的方式访问应用程序：富客户端、瘦客户端或API集成。

![](../assets/do-not-localize/glass.png) [了解有关Campaign展示层的更多信息](../start/ac-components.md).

## 开发环境 {#dev-env}

Adobe Campaign是一个使用不同应用程序的平台，用于创建开放且可扩展的架构。 Adobe Campaign平台在灵活的应用层上编写，可轻松配置以满足您的业务需求。 分布式架构可确保线性系统可扩展性，从数千条报文扩展到数百万条报文。

有些Campaign模块会持续运行，而其他模块则偶尔会启动以执行管理任务（例如配置数据库连接）或运行重复任务（例如合并跟踪信息）。

有三种类型的Adobe Campaign模块：

* **多实例模块**：针对所有实例运行单个进程。 这适用于以下模块：web、syslogd、trackinglogd和watchdog。
* **单实例模块**：每个实例运行一个进程。 这适用于以下模块：mta、wfserver、inMail、sms和stat。
* **实用模块**：这些模块为偶尔运行以执行临时或重复操作（清理、配置、下载跟踪日志等）的模块。

主要流程为：

* **应用程序服务器** (nlserver web) — 此进程通过Web服务API (SOAP/HTTP + XML)公开所有Adobe Campaign功能。 此外，它可以动态生成用于基于HTML的访问（报表、Web窗体等）的网页。 为实现此目的，此过程包括一个Apache Tomcat JSP服务器。 这是Console连接的进程。

* **工作流引擎** (nlserver wfserver) — 此进程执行应用程序中定义的工作流进程。 它还处理定期执行的技术工作流，包括：

   * **跟踪**：恢复并整合跟踪日志，以便您可以从重定向服务器中检索日志并创建报告模块使用的聚合指示器。
   * **Cleanup**：清理数据库，清除旧记录，避免数据库呈指数级增长。
   * **计费**：发送平台的活动报告（数据库的大小、营销操作的数量等）。

* **投放服务器** (nlserver mta) - Adobe Campaign具有本机电子邮件广播功能。 此过程可充当SMTP邮件传输代理(MTA)。 它执行消息的“一对一”个性化并处理消息的物理投放。 它使用投放作业运行，并处理自动重试。 此外，启用跟踪后，会自动替换URL，以便它们指向重定向服务器。 此过程可处理自定义以及向第三方路由器自动发送短信、传真和直邮的功能。

* **重定向服务器** (nlserver webmdl) — 对于电子邮件，Adobe Campaign会自动处理打开和点击跟踪（还可能在网站级别进行事务跟踪）。 要实现此目的，将重写电子邮件中纳入的URL，以便指向此模块，该模块会注册Internet用户的传递，然后再将用户重定向到所需的URL。

  为了保证最高可用性，此过程完全独立于数据库：其他服务器进程仅使用SOAP调用(HTTP、HTTP(S)和XML)与其通信。 从技术上讲，此功能是在HTTP服务器的扩展模块（IIS中的ISAPI扩展或DSO Apache模块等）中实现的 和仅在Windows中可用。

其他更技术性的流程也可使用：

* **管理退回电子邮件** (nlserver inMail) — 此进程允许您从配置为接收在投放失败时返回的退回邮件的邮箱自动选取电子邮件。 然后，这些邮件将进行基于规则的处理，以确定未投放的原因（未知收件人、超出配额等） 和更新数据库中的投放状态。 所有这些操作都是完全自动且已预配置的。

* **短信投放状态** (nlserver sms) — 此过程会轮询SMS路由器以收集进度状态并更新数据库。

* **正在写入日志消息** (nlserver syslogd) — 此技术进程捕获其他进程生成的日志消息和跟踪，并将它们写入硬盘。 这样一来，在出现问题时就可以获得充分的信息进行诊断。

* **写入跟踪日志** (nlserver trackinglogd) — 此过程将重定向进程生成的跟踪日志保存到磁盘。

* **编写入站事件** (nlserver interactiond) — 此过程确保在交互的框架内将入站事件记录到磁盘。

* **监控模块** (nlserver watchdog) — 此技术进程充当生成其他进程的主进程。 它还监控这些服务器，并在发生事件时自动重新启动它们，从而保持最长的系统正常运行时间。

* **统计服务器** (nlserver stat) — 此进程维护有关连接数、每个邮件服务器发送的邮件数、邮件发送目标及其限制（最大同时连接数、每小时邮件数/和/或连接数）的统计数据。 它还允许您联合多个实例或计算机（如果它们共享相同的公共IP地址）。


## 数据库容器 {#db-containers}

Adobe Campaign云数据库依赖于 [!DNL Snowflake] ，其中包含功能数据（用户档案、订阅、内容等）、技术数据（投放作业和日志、跟踪日志等） 和解决方案的工作数据（购买、商机），以及所有Adobe Campaign组件与数据库通信以执行其特定任务。

您可以使用预定义的数据库和架构部署Adobe Campaign，如果需要，可以扩展此预定义的环境。 Adobe Campaign通过SQL调用访问数据集市中的所有数据。 Adobe Campaign还提供了提取转换和加载(ETL)工具的完整补充，用于执行数据导入和导出到系统中的数据。

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>通过使用 **Campaign 托管云服务**，您的环境和初始配置已由 Adobe 根据您的许可协议条款进行了设置。您不可修改已安装的内置软件包、内置模式或报告。
>
>如果您需要使用 Campaign 加载项或尚未为您配置的特定功能，那么您必须联系 **Adobe 客户关怀**&#x200B;团队。

## 数据库存储 {#db-storage}

总存储容量在主数据库和Snowflake仓库之间分配。 存储数据的位置应在实施或升级时确定，具体取决于客户特定的用例。

了解如何在中监测数据库使用情况 [Campaign控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring.html){target="_blank"}.