---
solution: Campaign v8
product: Adobe Campaign
title: 实施指南
description: 了解如何实施Campaign v8
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 2%

---

# Campaign实施指南

在本节中，您将学习如何根据公司要求调整Adobe Campaign。 请按照以下准则来构建和组织实施。

1. **定义设置**:授予访问权限、共享客户端控制台、配置渠道（电子邮件、推送、短信）
1. **准备环境**:导入用户档案，创建受众，设计工作流和营销活动模板，创建分类规则
1. **自定义您的实例**:创建新数据字段，添加表/模式
1. **扩展部署**:连接到Adobe解决方案、其他产品和系统 — 连接器、多解决方案设置

>[!CAUTION]
>
>对于&#x200B;**Campaign托管Cloud Services**，您的环境和初始配置已由Adobe根据您的许可协议条款进行设置。 您不允许修改已安装的内置软件包、内置架构或报告。
>
>如果您需要使用Campaign附加组件或尚未为您配置的特定功能，则必须联系&#x200B;**Adobe客户关怀**。

## 开始前

本节包含有关隐私和安全性的关键信息，在开始实际实施之前，需要对这些信息进行审查和考虑。

### 隐私

Adobe Campaign提供了一些流程和设置，允许您按照适用的数据隐私法和收件人的首选项来使用Campaign。 您可以管理：

* **数据获取**:Adobe Campaign允许您收集数据，包括个人和敏感信息。因此，您必须获得并管理收件人的同意。 在[Campaign Classicv7文档](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)中了解更多信息

* **用户同意和数据保留**:在Campaign Classic隐私文档中了解如何获取用户同意、设置双重选择加入订阅机制、促进选择退出并配置数据 [保留](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **隐私和数据保护法规**:请参阅 [Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) 隐私文档，以了解有关欧盟《通用数据保护条例》(GDPR)、《加州消费者隐私法案》(CCPA)和其他国际隐私要求以及这些法规对贵组织和Adobe Campaign有何影响的信息。

### 安全性

在[Campaign安全检查列表](../config/security.md)中了解Adobe Campaign的安全准则和原则。

## 定义营销活动设置

### 添加用户和授予权限

您可以手动将用户添加到Cammaign，并将其与组关联，并与角色层次结构保持一致。 然后，用户将能够登录并访问适合他们的数据和权限。

:arrow_upper_right:了解如何在[此部分](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started)中将用户添加到Adobe Campaign。

### 安装Campaign客户端控制台

应用程序的主用户界面是一个富客户端，换句话说，是一个仅与标准Internet协议（SOAP、HTTP等）通信的与Adobe Campaign应用程序服务器通信的本机应用程序(Windows)。 Adobe Campaign客户端控制台为工作效率提供了极好的用户友好性，使用极少的带宽（通过使用本地缓存），并且设计为易于部署。 此控制台可以从Internet浏览器部署，可以自动更新，并且不需要任何特定的网络配置，因为它只生成HTTP(S)流量。

：灯泡：[了解有关Campaign客户端控制台的更多信息](connect.md)。

## 准备环境

在开始发送消息和创建营销活动之前，您需要：

1. 导入用户档案并创建受众

   Campaign可帮助您将联系人添加到云数据库。 您可以加载文件、计划和自动进行多次联系人更新、在Web上收集数据或直接在收件人表中输入用户档案信息。

   ：灯泡：[了解如何导入用户档案](import.md)。

   受众将分组到列表中，并可通过工作流创建。 然后，可以在跨渠道投放中定位这些量度。

   ：灯泡：[了解如何定义受众](audiences.md)。

1. 创建模板

   营销活动、投放、作业或工作流都基于模板，模板可存储关键设置和功能。 为每个组件提供了内置模板，尚未为其定义特定配置。 您需要配置和调整模板以满足您的需求，并向最终用户提供模板。

   :arrow_upper_right:[了解有关电子邮件模板的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   :arrow_upper_right:了解如何在[本页](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)中使用营销活动模板

   :arrow_upper_right:了解如何在[此页面](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)中配置工作流模板

1. 配置分类规则

   利用Campaign分类规则过滤、控制和监控投放发送。 例如，疲劳规则控制消息传送的频率和数量，以避免收件人过度通信。 实施后，将在投放中引用分类规则。

   :arrow_upper_right:[了解有关分类和疲劳管理的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. 熟悉Campaign内置数据模型

   Adobe Campaign 提供了预定义的数据模型。要实施和自定义您的环境，您需要熟悉Adobe Campaign数据模型的内置表以及它们彼此的关系。

   ：灯泡：[了解有关Campaign数据模型的更多信息](../dev/datamodel.md)。

## 自定义实例

您可以自定义许多不同的Campaign区域和功能。 我们的大多数客户都会自定义以下三项：

1. **表和架构**

   Adobe Campaign提供了一些用于识别数据的通用架构，例如：收件人、投放日志、订阅等。

   ：灯泡：请参阅此部分，了解有关[Campaign内置数据模型](../dev/datamodel.md)的更多信息。

   ：灯泡：您可以扩展现有架构或从头开始创建新架构。 在[此页面](../dev/customize.md)中了解详情。

1. **功能板和列表**

   您可以轻松配置列表、添加和删除字段以及自定义列。

   ：灯泡：在[本页](../dev/customize.md#gs-lists-and-filters)中了解如何在Campaign中管理过滤器和列表。

   您还可以根据自己的需求创建新功能板以显示促销活动数据。

   ：灯泡：在[此页面](../dev/customize.md#gs-custom-dashboards)中了解详情。

1. **报告**

   Campaign提供了一组关于投放监控、URL和点击流、跟踪、投放能力指标等的内置报告。

   除了内置的报告，Adobe Campaign 还可用于在不同的上下文中生成各种报告，以满足不同的需求。本文详细介绍了使用原则和实施模式。

   ：灯泡：在[本页](reporting.md)中了解有关Campaign中报告功能的更多信息。


## 设置Campaign自动化

要跨多个渠道向不同受众编排复杂的营销活动，请利用Campaign自动化功能。

* 工作流：管理流程和数据

* 订阅和登陆页面

* 分类规则：疲劳和控制管理

## 扩展部署

### 多解决方案实施

如果您使用其他Adobe解决方案，则可以将它们连接到Campaign环境并结合各种功能。

* 营销活动 — Journey Orchestration
* Campaign - Real-time CDP
* 促销活动 — Experience Cloud触发器
* 营销活动 — Experience Manager
* 营销活动 — Target
* Campaign -Audience Manager/人员核心服务
* 营销活动 — 资产
* Campaign - Analytics Data Connectors


您还可以使用单点登录(SSO)连接到Campaign。 在[此页面](connect.md)中了解详情。

：灯泡：在本页](../connect/integration.md)中，了解可与Adobe Campaign [集成的Adobe解决方案的完整列表。

### 连接器

将Campaign与第三方系统连接起来，以组合大量功能并自动执行各个流程。

：灯泡：在[此部分](../connect/integration.md)中了解有关可用连接器的更多信息。

**将CRM连接到Campaign**

您可以将Adobe Campaign平台连接到CRM第三方系统并同步数据：联系人、帐户、购买等

：灯泡：在[此部分](../connect/integration.md#gs-crm-connectors)中了解如何将CRM系统连接到Campaign

**连接到外部数据库**

您可以通过联合数据访问(FDA)模块将Campaign Cloud数据库连接到外部系统。

：灯泡：了解如何配置Campaign FDA模块以在[此部分](../connect/integration.md#gs-fda)中定义访问参数
