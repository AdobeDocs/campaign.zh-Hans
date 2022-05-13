---
title: Campaign Classic v7 - Campaign v8 功能矩阵
description: 了解 Campaign Classic v7 和 Campaign v8 之间的差异
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 220ff4ff31e55aba085f47de67347e28bcb3e30d
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 40%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8 功能{#gs-matrix}

作为前身 [!DNL Campaign Classic] v7用户，您不应期望与之交互的方式出现任何重大中断 [!DNL Adobe Campaign]. 除了 UI 和配置步骤中显现的小变化外，v8 中的大多数变化都不明显。

Adobe Campaign v8可作为a **托管Cloud Service**. 这一新产品将同类最佳服务与主动监督和及时警报相结合，重点关注三个方面：

* **云敏捷性**  — 通过Adobe实现自动化，具有优化、标准化的云部署，以实现更可预测的性能、更高的敏捷性和更高的自助服务工作效率。
* **服务体验**  — 主动预防性可用性、容量和性能监控和响应，以防中断、更快地解决事件，并定期审查服务以持续改进。
* **深入的Campaign专业知识**  — 客户工程专家团队提供的高亲和度服务，可满足功能、技术或可交付性需求，降低部署风险，并改进变更管理。

作为前身 [!DNL Campaign Classic] 用户，请注意， [!DNL Campaign Classic] v7功能 [!DNL Campaign] v8，除其中一小组外，列在 [此部分](#gs-removed). 其他功能将在以后的版本中发布。[在本节中了解详情](#gs-unavailable-features)

>[!NOTE]
>
> Campaign v8依赖于混合架构。 如果您从Campaign Classicv7进行过渡，请注意，所有投放都经过中间源服务器。 [了解详情](../architecture/architecture.md)
>
> 因此，内部路由是 **不可能** 在Campaign v8中，并且外部帐户已相应禁用。


## [!DNL Campaign] 和 [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8适用于 [!DNL Snowflake]. 提供了两种部署模型。

![](../assets/do-not-localize/glass.png)如需详细了解[!DNL Campaign] v8 架构，请参阅[此页面](../architecture/architecture.md)。


## 使用Adobe ID连接到Campaign{#adobe-id}

Campaign 用户通过其 Adobe ID 进行连接。同一Adobe ID用于将所有Adobe计划和产品与单个帐户(适用于所有Adobe Experience Cloud解决方案)关联。

![](../assets/do-not-localize/glass.png) 有关如何连接到 [!DNL Campaign]，请参阅[此页面](connect.md)。

## 使用多维数据集分析数据{#adobe-reporting}

使用Marketing Analytics模块来分析和测量数据、计算统计数据、简化和优化报表创建和计算。 此外，创建报告并构建目标群体：识别后，这些区段会存储在可在Adobe Campaign中使用的列表（定位、分段等）中。

Adobe Campaign多维数据集报表经过优化，比Campaign Classicv7具有更好的扩展功能。 以前对多维数据集的限制在Campaign v8中不适用。

## 更改数据源 {#change-data-source}

Campaign v8 增添了一个定位工作流活动：**[!UICONTROL Change data source]**。

利用 **[!UICONTROL Change data source]** 活动，可更改工作流 **[!UICONTROL Working table]** 的数据源，以管理跨不同数据源（如 FDA、FFDA 和本地数据库）的数据。

![](../assets/do-not-localize/glass.png) 有关 **[!UICONTROL Change data source]** 活动的更多信息，请参阅[此页面](../config/workflows.md#change-data-source-activity)。

## 不可用功能{#gs-unavailable-features}

请注意，在此版本 Campaign 中未提供某些功能，例如：

* 营销资源管理
* 分布式营销
* 响应管理器
* 混合/内部部署模型

>[!CAUTION]
>
>* 目前，Campaign v8 **仅**&#x200B;作为托管云服务提供，不能部署在内部部署或混合环境中。
>
>* 从现有 Campaign Classic v7 环境进行迁移的功能尚不可用。
>
>* 如果您不确定部署模型或有任何问题，请联系您的Adobe帐户主管。


## 不支持的功能{#gs-removed}

为了与 Campaign v8 的新架构和部署模型保持一致，Campaign v8 不再支持某些 Campaign Classic v7 的旧功能，例如：

* 优惠券
* Web 跟踪
* 调查
* 社交媒体营销使用 Facebook
* ACS 连接器（高级服务）
* 与 LDAP 集成
* 用户/密码登录

>[!NOTE]
>
>用户界面中仍可看到某些不可用或不受支持的功能。
