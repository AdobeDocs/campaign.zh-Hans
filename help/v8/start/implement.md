---
solution: Campaign
product: Adobe Campaign
title: 实施指南
description: 了解如何实施活动 v8
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
translation-type: tm+mt
source-git-commit: 9b6190f48373b772a72d6c1ef1b7510ec41112be
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 2%

---

# 活动实施指南

在本节中，您将学习如何根据公司的要求调整Adobe Campaign。 请遵循以下准则来组织实施。

1. **定义设置**:授予访问权限、共享客户端控制台、配置渠道（电子邮件、推送、sms）
1. **准备环境**:导入用户档案、创建受众、设计工作流和活动模板、创建类型规则
1. **自定义实例**:创建新数据字段，添加表/模式
1. **扩展您的部署**:连接到Adobe解决方案、其他产品和系统 — 连接器、多解决方案设置

## 开始前

本节包含有关隐私和安全性的重要信息，在开始实际实施之前，需要审查并考虑这些信息。

### 隐私

Adobe Campaign附带流程和设置，允许您在遵守适用活动隐私法和收件人偏好的情况下使用Adobe。 您可以管理：

* **数据获取**:Adobe Campaign使您能够收集数据，包括个人和敏感信息。因此，您必须获得和管理收件人的同意。 了解有关[Campaign Classic文档](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)的更多信息

* **用户同意和数据保留**:了解如何获得用户同意、设置多次选择加入订阅机制、促进选择退出并在Campaign Classic隐私文档中配置数 [据保留](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **隐私和数据保护规定**:有关欧洲 [合并一](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) 般数据保护规定(GDPR)、加利福尼亚消费者隐私法(CCPA)和其他国际隐私要求的信息，以及这些规定对您的组织和Adobe Campaign有何影响，请参阅Campaign Classic隐私文档。

### 安全性

在[活动安全清单](../config/security.md)中学习安全指南和Adobe Campaign原则

## 定义活动设置

### 添加用户和授予权限

您可以手动将用户添加到营销活动，并将其与组关联，这与您的角色层次结构一致。 随后，用户将能够登录并访问适合他们的数据和权限。

:arrow_upper_right:了解如何在[本节](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started)中将用户添加到Adobe Campaign。

### 安装活动客户端控制台

应用程序的主用户界面是一个富客户端，换句话说，是一个仅与标准Internet协议（SOAP、HTTP等）通信的本机应用程序(Windows)。 Adobe Campaign Client Console为工作效率提供了极好的用户友好性，使用的带宽非常少（通过使用本地缓存），并且设计为易于部署。 此控制台可以从Internet浏览器部署，可以自动更新，并且不需要任何特定的网络配置，因为它只生成HTTP(S)通信。

：灯泡：[了解有关活动 Client Console](connect.md)的更多信息。

## 准备环境

在开始发送消息和创建营销活动之前，您需要：

1. 导入用户档案和创建受众

   活动可帮助您将联系人添加到云数据库。 您可以加载文件、计划和自动进行多个联系人更新、在Web上收集数据或直接在收件人表中输入用户档案信息。

   ：灯泡：[了解如何导入用户档案](import.md)。

   受众将分组为列表，并可通过工作流创建。 然后，它们可以在跨渠道投放中定位。

   ：灯泡：[了解如何定义受众](audiences.md)。

1. 创建模板

   活动、投放、作业或工作流都基于存储关键设置和功能的模板。 将为每个组件提供一个内置模板，尚未为其定义特定配置。 您需要配置和调整模板以满足您的需求，并向最终用户提供这些模板。

   :arrow_upper_right:[了解有关电子邮件模板的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   :arrow_upper_right:了解如何在[此页面](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)中使用活动模板

   :arrow_upper_right:了解如何在[此页面](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)中配置工作流模板

1. 配置类型规则

   利用活动类型规则来过滤、控制和监视投放发送。 例如，疲劳规则控制消息传递的频率和数量，以避免收件人过度请求。 实施后，类型规则在投放中引用。

   :arrow_upper_right:[了解有关类型和疲劳管理的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. 熟悉活动内置的数据模型

   Adobe Campaign 提供了预定义的数据模型。要实施和自定义环境，您需要熟悉Adobe Campaign数据模型的内置表以及它们彼此的关系。

   ：灯泡：[了解有关活动数据模型的更多信息](../dev/datamodel.md)。

## 自定义实例

您可以自定义许多不同的活动区域和功能。 我们的大多数客户都定制了三件事：

1. **表和模式**

   Adobe Campaign附带常见模式来识别数据，例如：收件人、投放日志、订阅等。

   ：灯泡：请参阅本节以了解有关[活动内置数据模型](../dev/datamodel.md)的更多信息。

   ：灯泡：您可以扩展现有模式或从头开始创建新模式。 请阅读[本页](../dev/customize.md)了解更多信息。

1. **仪表板和列表**

   您可以轻松配置列表、添加和删除字段以及自定义列。

   ：灯泡：了解如何在[本页](../dev/customize.md#gs-lists-and-filters)中管理活动中的过滤器和列表。

   您还可以创建新仪表板，以根据您的需要显示活动数据。

   ：灯泡：请阅读[本页](../dev/customize.md#gs-custom-dashboards)了解更多信息。

1. **报告**

   活动提供一组关于投放监视、URL和点击流、跟踪、交付性指示器等的内置报告。

   除了内置的报告，Adobe Campaign 还可用于在不同的上下文中生成各种报告，以满足不同的需求。本文档详细介绍了使用原则和实施模式。

   ：灯泡：了解有关[本页](reporting.md)中活动中报告功能的更多信息。


## 设置活动自动化

要跨多个渠道将复杂的营销活动编排到不同受众，请利用活动自动化功能。

* 工作流:管理流程和数据

* 订阅和登陆页

* 类型规则:疲劳与控制管理

## 扩展您的部署

### 多解决方案实施

如果您使用其他Adobe解决方案，您可以将其连接到活动环境并结合功能。

* 活动-Journey Orchestration
* 活动 — 实时CDP
* 活动-Experience Cloud触发器
* 活动-Experience Manager
* 活动-目标
* 活动-Audience Manager/人员核心服务
* 活动 — 资产
* 活动- Analytics Data connectors


您还可以使用单点登录(SSO)连接到活动。 请阅读[本页](connect.md)了解更多信息。

：灯泡：了解可与本页](../connect/integration.md)中的Adobe Campaign [集成的Adobe解决方案的完整列表。

### 连接器

将活动与第三方系统连接起来，结合大量功能并实现流程自动化。

：灯泡：了解有关[本节](../connect/integration.md)中可用连接器的更多信息。

**将您的CRM连接到活动**

您可以将Adobe Campaign平台连接到CRM第三方系统并同步数据：联系人、帐户、购买等。

：灯泡：了解如何将您的CRM系统连接到[本部分](../connect/integration.md#gs-crm-connectors)中的活动

**连接到外部数据库**

您可以通过活动(联合数据访问)模块将联合数据访问 Cloud数据库连接到外部系统。

：灯泡：了解如何配置活动联合数据访问模块以在[本节](../connect/integration.md#gs-fda)中定义访问参数
