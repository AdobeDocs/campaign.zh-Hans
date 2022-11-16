---
title: Campaign架构快速入门
description: 了解环境和部署基础知识，包括如何报告营销活动环境。
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 507f30d16eecf5400ee88a4d29913e4cdaca9cba
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 12%

---

# Campaign架构快速入门{#gs-ac-archi}

## 环境 {#environments}

Campaign可作为单个实例使用，每个实例代表一个完整的Campaign环境。

提供了两种类型的环境：

* **生产环境**:为业务从业者托管应用程序。

* **非生产环境**:在将对应用程序所做的更改推送到生产环境之前，用于各种性能和质量测试。

您可以将资源包从一个环境导出并导入到另一个环境。

![](../assets/do-not-localize/book.png) 了解有关 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target=&quot;_blank&quot;}

## 部署模型{#ac-deployment}

提供了两种部署模型：

* **营销活动联合数据访问 [!DNL Snowflake] 部署**

   在 [[!DNL Snowflake] FDA部署](fda-deployment.md), [!DNL Adobe Campaign] v8连接到 [!DNL Snowflake] 要通过“联合数据访问”功能访问数据，请执行以下操作：您可以访问和处理存储在 [!DNL Snowflake] 数据库，而不改变Adobe Campaign数据的结构。 PostgreSQL是主数据库，Snowflake是次数据库。 您可以扩展数据模型并在Snowflake上存储数据。 随后，您可以对性能卓越的大型数据集运行ETL、分段和报告。

* **Campaign Enterprise(FFDA)部署**

   在 [企业(FFDA)部署](enterprise-deployment.md), [!DNL Adobe Campaign] v8与两个数据库配合使用：本地 [!DNL Campaign] 用于用户界面实时消息传送和统一查询和通过API和云写入的数据库 [!DNL Snowflake] 用于促销活动执行、批量查询和工作流执行的数据库。

   Campaign v8 企业版引入了&#x200B;**完全联合数据访问** (FFDA) 概念：所有数据现在都位于云数据库上的远程位置。凭借这种新架构，Campaign v8 企业版 (FFDA) 部署简化了数据管理：云数据库上不需要索引。您只需创建表格、复制数据即可开始。云数据库技术无需特定的维护来保证性能级别。


## 消息中心架构{#transac-msg-archi}

事务性消息（消息中心）是用于管理触发消息的 Campaign 模块。

![](../assets/do-not-localize/glass.png) 了解如何在 [此部分](../send/transactional.md).

为响应客户在网站上的操作，通过REST API发送Campaign事件，并填充通过API调用提供的信息或数据，向客户实时发送事务型消息。 这些消息可以单独发送，也可以通过电子邮件、短信或推送通知批量发送。

在此特定架构中，执行单元与控制实例分开，以确保高可用性和负载管理。

* 的 **控制实例** （或营销实例），供营销人员和IT团队用于创建、配置和发布消息模板。 此实例还将事件监控和历史记录集中在一起。

   ![](../assets/do-not-localize/glass.png) 了解如何在 [此部分](../send/transactional.md).

* 的 **执行实例** 检索传入事件（例如，密码重置或来自网站的订单）并发送个性化消息。 可以有多个执行实例通过负载平衡器处理消息，并扩展要进行的事件数以实现最大可用性。

>[!CAUTION]
>
>控制实例和执行实例必须安装在不同的计算机上。 他们无法共享同一Campaign实例。

![](assets/messagecenter_diagram.png)

### 身份验证

要使用这些功能，Adobe Campaign用户登录到控制实例以创建事务型消息模板、使用种子列表生成消息预览、显示报告并监视执行实例。

* 单个执行实例与Adobe托管的消息中心执行实例交互时，外部系统可以首先通过使用提供的帐户登录和密码对会话登录方法进行api调用，来检索会话令牌（默认在24小时后过期）。
然后，通过执行实例为响应上述调用而提供的sessionToken，外部应用程序可以调用SOAP API（rtEvents或batchEvents）来发送通信，而无需在每个SOAP调用中包含帐户登录和密码。

* 多个执行实例在负载平衡器后面具有多个执行实例的多单元执行架构中，外部应用程序调用的登录方法将通过负载平衡器：因此，无法使用基于令牌的身份验证。 需要基于用户/密码的身份验证。

![](../assets/do-not-localize/book.png) 了解有关事务性消息传递事件的更多信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel){target=&quot;_blank&quot;}
