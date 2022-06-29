---
title: Campaign v8护栏
description: Campaign v8护栏
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: cda523168525c24ec1c976850bc336f273276ac9
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 35%

---

# 产品护栏{#guardrails}

授权、产品限制和性能护栏列在 [Adobe Campaign Managed Cloud Services产品描述页面](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}。

在下面，您将看到使用 [!DNL Adobe Campaign].

护栏和限制可标识本产品版本不支持或无法与其正确交互的功能、架构或流程。 请仔细查看这些限制。

* Adobe Campaign v8不适用于内部部署/混合部署 — 仅作为Adobe管理的Cloud Service发布
* 现有客户无法从现有 Adobe Campaign 环境迁移到 Adobe Campaign v8
* 在 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，则不提供双向数据复制：复制仅从Campaign本地数据库到云数据库
* [此部分](v7-to-v8.md#gs-unavailable-features)列出的功能在当前 Campaign v8 内部版本中不可用
* 用户界面中仍显示某些不可用或已删除的功能
* 在 [企业(FFDA)部署](../architecture/enterprise-deployment.md)、订阅（选择加入）和退订（选择退出）机制，以及移动设备注册是异步流程。 请求是每小时通过特定的技术工作流处理的。[了解详情](../architecture/replication.md#tech-wf)
* 重复项需要由最终用户手动处理。[了解详情](../architecture/keys.md)
* Adobe Campaign v8不支持API和Web应用程序的扩展吞吐量 — 如果需要，请联系Adobe以获取指导
* Adobe Campaign Campaign优化模块在压力分类规则中未考虑计划投放。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=zh-Hans#setting-the-period) {target=&quot;_blank&quot;} 以了解详情。