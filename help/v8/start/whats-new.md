---
solution: Campaign v8
product: Adobe Campaign
title: Campaign v8的新增功能
description: 了解更多关键功能
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Adobe Campaign v8有哪些新增功能？{#ac-gs-what-is-new}

Adobe Campaign v8提供了显着的基础架构、安全性、可交付性和监控增强功能。 利用[[!DNL Snowflake]](https://www.snowflake.com/)云数据库技术，Adobe Campaign可以显着提高其规模和速度，并能够管理更多的客户档案，以及更高的每小时交付率和交易。

主要功能包括：

* **速度和规模**。Adobe Campaign v8利用Cloud Database Manager，导致查询性能提高200倍，可扩展多PB级，每小时增加消息数，事务型消息最多20M/小时或1.5M/小时，并管理多达200M的活动用户档案，可能达到1B。

* **与Adobe Experience Platform的连接**。Adobe Campaign v8支持带有Adobe Experience Platform/RT-CDP的Data Connectors、统一的客户资料，以及与Journey Orchestration的本机集成。 这些投资将优化Adobe Campaign客户体验，并释放新的用例，例如向促销活动添加个性化的实时客户历程的功能。

* **托管Cloud Services**。Adobe Campaign v8是一款同类最佳的托管Cloud Services，可提供主动预防性监督、及时警报和服务管理。 对营销人员而言，这是一种更灵活、更可扩展的跨渠道营销活动管理。

>[!CAUTION]
>
>目前，Campaign v8仅&#x200B;****&#x200B;可用作托管Cloud Service，不能部署在内部部署或混合环境中。
>
>从现有Campaign Classicv7环境进行迁移的功能尚不可用。


## 缩放

Campaign v8在从定位到最终报告的流程中的任何步骤都提供了端到端规模：

* 扩展您可以处理的数据量（直到8 TB）
* 扩展查询的性能以用于分段和定位，以及数据摄取和出口
* 将投放准备范围从小时扩展到分钟

## 简化和性能提高

Campaign v8引入了&#x200B;**完全联合数据访问**(FDA)的概念：现在，云数据库中的所有数据都是远程的。

使用此新架构，Campaign v8简化了数据管理：云数据库上不需要索引。 您只需创建表、复制数据即可开始。

[!DNL Snowflake] 是Campaign Cloud数据库，它将为您带来速度和耐力：系统活动峰值没有过载。

云数据库技术不需要进行具体的维护，就能保证性能级别。

## 综合生态系统

您可以将Campaign与一组功能强大的Adobe解决方案集成，例如：Adobe Analytics、Workfront、Journey Orchestration、实时CDP等。

您还可以使用历程AI配置预测发送时间优化和预测参与度评分，并增加打开率、点击量和收入。

[!DNL :bulb:] [进一步了解Campaign集成](../connect/integration.md)

