---
title: 从 Campaign Classic v7 过渡到 Campaign v8
description: 了解 Campaign Classic v7 和 Campaign v8 之间的差异
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: ht
source-wordcount: '636'
ht-degree: 100%

---

# 从 [!DNL Campaign Classic] v7 过渡到 [!DNL Campaign] v8{#gs-matrix}

作为之前的 [!DNL Campaign Classic] v7 用户，您与 [!DNL Adobe Campaign] 的交互方式不会发生任何重大的变化。除了 UI 和配置步骤中显现的小变化外，v8 中的大多数变化都不明显。

>[!AVAILABILITY]
>
>* 目前，Campaign v8 **仅**&#x200B;作为托管云服务提供，不能部署在内部部署或混合环境中。[了解详情](#cloud-services)
>
>* 从现有 Campaign Classic v7 环境进行自动迁移的功能尚不可用。



## Managed Cloud Services{#cloud-services}

Adobe Campaign v8 是以&#x200B;**托管云服务**&#x200B;的形式提供。

Adobe Campaign Managed Cloud Services 提供了可用于进行跨渠道客户体验设计的托管服务平台，并为可视化的营销活动编排、实时互动管理和跨渠道执行提供了环境。在[产品描述页面](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}中了解关于 Campaign Managed Cloud Services 的更多信息。

这一新产品将同类最佳服务与主动监督和及时发送警报的功能融合在一起，将重心放在三个方面：

* **云敏捷性** — 通过 Adobe 实现自动化，提供经过优化、标准化的云部署，以实现可预测性更高的性能、更高的敏捷性和更高的自助服务效率。
* **服务体验** — 主动监测可用性、容量和性能及响应，从而防止出现中断、更快地解决事件，并定期审查服务以持续改进。
* **深入的 Campaign 专业知识** — 客户工程专家团队提供十分亲切的服务，可满足功能、技术或可投放性需求，降低部署风险，并改进变更管理。

作为之前的 [!DNL Campaign Classic] 用户，请注意，v7 的大多数功能[!DNL Campaign Classic]都可以在 [!DNL Campaign] v8 中使用，但[本节](#gs-removed)中所列的一小部分功能除外。

>[!NOTE]
>
> Campaign v8 依赖于混合架构。请注意，如果从 Campaign Classic v7 进行过渡，所有投放都要经过中间源服务器。[了解详情](../architecture/architecture.md)
>
> 因此，内部路由在 Campaign v8 中&#x200B;**不受支持**，并且已相应地禁用外部帐户。


## [!DNL Campaign] 和 [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 适用于 [!DNL Snowflake]。

在其[企业版 (FFDA) 部署](../architecture/enterprise-deployment.md)中，[!DNL Adobe Campaign] v8 可与两个数据库配合使用：用于用户界面实时消息传递和统一查询、通过 API 写入的本地 [!DNL Campaign] 数据库，以及用于营销活动执行、批量查询和工作流执行的云端 [!DNL Snowflake] 数据库。

Campaign v8 企业版引入了&#x200B;**完全联合数据访问** (FFDA) 概念：所有数据现在都位于云数据库上的远程位置。凭借这种新架构，Campaign v8 企业版 (FFDA) 部署简化了数据管理：云数据库上不需要索引。您只需创建表格、复制数据即可开始。云数据库技术无需特定的维护来保证性能级别。

![](../assets/do-not-localize/glass.png)如需详细了解 [!DNL Campaign] v8 架构，请参阅[此页面](../architecture/architecture.md)。


## 使用 Adobe ID 连接到 Campaign{#adobe-id}

Campaign 用户仅可通过其 Adobe ID 进行连接。可使用同一个 Adobe ID 来管理与单个帐户关联的所有 Adobe 计划和产品，适合所有 Adobe Experience Cloud 解决方案。

![](../assets/do-not-localize/glass.png) 有关如何连接到 [!DNL Campaign]，请参阅[此页面](connect.md)。

## 使用多维数据集分析数据{#adobe-reporting}

使用 Marketing Analytics 模块来分析和测量数据，计算统计数据，简化和优化报告创建与计算。此外，创建报告并构建目标群体：确定群体后，会将它们存储于可在 Adobe Campaign 中（定位、分段等）使用的列表中。

与 Campaign Classic v7 相比，Adobe Campaign 多维数据集报告已得到优化，并提供了更好的扩展功能。之前存在的对“多维数据集”的限制在 Campaign v8 中不适用。

## 不可用功能{#gs-unavailable-features}

请注意，在此版本 Campaign 中未提供某些功能，例如：

* 营销资源管理
* 混合/内部部署模型


## 不支持的功能{#gs-removed}

为了与 Campaign v8 的新架构和部署模型保持一致，Campaign v8 不再支持某些 Campaign Classic v7 的旧功能，例如：

* 优惠券
* Web 跟踪
* 调查
* 社交媒体营销
* ACS 连接器（高级服务）
* 与 LDAP 集成
* 用户/密码登录

>[!NOTE]
>
>用户界面中仍会显示某些不可用或不支持的功能。
