---
title: Campaign v8 新增功能
description: 探索Adobe Campaign v8中的关键功能
feature: Overview
role: User
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 5c4bbbd06eb7bf6dc9ada1d08c3fc696e88ee760
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 91%

---

# Adobe Campaign v8关键功能 {#ac-gs-what-is-new}

Adobe Campaign v8 专为需要同类最佳云解决方案的跨渠道营销人员而设计，可帮助实现企业规模的跨渠道营销活动管理。它提供了强大的 ETL 和数据管理功能，以帮助制定和策划完美的营销活动。它的编排引擎提供丰富的多接触点营销计划，核心重点放在基于批处理驱动的历程。它还配有一个可扩展的实时消息服务器，使营销团队能够根据任何 IT 系统的总体有效负载发送预定义的消息，如密码重置、订单确认、电子收据等。

Adobe Campaign v8 在基础架构、安全性、可投放性和监测方面有着显著改进。

![](assets/home-page.png)

## 关键功能{#key-capabilities}

下面列出了关键功能。

### 中央工作流管理{#central-wf-mgt}

从创建区段、准备消息到投放，提高营销活动各个方面的速度和规模。

Adobe Campaign 提供了用于进行活动编排的简单易用的单个界面，让您能够轻松地使渠道保持同步。因此，在线渠道（如电子邮件、Web、移动设备和社交渠道）与离线渠道（包括直邮、呼叫中心、店内等）相匹配。它使您能够在数字和传统渠道中为客户提供一致的情境式体验。Adobe Campaign 使您可以通过任何渠道轻松将内容投放到客户可能选择的所有路径。

![](../assets/do-not-localize/glass.png) [了解关于活动工作流的更多信息](../config/workflows.md)

### 个性化电子邮件营销 {#perso-email-mkt}

创建上下文相关的个性化电子邮件，使它们提供的体验与客户的其他体验保持一致。

借助 Adobe Campaign，您可以制作质量更好、更加个性化且获益更高的电子邮件内容。电子邮件的创建步骤简单且可轻松投放。 Campaign v8 让您能够灵活地设计、个性化、测试并改进您发送的每条消息。

![](../assets/do-not-localize/glass.png) [了解关于个性化功能的更多信息](create-message.md)

### 客户数据管理 {#customer-data-mgt}

全面了解客户的情况，以便快速创建企业级的个性化营销活动。

Adobe Campaign 可帮助您根据在所有渠道中收集的数据构建客户档案。使用此用户档案，您可以跨渠道编排营销活动。通过连接所有营销渠道，您可以根据客户的具体需求对其所经过的不同历程进行自定义。

![](../assets/do-not-localize/glass.png) [了解有关客户数据管理的更多信息](audiences.md)

### 同类最佳的营销活动管理 {#best-in-campaign-mgt}

Adobe Campaign v8 为营销人员提供了同类最佳的功能，可用于跨渠道规划、启动和衡量营销活动。

丰富多样的功能中包含集成式用户档案，可提供有关客户的单一视图。用于大规模构建营销活动受众的数据管理和分段功能。跨渠道工作流管理功能，用于实现多渠道和多波次营销活动的自动化。集成电子邮件，减少对成本高昂的 ESP 的依赖。用于了解客户行为和营销活动效果的报告和分析功能。

![](../assets/do-not-localize/glass.png) [了解关于营销活动管理的更多信息](campaigns.md)


### 连接至Adobe Experience Platform {#connection-to-aep}

Adobe Campaign v8 支持 Real-Time CDP 和 Adobe Experience Platform 的 Data Connectors，因此组织可以利用实时一致的客户档案。

此外，Adobe Campaign v8 与 Journey Orchestration 功能原生集成，因此营销人员可以在 Adobe Campaign 中重复使用相同的模板和投放功能，以便与客户实时互动。这些投资将可以优化 Adobe Campaign 客户体验并解锁新的用例，如向活动添加个性化实时客户旅程的能力。

您还可以通过旅程人工智能配置预测发送时间优化和预测参与度评分，并提高打开率、点击量和收入。

![](../assets/do-not-localize/glass.png) [了解关于 Campaign 集成的更多信息](../connect/integration.md)


### Managed Cloud Services {#acms-desc}

Adobe Campaign v8 是一款托管式云服务，提供主动监督、及时发送警报和服务治理功能。

Adobe 托管式云服务以较低的总体拥有成本为营销人员提供更加灵活、安全且可扩展性更高的跨渠道营销活动管理解决方案。新产品将各种服务与主动监督和及时发送警报的功能相结合。

>[!NOTE]
>
>新的云架构使Campaign能够简化流程、降低成本、管理风险并提高数据安全性。 您的Campaign v8环境附带为您预配置的专用虚拟专用云(VPC)。

### 速度和规模 {#speed-scale}

Adobe Campaign 现在可以利用云规模数据库技术显著提升其规模和速度。

[Campaign v8 企业版](../architecture/enterprise-deployment.md)引入了&#x200B;**完全联合数据访问** (FFDA) 概念：所有数据现在都位于云数据库上的远程位置。凭借这种新模式，Campaign v8 简化了数据管理：云数据库上不需要索引。您只需创建表格、复制数据即可开始。[!DNL Snowflake] 是 Campaign 云数据库，它将为您带来速度和耐用性上的提升：不会出现系统活动峰值过载的情况。云数据库技术无需特定的维护来保证性能级别。

![](../assets/do-not-localize/glass.png) [了解关于企业 (FFDA) 部署的更多信息](../architecture/enterprise-deployment.md)

>[!CAUTION]
>
>* Campaign v8 **仅**&#x200B;作为托管式云服务提供，不能部署在内部部署或混合环境中。
>
>* 从现有 Campaign Classic v7 环境进行自动迁移的功能尚不可用。


## 自助式管理界面{#self-service-admin}

作为产品管理员，您可以通过 **Campaign 控制面板**&#x200B;管理每个 Campaign v8 实例的设置和使用情况。

通过直观的用户界面，管理员可以监控关键资产的使用情况、执行高级任务，如将 IP 地址添加到允许列表、SFTP 存储监控、密钥管理等。此自助式界面为您提供了更高的灵活性，并可帮助您：

* 无需联系 Adobe 支持团队，即可自行快速更改设置
* 根据不同的业务需求在不同时间配置设置
* 根据需要控制访问设置，从而增强安全性

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [了解关于Campaign控制面板的更多信息](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=zh-Hans){target="_blank"}


