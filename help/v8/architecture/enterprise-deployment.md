---
title: Campaign FDA部署入门
description: Campaign FDA部署入门
feature: Architecture, FFDA
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 55%

---

# [!DNL Campaign] FFDA部署{#gs-ac-ffda}

通过利用 [[!DNL Snowflake]](https://www.snowflake.com/)，作为云数据库技术，Adobe Campaign企业完全联合访问(FFDA)部署显着提高了其规模和速度，能够管理更多的客户配置文件，以及更高的每小时交付率和交易。

## 好处 {#ffda-benefits}

Campaign v8 Enterprise(FFDA)在从定位到最终报告的流程中的任何步骤都提供端到端规模：

* 扩展可处理的数据量（最高达 8 TB）
* 扩展分段和定位的查询性能，还可扩展数据摄取和输出
* 将投放准备速度从小时扩展到分钟

这是软件架构的重大变化。数据现在位于远程位置，Campaign 会联合所有数据（包括用户档案）。[!DNL Campaign] 流程现在实现了端到端扩展，从定位到消息执行：数据摄取、分段、定位、查询、投放一般只需要几分钟即可运行。这个新版本解决了扩展的全部难题，同时保持了相同级别的灵活性和可扩展性。用户档案的数量几乎是无限的，而且可以延长数据保留时间。

云存储在 **[!DNL Snowflake]** 中执行：一种新的内置&#x200B;**外部帐户**&#x200B;可确保与云数据库的连接。它由 Adobe 配置，不可修改。[了解详情](../config/external-accounts.md)

需要在云数据库中移动或复制的任何内置模式/表格都在 **xxl** 命名空间下附带内置模式扩展。这些扩展包含将内置模式从[!DNL Campaign]本地数据库移动到 [!DNL Snowflake] 云数据库并相应地调整其结构所需的任何修改：新的 UUID、更新的链接等。

>[!CAUTION]
>
> 客户数据并不存储在本地 [!DNL Campaign] 数据库中。因此，所有自定义表格都需要在云数据库中创建。

## Campaign企业(FFDA)架构{#ffda-archi}

在 [企业(FFDA)部署](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8与两个数据库配合使用：本地 [!DNL Campaign] 用于用户界面实时消息传送和统一查询和通过API和云写入的数据库 [!DNL Snowflake] 用于促销活动执行、批量查询和工作流执行的数据库。

Campaign v8 企业版引入了&#x200B;**完全联合数据访问** (FFDA) 概念：所有数据现在都位于云数据库上的远程位置。

特定 API 可用于管理本地数据库和云数据库之间的数据。在[本页面](new-apis.md)中了解这些新 API 的工作方式以及如何使用它们。

服务器和进程之间的一般通信按照以下模式进行：

![](assets/architecture.png)

* 实例上禁用了执行和退回管理模块。
* 该应用程序配置为在使用SOAP调用（通过HTTP或HTTPS）驱动的远程“中间源”服务器上执行消息执行。

的 [!DNL Snowflake] 营销端数据库用于：

* 存储所有客户数据：用户档案、自定义数据（如交易、产品、位置等）
* 存储由Campaign生成或收集的所有事件和行为数据，如投放日志、跟踪日志、推送注册等。
* 存储上述的所有数据聚合。
* 存储参考表的副本(h+1)（如投放、枚举、国家/地区等） 工作流、营销活动和报表中使用的插件。
* 运行所有批处理过程和工作负载


营销实例上的PostgreSQL数据库用于：

* 执行某些工作负载，例如低卷API。
* 存储所有Campaign数据，包括投放和促销活动设置、工作流和服务定义。
* 存储所有内置参考表（枚举、国家/地区等） 复制到 [!DNL Snowflake].

   但是，您不能：
   * 为客户数据创建自定义，例如，不要在PostgreSQL中创建家庭表，而是仅在Snowflake中
   * 存储任何投放日志、跟踪日志等。 在FFDA定位维度上。
   * 存储大量数据。


中间源实例上的PostgreSQL数据库用于：

* 执行批量和实时(RT)投放。
* 发送投放和跟踪日志 — 请注意，投放和跟踪日志ID是UUID，而不是32位ID。
* 收集和存储跟踪数据。


## 影响{#ffda-impacts}

### [!DNL Campaign] API 暂存机制{#staging-api}

使用 [!DNL Campaign] 由于性能（延迟和并发），不建议使用云数据库、爆炸式统一调用。 批处理操作始终为首选。 为了确保API的最佳性能，Campaign会保持在本地数据库级别处理API调用。

![](../assets/do-not-localize/glass.png) [本页详细介绍了API暂存机制](staging.md)

### 新 API{#new-apis}

提供了新的API，用于管理 [!DNL Campaign] 本地数据库和云数据库。 此外，还引入了新机制，在本地数据库级别处理API调用，以避免延迟并提高整体性能。

![](../assets/do-not-localize/glass.png) [本页详细介绍了新的API](new-apis.md)


### 数据复制{#data-replication}

特定的技术工作流可处理需要存在于两端（Campaign 本地数据库和云数据库）的表格的复制操作。此工作流每小时都会触发一次，并且依赖于新的内置 JavaScript 库。

>[!NOTE]
>
> 已根据表格的大小（XS、XL等）创建了多种复制策略。
> 部分表格是实时复制的，其他表格则是每小时复制一次。部分表格将具有增量更新，而其他表格则将进行全面更新。

[了解关于数据复制的更多信息](replication.md)

### ID 管理{#id-mgt-ffda}

Campaign v8 对象现在使用&#x200B;**通用唯一标识符 (UUID)**，允许使用无限的唯一值来标识数据。

请注意，此 ID 是基于字符串的，而不是按顺序的。主密钥不是 Campaign v8 中的数字值，您需要在模式中使用 **autouuid** 和 **autopk** 属性。

在 Campaign Classic v7 及更早的版本中，模式（即表格）中密钥的唯一性在数据库引擎级别进行处理。一般来说，PostgreSQL、Oracle 或 SQL Server 等 Classic 数据库引擎包含原生机制，以防止通过主密钥和/或唯一索引根据列或一组列插入重复的行。在数据库级别设置正确的索引和主密钥后，这些版本中不存在重复的 ID。

Adobe Campaign v8 以 Snowflake 为核心数据库。随着查询规模的显着增长，Snowflake 数据库的分布式架构无法提供这样的机制来管理并对表格中某个密钥强制执行唯一性。因此，使用 Adobe Campaign v8 时，没有任何内容会阻止在表格中摄取重复的密钥。现在，最终用户负责确保 Adobe Campaign 数据库中密钥的一致性。[了解详情](keys.md)

**相关主题**

* [数据模型最佳实践](../dev/datamodel-best-practices.md)
