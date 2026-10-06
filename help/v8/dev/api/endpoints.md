---
title: 端点
description: 了解有关API端点的更多信息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
TQID: 'https://experienceleague.adobe.com/1ajh28ZpUsuyTh-qHnto3GsH4J25WSsyK7TqTjlhHfg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 9%
---
# 端点 {#endpoints}

Adobe Campaign REST API的可用端点：

* **/profileAndServices**：与开箱即用的字段交互。 不能使用此端点访问扩展字段。
* **/profileAndServicesExt**：与在Profile或Services自定义资源扩展期间添加的自定义字段交互。 有关自定义资源的详细信息，请参阅[此部分](custom-resources.md)。
* **/&lt;transactionalAPI>**：与事务性消息API交互（事务性消息API端点的名称取决于您的实例配置）。 如需详细信息，请参阅[此小节](managing-transactional-messages.md)。
* **/工作流/执行**：与工作流交互。 如需详细信息，请参阅[此小节](controlling-a-workflow.md)。

默认情况下，**profileAndServices**&#x200B;和&#x200B;**profileAndServicesExt** API可用的主要资源包括：

* **/配置文件**：与Campaign数据库中的配置文件进行交互。 若要向服务添加配置文件，请使用&#x200B;**/服务**&#x200B;终结点。 有关Campaign中用户档案的详细信息，请参阅[Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/服务**：管理订阅服务。 有关Campaign中服务的详细信息，请参阅[Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>已扩展或创建的所有其他资源只能通过&#x200B;**ProfileAndServicesExt** API使用。 它们必须链接到&#x200B;**配置文件**&#x200B;资源才能访问。
