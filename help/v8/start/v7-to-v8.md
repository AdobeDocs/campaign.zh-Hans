---
title: 从 Campaign Classic v7 过渡到 Campaign v8
description: 了解 Campaign Classic v7 和 Campaign v8 之间的差异。
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 76%

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

Adobe Campaign Managed Cloud Services 提供了可用于进行跨渠道客户体验设计的云服务平台，并为可视化的活动编排、实时互动管理和跨渠道执行提供了环境。要了解有关Campaign托管Cloud Service的更多信息，请参阅 [产品描述页面](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

这一新产品将同类最佳服务与主动监督和及时发送警报的功能融合在一起，将重心放在三个方面：

* **云敏捷性** — 通过 Adobe 实现自动化，提供经过优化、标准化的云部署，以实现可预测性更高的性能、更高的敏捷性和更高的自助服务效率。
* **服务体验** — 主动监测可用性、容量和性能及响应，从而防止出现中断、更快地解决事件，并定期审查服务以持续改进。
* **深入的 Campaign 专业知识** — 客户工程专家团队提供十分亲切的服务，可满足功能、技术或可投放性需求，降低部署风险，并改进变更管理。

作为之前的 [!DNL Campaign Classic] 用户，请注意，v7 的大多数功能[!DNL Campaign Classic]都可以在 [!DNL Campaign] v8 中使用，但[本节](#gs-removed)中所列的一小部分功能除外。

>新的云架构使Campaign能够简化流程、降低成本、管理风险并提高数据安全性。 您的 Campaign v8 环境附带为您预配置的专用虚拟私有云 (VPC)。


## 混合架构 {#hybrid-archi}

Campaign v8依赖于 **混合架构**. 请注意，如果从Campaign Classicv7进行过渡，所有投放都将通过中间源服务器。

因此：

* 内部路由为 **不可能** Campaign v8中，并且已相应地禁用外部帐户，
* 投放状态不会立即更新 — 在营销实例上运行一个技术流程，用于及时更新投放状态。


了解有关在从v7过渡时发送事务性消息校样的更多信息 [此页面](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] 和 [!DNL Snowflake] {#ac-gs-snowflake}

在 [企业(FFDA)部署](../architecture/enterprise-deployment.md)， [!DNL Adobe Campaign] v8可与两个数据库配合使用：本地 [!DNL Campaign] 数据库用于用户界面实时消息传递和统一查询，并通过API进行编写，以及建立一个云 [!DNL Snowflake] 数据库，用于活动执行、批量查询和工作流执行。

Campaign v8 企业版引入了&#x200B;**完全联合数据访问** (FFDA) 概念：所有数据现在都位于云数据库上的远程位置。凭借这种新架构，Campaign v8 企业版 (FFDA) 部署简化了数据管理：云数据库上不需要索引。您只需创建表格、复制数据即可开始。云数据库技术无需特定的维护来保证性能级别。

了解有关 [!DNL Campaign] 中的v8架构 [此页面](../architecture/architecture.md).


## 使用 Adobe ID 连接到 Campaign{#adobe-id}

Campaign 用户仅可通过其 Adobe ID 进行连接。可使用同一个 Adobe ID 来管理与单个帐户关联的所有 Adobe 计划和产品，适合所有 Adobe Experience Cloud 解决方案。

了解如何连接到 [!DNL Campaign] 在 [此页面](connect.md).

## 使用多维数据集分析数据{#adobe-reporting}

使用 Marketing Analytics 模块来分析和测量数据，计算统计数据，简化和优化报告创建与计算。此外，创建报告并构建目标群体：确定群体后，会将它们存储于可在 Adobe Campaign 中（定位、分段等）使用的列表中。

与 Campaign Classic v7 相比，Adobe Campaign v8 的多维数据集报告已得到优化，并提供了更好的扩展功能。在该特定部署模型中，以前对多维数据集的限制在 Campaign v8 中不适用。请在[此部分](../../v8/reporting/gs-cubes.md)中了解有关多维数据集的更多信息。

## 不可用功能{#gs-unavailable-features}

请注意，某些功能在 Campaign 的[企业 (FFDA) 部署](../architecture/enterprise-deployment.md)的环境下不可用，例如：

* 营销资源管理
* 优惠券
* Web 跟踪
* 调查

## 不支持的功能{#gs-removed}

Campaign v8 不再支持某些 Campaign Classic v7 曾支持的功能，例如：

* 通过 Facebook 进行社交媒体营销
* ACS 连接器（高级服务）
* 与 LDAP 集成
* 用户/密码登录
* 混合/内部部署模型


>[!NOTE]
>
>用户界面中仍会显示某些不可用或不支持的功能。
