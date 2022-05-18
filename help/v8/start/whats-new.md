---
title: Campaign v8 新增功能
description: 探索 Campaign v8 关键功能
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 30%

---

# Adobe Campaign v8 有哪些新增功能？ {#ac-gs-what-is-new}

Adobe Campaign v8专为需要一流的云解决方案以实现企业规模跨渠道营销活动管理的跨渠道营销人员而设计。 它提供了强大的ETL和数据管理功能，以帮助策划和策划完美的营销活动。 其编排引擎提供丰富的多接触点营销计划，其核心重点是基于批处理的驱动历程。 它还与可扩展的实时消息传送服务器相配对，该服务器使营销团队能够根据来自任何IT系统的包含所有内容的有效负载发送预定义的消息，以便进行密码重置、订单确认、电子收据等操作。

Adobe Campaign v8 在基础架构、安全性、可投放性和监测方面有着显著改进。

![](assets/home-page.png)

## 重要功能{#key-capabilities}

关键功能包括：

* **中央工作流管理**. 从创建区段、准备消息到投放，提高营销活动各个方面的速度和规模。

   Adobe Campaign通过单个易用的界面，让您能够轻松地使渠道同步进行活动编排。 因此，您的在线渠道（如电子邮件、Web、移动设备和社交渠道）与您的离线渠道（包括直邮、呼叫中心、店内等）相匹配。 它使您能够在数字和传统渠道中为客户提供一致的情境式体验。 Adobe Campaign可简化向客户在任何渠道上可能采用的所有路径交付内容的过程。

   ![](../assets/do-not-localize/glass.png) [进一步了解Campaign工作流](../config/workflows.md)

* **个性化电子邮件营销**. 创建与上下文相关的个性化电子邮件，使其与客户的其他体验保持一致。

   借助Adobe Campaign，您可以让电子邮件变得更好、更个性化、更盈利。 电子邮件创建简单，交付方便。 Campaign v8让您能够灵活地设计、个性化、测试、优化和改进您发送的每条消息。

   ![](../assets/do-not-localize/glass.png) [进一步了解个性化功能](create-message.md)

* **客户数据管理**. 查看客户的全貌，以便快速创建企业级的个性化营销活动。

   Adobe Campaign可帮助您根据所有渠道中收集的数据构建客户用户档案。 通过此用户档案，您可以跨渠道编排活动。 通过连接所有营销渠道，您可以自定义每个客户将采用的对其有意义的方式的不同历程。

   ![](../assets/do-not-localize/glass.png) [了解有关客户数据管理的更多信息](audiences.md)

* **一流的营销活动管理**. Adobe Campaign v8为营销人员提供了一流的功能，可以跨渠道规划、启动和测量促销活动。

   这些功能包括提供客户单一视图的集成用户档案。 用于大规模构建营销活动受众的数据管理和分段。 跨渠道工作流管理，用于自动化多渠道和多波次营销活动。 集成电子邮件，减少对成本高昂的ESP的依赖。 报告和分析，以了解客户行为和促销活动效果。

   ![](../assets/do-not-localize/glass.png) [进一步了解营销活动管理](campaigns.md)


* **与Adobe Experience Platform的连接**. Adobe Campaign v8支持带有Real-Time CDP和Adobe Experience Platform的Data Connectors，因此组织可以利用实时统一的客户资料。

   此外，Adobe Campaign v8本身与实时历程编排功能集成，以便营销人员可以重复使用Adobe Campaign中相同的模板和交付功能，以便与客户实时互动。 这些投资将可以优化 Adobe Campaign 客户体验并解锁新的用例，如向活动添加个性化实时客户旅程的能力。

   您还可以通过旅程人工智能配置预测发送时间优化和预测参与度评分，并提高打开率、点击量和收入。

   ![](../assets/do-not-localize/glass.png) [了解关于 Campaign 集成的更多信息](../connect/integration.md)


* **托管式云服务**。Adobe Campaign v8可作为托管Cloud Service使用，提供主动预防性监督、及时警报和服务管理。

   Adobe管理Cloud Service为营销人员提供了更灵活、安全且可扩展的跨渠道活动管理解决方案，并且总体拥有成本较低。 新产品将服务与主动监督和及时警报相结合。

* **速度和规模**。Adobe Campaign现在可以利用云规模数据库技术来显着提高其规模和速度。

   [Campaign v8企业版](../architecture/enterprise-deployment.md) 将 **完全联合数据访问** (FFDA):现在，云数据库中的所有数据都是远程的。 通过此新产品，Campaign v8简化了数据管理：云数据库上不需要索引。 您只需创建表格、复制数据即可开始。[!DNL Snowflake]是 Campaign 云数据库，它将为您带来速度和耐用性上的提升：不会出现系统活动峰值过载的情况。云数据库技术无需特定的维护来保证性能级别。

   ![](../assets/do-not-localize/glass.png) [了解有关企业(FFDA)部署的更多信息](../architecture/enterprise-deployment.md)


>[!CAUTION]
>
>* Campaign v8是 **仅** 可作为托管Cloud Service使用，并且不能部署在内部部署或混合环境中。
>
>* 从现有 Campaign Classic v7 环境进行迁移的功能尚不可用。




## 自助式管理界面{#self-service-admin}

作为产品管理员，您可以通过 **Campaign 控制面板**&#x200B;管理每个 Campaign v8 实例的设置和使用情况。

通过直观的用户界面，管理员可以监控关键资产的使用情况、执行高级任务，如将 IP 地址添加到允许列表、SFTP 存储监控、密钥管理等。此自助式界面为您提供了更高的灵活性，并可帮助您：

* 无需联系 Adobe 支持团队，即可自行快速更改设置
* 根据不同的业务需求在不同时间配置设置
* 根据需要控制访问设置，从而增强安全性

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png)[了解有关 Campaign 控制面板的更多信息](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=zh-Hans){target=&quot;_blank&quot;}


