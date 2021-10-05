---
title: Campaign v8 已知限制
description: 已知限制
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: ht
source-wordcount: '176'
ht-degree: 100%

---

# 已知限制

已知限制指明了在这款产品中不受支持的，或是不能正确地与此版本产品交互操作的功能、架构或流程。请仔细查看这些限制。

Adobe Campaign v8 存在以下限制：

* Adobe Campaign v8 不适用于内部部署/混合部署 - 仅作为一项 Adobe 托管云服务发布。
* 现有客户无法从现有 Adobe Campaign 环境迁移到 Adobe Campaign v8
* 无双向数据复制：仅能从 Campaign 本地数据库复制到云数据库
* [此部分](capability-matrix.md#gs-unavailable-features)列出的功能在当前 Campaign v8 内部版本中不可用
* 用户界面中仍显示某些不可用或已删除的功能
* 订阅（选择加入）和退订（选择退出）机制以及移动设备注册是异步流程。请求是每小时通过特定的技术工作流处理的。[了解详情](../config/replication.md#tech-wf)
* 重复项需要由最终用户手动处理。[了解详情](../dev/keys.md)
* Adobe Campaign v8 不支持 API 和 Web 应用程序的扩展吞吐量。 如有特定需求，请联系 Adobe 获取指导。
