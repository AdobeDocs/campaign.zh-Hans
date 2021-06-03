---
product: Adobe Campaign
title: Campaign v8已知限制
description: 已知限制
feature: 概述
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 3%

---

# 已知限制

已知限制可识别此产品版本不支持或无法与其正确互操作的功能、架构或进程。 请仔细查看这些限制。

对于Adobe Campaign v8，存在以下限制：

* Adobe Campaign v8不适用于内部部署/混合部署 — 仅作为Adobe管理的Cloud Service发布。
* 现有客户无法从现有Adobe Campaign环境迁移到Adobe Campaign v8
* 无双向数据复制：复制仅从Campaign本地数据库到云数据库
* 此部分](capability-matrix.md#gs-unavailable-features)中列出的[功能在当前Campaign v8内部版本中不可用
* 用户界面中仍显示某些不可用或已删除的功能
* 订阅（选择加入）和退订（选择退出）机制，以及移动设备注册是异步流程。 请求每小时通过特定的技术工作流进行处理。 [了解详情](../config/replication.md#tech-wf)
* 重复项需要由最终用户手动处理。 [了解详情](../dev/keys.md)
