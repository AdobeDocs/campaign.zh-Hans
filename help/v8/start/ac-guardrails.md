---
title: Campaign v8 护栏
description: Campaign v8 护栏
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 631c4986d24daeff870412566318adb170ce040f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 77%

---

# 产品护栏{#guardrails}

[Adobe Campaign Managed Cloud Services产品说明页面](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}列出了授权、产品限制和性能护栏。

下文中介绍了使用 [!DNL Adobe Campaign] 时的额外护栏和限制。

护栏和限制指明了在这个版本的产品中不受支持的，或是不能正确地与此版本产品交互操作的功能、架构或流程。请仔细查看这些限制。

* Adobe Campaign v8 不适用于内部部署/混合部署 - 仅作为一项 Adobe 托管云服务发布
* 现有客户无法自动迁移到 Adobe Campaign v8
* 采用[企业版 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)时，不提供双向数据复制：仅能从 Campaign 本地数据库复制到云数据库
* [此部分](v7-to-v8.md#gs-unavailable-features)列出的功能在当前 Campaign v8 内部版本中不可用
* 用户界面中仍显示某些不可用或已删除的功能
* 采用[企业版 (FFDA) 部署](../architecture/enterprise-deployment.md)时，订阅（选择启用）和退订（选择禁用）机制以及移动设备注册是异步流程。请求是每小时通过特定的技术工作流处理的。[了解详情](../architecture/replication.md#tech-wf)
* 在[企业(FFDA)部署](../architecture/enterprise-deployment.md)的上下文中，重复项需要由最终用户手动处理。 [了解详情](../architecture/keys.md)
* Adobe Campaign v8 不支持 API 和 Web 应用程序的扩展吞吐量 - 如有特定需求，请联系 Adobe 以获取指导
* 在[企业(FFDA)部署](../architecture/enterprise-deployment.md)的上下文中，Adobe Campaign活动优化模块不考虑压力类型规则中的计划投放。 请参阅[此页面](../../automation/campaign-opt/pressure-rules.md)以了解详情