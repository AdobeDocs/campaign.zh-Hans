---
solution: Campaign Classic
product: campaign
title: 活动 v8的新增功能
description: 了解更多关键功能
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
translation-type: tm+mt
source-git-commit: c3eaaecd33c70be0b8c7e9e69a78aa43cf5d18b8
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---

# Adobe Campaign v8有哪些新增功能？{#ac-gs-what-is-new}

Adobe Campaign v8提供了重要的基础架构、安全性、交付性和监控增强。 通过利用[!DNL Snowflake](一种云用户档案库技术),Adobe Campaign大幅提高了其规模和速度，并能够管理更多客户，以及更高的投放率和每小时交易。

主要功能包括：

* **快速扩展**。Adobe Campaign v8利用Cloud Database Manager，使查询的速度提高了200倍，扩展了PB级，每小时消息数增加，事务性消息每小时消息数达20M或1.5M/小时，并管理了多达200M的活动用户档案，可能达到1B。

* **连接Adobe Experience Platform**。Adobe Campaign v8支持Adobe Experience Platform/RT-CDP的数据连接器、统一的客户用户档案以及与Journey Orchestration的本机集成。 这些投资将优化Adobe Campaign客户体验并释放新的使用案例，如向活动添加个性化实时客户旅程的能力。

* **托管Cloud Services**。Adobe Campaign v8是一款一流的受管Cloud Services，可提供主动式监督、及时警报和服务治理。 营销人员的价值在于更灵活、可扩展的跨渠道活动管理。

## 缩放

活动 v8在流程的任何步骤(从定位到最终报告)中都实现了端到端的缩放：

* 扩展可处理的数据量（直到8 TB）
* 扩展查询的性能，以实现细分和定位，同时提高数据摄取和输出
* 将投放准备范围（从小时缩小到分钟）
同时简化数据管理

## 简化和性能提高

活动 v8带有&#x200B;**完全联合数据访问**(联合数据访问)的概念：现在，所有数据都位于云数据库上的远程位置。

使用这一新架构，活动 v8简化了数据管理:云数据库上不需要索引。 您只需创建表、复制数据即可进行开始。

[!DNL Snowflake] 是活动 Cloud Database，它将为您带来速度和耐力：系统活动峰值没有过载。

云数据库技术不需要进行特定的维护来保证性能级别。

## 综合生态系统

您可以将活动与一组功能强大的Adobe解决方案集成，例如：Adobe Analytics、Workfront、Journey Orchestration、实时CDP等。

您还可以配置历程AI的预测发送时间优化和预测参与评分，并提高打开率、点击量和收入。

：灯泡：[了解有关活动集成的更多信息](../connect/integration.md)

