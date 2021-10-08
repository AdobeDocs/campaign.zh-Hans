---
title: 实施准则
description: 了解如何实施 Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: eb8ad88ffd9dbaaf1f9ace2e88ba4486711bc72d
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 95%

---

# Campaign 实施准则

在本节中，您将学习如何根据公司的要求调整 Adobe Campaign。请遵循以下准则来安排和组织实施。

1. **确定设置**：授予访问权限、共享 Client Console、配置渠道（电子邮件、推送、短信）
1. **准备环境**：导入用户档案、创建受众、设计工作流和活动模板、创建类型规则
1. **自定义实例**：创建新数据字段，添加表格/模式
1. **扩展部署**：连接到 Adobe 解决方案、其他产品和系统 - 连接器、多解决方案设置

>[!CAUTION]
>
>对于&#x200B;**Campaign托管Cloud Services**，您的环境和初始配置已由Adobe根据您的许可协议条款进行设置。 您不可修改已安装的内置软件包、内置模式或报告。
>
>如果您需要使用 Campaign 加载项或尚未为您配置的特定功能，那么您必须联系 **Adobe 客户关怀**&#x200B;团队。

## 开始前

本节包含有关隐私和安全性的重要信息，在开始实际实施之前需要查看并考虑这些信息。

### 隐私

Adobe Campaign 提供的流程和设置可帮助您在使用 Campaign 时遵守适用的数据隐私法律并适应收件人的偏好。您可以管理：

* **数据获取**：通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并管理收件人的同意至关重要。请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hans#data-acquisition)以了解详情

* **用户同意和数据保留**：请参阅 [Campaign Classic 隐私文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hans#consent)以了解如何获得用户同意、设置双重选择加入订阅机制、简化选择退出并配置数据保留

* **隐私和数据保护法规**：请参阅 [Campaign Classic 隐私文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=zh-Hans){target=&quot;_blank&quot;}，了解有关欧盟《通用数据保护条例》(GDPR)、《加州消费者隐私法案》(CCPA) 和其他国际隐私要求的信息，以及这些法规对您的组织和 Adobe Campaign 有何影响。

### 安全性

在 [Campaign 安全性检查表](../config/security.md)中了解 Adobe Campaign 的安全准则和原则。

## 确定 Campaign 设置

### 添加用户和授予权限

您可以手动将用户添加到Campaign并将其与组关联，并与角色层次结构保持一致。 随后，用户将能够登录并获取适合他们的数据和权限。

![](../assets/do-not-localize/book.png) 请参阅[本节](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=zh-Hans#getting-started)了解如何将用户添加到 Adobe Campaign。

### 安装 Campaign Client Console

应用程序的主要用户界面是一个富客户端，换句话说，是一个仅用标准互联网协议（SOAP、HTTP 等）与 Adobe Campaign 应用程序服务器通信的本机应用程序 (Windows)。Adobe Campaign Client Console 具有出色的用户友好性，可帮助提升工作效率，使用的带宽非常少（通过使用本地缓存），并且易于部署。此 Console 可以从互联网浏览器部署，可以自动更新，并且不需要任何特定的网络配置，因为它只生成 HTTP(S) 流量。

![](../assets/do-not-localize/glass.png) [了解关于 Campaign 客户端控制台的更多信息](connect.md)。

## 准备环境

在开始发送消息和创建营销活动之前，您需要：

1. 导入用户档案和创建受众

   Campaign 可帮助您将联系人添加到云数据库。您可以加载文件、计划和自动更新多个联系人，在网站上收集数据，或直接在收件人表格中输入用户档案信息。

   ![](../assets/do-not-localize/glass.png) [了解如何导入用户档案](import.md)。

   受众会分组到列表中，并且可以通过工作流创建。 然后可以在跨渠道投放中定位他们。

   ![](../assets/do-not-localize/glass.png) [了解如何定义受众](audiences.md)。

1. 创建模板

   活动、投放、任务或工作流都以存储着关键设置和功能的模板为基础。我们为每个组件提供了一个内置模板，但尚未为它们定义具体配置。您需要配置和调整模板以满足您的需求，并向最终用户提供这些模板。

   ![](../assets/do-not-localize/book.png) [了解有关电子邮件模板的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=zh-Hans){target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png)请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=zh-Hans#orchestrating-campaigns){target=&quot;_blank&quot;}以了解如何使用活动模板

   ![](../assets/do-not-localize/book.png) 了解如何在 [Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=zh-Hans#workflow-templates){target=&quot;_blank&quot;}中配置工作流程模板

1. 配置类型规则

   利用 Campaign 类型规则来筛选、控制和监测投放发送。例如，疲劳规则可控制消息传递的频率和数量，以避免对收件人过度宣传。实施后，类型规则就会在投放中引用。

   ![](../assets/do-not-localize/book.png) 在 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=zh-Hans#orchestrating-campaigns){target=&quot;_blank&quot;}中了解有关分类和疲劳管理的更多信息

1. 熟悉 Campaign 内置数据模型

   Adobe Campaign 提供了预定义的数据模型。为了实施和自定义环境，您需要熟悉 Adobe Campaign 数据模型的内置表格以及它们彼此的关系。

   ![](../assets/do-not-localize/glass.png) [了解关于 Campaign 数据模型的更多信息](../dev/datamodel.md)。

## 自定义实例

您可以自定义许多不同的 Campaign 区域和功能。我们的大多数客户都会自定义三项内容：

1. **表格和模式**

   Adobe Campaign 提供用来识别数据的常用模式，例如：收件人、投放日志、订阅等。

   ![](../assets/do-not-localize/glass.png) 请参阅本节以了解关于 [Campaign 内置数据模型](../dev/datamodel.md)的更多信息。

   ![](../assets/do-not-localize/glass.png)您可以扩展现有模式或从头开始创建新模式。请参阅[此页面](../dev/customize.md)以了解详情。

1. **仪表板和列表**

   您可以轻松配置列表，添加和删除字段以及自定义列。

   ![](../assets/do-not-localize/glass.png)请参阅[此页面](../dev/customize.md#gs-lists-and-filters)以了解如何管理 Campaign 中的过滤器和列表。

   您还可以创建新仪表板，以根据您的需要显示 Campaign 数据。

   ![](../assets/do-not-localize/glass.png)请参阅[此页面](../dev/customize.md#gs-custom-dashboards)以了解详情。

1. **报告**

   Campaign 提供一套关于投放监测、URL 和点击流、跟踪、可投放性指标等的内置报告。

   除了内置的报告，Adobe Campaign 还可用于在不同的上下文中生成各种报告，以满足不同的需求。本文档详细介绍了使用原则和实施模式。

   ![](../assets/do-not-localize/glass.png)在[此页面](reporting.md)中了解关于 Campaign 报告功能的更多信息。


## 设置活动自动化

要跨多个渠道编排复杂的营销活动，以便向不同受众进行宣传，请利用 Campaign 自动化功能。

* 工作流：管理流程和数据

* 订阅和登陆页面

* 类型规则：疲劳与控制管理

## 扩展您的部署

### 实施多重解决方案

如果您使用其他 Adobe 解决方案，您可以将它们连接到 Campaign 环境并结合使用。

* Campaign - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Experience Cloud Triggers
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager / People core service
* Campaign - Asset
* Campaign - Analytics Data connectors


您还可以使用单点登录 (SSO) 连接到 Campaign。请参阅[此页面](connect.md)以了解详情。

![](../assets/do-not-localize/glass.png) 有关能够与 Adobe Campaign 集成的 Adobe 解决方案的完整列表，请参阅[此页面](../connect/integration.md)。

### 连接器

将 Campaign 与第三方系统连接起来，以结合大量功能并实现流程自动化。

![](../assets/do-not-localize/glass.png) 在[本节](../connect/integration.md)中了解关于可用连接器的更多信息。

**将您的 CRM 连接到 Campaign**

您可以将 Adobe Campaign 平台连接到您的 CRM 第三方系统并同步数据：联系人、帐户、购买等。

![](../assets/do-not-localize/glass.png) 请参阅[本节](../connect/integration.md#gs-crm-connectors)以了解如何将您的 CRM 系统连接到 Campaign

**连接到外部数据库**

您可以通过联合数据访问 (FDA) 模块将 Campaign 云数据库连接到外部系统。

![](../assets/do-not-localize/glass.png) 请参阅[本节](../connect/integration.md#gs-fda)，了解如何配置 Campaign FDA 模块以定义访问参数
