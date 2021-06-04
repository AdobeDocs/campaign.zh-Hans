---
product: Adobe Campaign
title: Campaign v8 的新增功能
description: 了解更多关键功能
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 36e29801bcc95565c32e51742a23d4d74d4e3049
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 53%

---

# Adobe Campaign v8 有哪些新增功能？{#ac-gs-what-is-new}

Adobe Campaign v8 在基础架构、安全性、可投放性和监测方面有着显著改进。利用[[!DNL Snowflake]](https://www.snowflake.com/)云数据库技术，Adobe Campaign可以显着提高其规模和速度，并能够管理更多的客户档案，以及更高的每小时交付率和交易。

关键功能包括：

* **速度和规模**。通过利用 Cloud Database Manager，Adobe Campaign v8 的查询速度提高了 200 倍，具有多 PB 规模，提升了每小时消息处理量，消息处理速度高达 20M/小时或 1M/小时（事务性消息），并可管理多达 2 亿的活动用户档案（可能达到 10 亿）。

* **连接至 Adobe Experience Platform**。Adobe Campaign v8 支持各种数据连接器与 Adobe Experience Platform/RT-CDP 的搭配使用、统一的客户档案以及与 Journey Orchestration 的本机集成。这些投资将可以优化 Adobe Campaign 客户体验并解锁新的用例，如向活动添加个性化实时客户旅程的能力。

* **托管式云服务**。Adobe Campaign v8 是一款领先的托管式云服务，提供主动监督、及时警报和服务治理功能。对营销人员而言，这是一种更灵活、更可扩展的跨渠道营销活动管理。

>[!CAUTION]
>
>目前，Campaign v8仅&#x200B;****&#x200B;可用作托管Cloud Service，不能部署在内部部署或混合环境中。
>
>从现有Campaign Classicv7环境进行迁移的功能尚不可用。
>
>如果您不确定部署模型或有任何问题，请与您的客户团队联系。


## 扩展

Campaign v8在从定位到最终报告的流程中的任何步骤都提供了端到端规模：

* 扩展可处理的数据量（最高达 8 TB）
* 扩展分段和定位的查询性能，还可扩展数据摄取和输出
* 将投放准备范围从小时扩展到分钟

## 简化和性能提升

Campaign v8引入了&#x200B;**完全联合数据访问**(FFDA)的概念：现在，云数据库中的所有数据都是远程的。

使用此新架构，Campaign v8简化了数据管理：云数据库上不需要索引。 您只需创建表格、复制数据即可开始。

[!DNL Snowflake] 是Campaign Cloud数据库，它将为您带来速度和耐力：系统活动峰值没有过载。

云数据库技术无需特定的维护来保证性能级别。

## 综合性生态系统

您可以将Campaign与一组功能强大的Adobe解决方案集成，例如：Adobe Analytics、AdobeJourney Orchestration、实时CDP等。

您还可以通过旅程人工智能配置预测发送时间优化和预测参与度评分，并提高打开率、点击量和收入。

[!DNL :bulb:] [了解有关 Campaign 集成的更多信息](../connect/integration.md)

