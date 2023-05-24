---
title: 開始使用Campaign FFDA部署
description: 開始使用Campaign FFDA部署
feature: Architecture, FFDA
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
source-git-commit: 51bba0a2b4be03577f508d352fc7c2b514ba28e5
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 54%

---

# [!DNL Campaign] FFDA部署{#gs-ac-ffda}

善用 [[!DNL Snowflake]](https://www.snowflake.com/)Adobe Campaign企業完整同盟存取(FFDA)部署是一項雲端資料庫技術，可大幅提升其規模和速度，能夠管理更多的客戶設定檔，並提供更高的每小時傳送率和異動。

## 好处 {#ffda-benefits}

Campaign v8企業版(FFDA)在流程的任何步驟中都提供端對端規模，從目標定位到最終報告：

* 扩展可处理的数据量（最高达 8 TB）
* 扩展分段和定位的查询性能，还可扩展数据摄取和输出
* 将投放准备速度从小时扩展到分钟

这是软件架构的重大变化。数据现在位于远程位置，Campaign 会联合所有数据（包括用户档案）。[!DNL Campaign] 流程现在实现了端到端扩展，从定位到消息执行：数据摄取、分段、定位、查询、投放一般只需要几分钟即可运行。这个新版本解决了扩展的全部难题，同时保持了相同级别的灵活性和可扩展性。用户档案的数量几乎是无限的，而且可以延长数据保留时间。

云存储在 **[!DNL Snowflake]** 中执行：一种新的内置&#x200B;**外部帐户**&#x200B;可确保与云数据库的连接。它由 Adobe 配置，不可修改。[了解详情](../config/external-accounts.md)

需要在云数据库中移动或复制的任何内置模式/表格都在 **xxl** 命名空间下附带内置模式扩展。这些扩展包含将内置模式从[!DNL Campaign]本地数据库移动到 [!DNL Snowflake] 云数据库并相应地调整其结构所需的任何修改：新的 UUID、更新的链接等。

>[!CAUTION]
>
> 客户数据并不存储在本地 [!DNL Campaign] 数据库中。因此，所有自定义表格都需要在云数据库中创建。

## Campaign Enterprise (FFDA)架構{#ffda-archi}

在 [企業(FFDA)部署](../architecture/enterprise-deployment.md)， [!DNL Adobe Campaign] v8適用於兩個資料庫：本機 [!DNL Campaign] 資料庫用於使用者介面即時傳送訊息和統一查詢，以及透過API和雲端寫入 [!DNL Snowflake] 用於行銷活動執行、批次查詢和工作流程執行的資料庫。

Campaign v8 企业版引入了&#x200B;**完全联合数据访问** (FFDA) 概念：所有数据现在都位于云数据库上的远程位置。

特定 API 可用于管理本地数据库和云数据库之间的数据。在[本页面](new-apis.md)中了解这些新 API 的工作方式以及如何使用它们。

伺服器與處理序之間的一般通訊會根據下列結構描述執行：

![](assets/architecture.png)

* 執行個體上的執行和彈回管理模組已停用。
* 應用程式設定為在使用SOAP呼叫（透過HTTP或HTTPS）驅動的遠端「中間來源」伺服器上執行訊息。

此 [!DNL Snowflake] 行銷端的資料庫用於：

* 儲存所有客戶資料：設定檔、交易、產品、位置等自訂資料。
* 儲存Campaign產生或收集的所有事件和行為資料，例如傳送記錄、追蹤記錄、推播註冊等。
* 儲存上述專案的所有資料彙總。
* 儲存參考表格（例如傳送、分項清單、國家/地區等）的復本(h+1) 用於工作流程、行銷活動和報表。
* 執行所有批次處理及工作負載


行銷執行個體上的PostgreSQL資料庫用於：

* 執行特定工作負載，例如低流量API。
* 儲存所有Campaign資料，包括傳遞和行銷活動設定、工作流程和服務定義。
* 儲存所有內建參考表（分項清單、國家/地區等） 已復寫至 [!DNL Snowflake].

   但是，您不能：
   * 建立客戶資料的自訂專案，例如，不要在PostgreSQL中建立家用表格，而只在Snowflake中建立
   * 儲存任何傳遞記錄、追蹤記錄等。 FFDA目標維度。
   * 儲存大量資料。


中間來源執行個體上的PostgreSQL資料庫用於：

* 執行批次和即時(RT)傳遞。
* 傳送傳送和追蹤記錄 — 請注意，傳送和追蹤記錄ID是UUID，而非32位元ID。
* 收集和儲存追蹤資料。


## 影響{#ffda-impacts}

### [!DNL Campaign] API 暂存机制{#staging-api}

替換為 [!DNL Campaign] 雲端資料庫，由於效能（延遲和並行），不建議使用Blast單一呼叫。 一律偏好使用批次作業。 為了保證API的最佳效能，Campaign會持續在本機資料庫層級處理API呼叫。

![](../assets/do-not-localize/glass.png) [本頁面會詳細說明API暫存機制](staging.md)

### 新 API{#new-apis}

新的API可用於管理以下專案之間的資料同步： [!DNL Campaign] 本機資料庫和雲端資料庫。 此外也引入新機制，可在本機資料庫層級處理API呼叫，以避免延遲並提高整體效能。

![](../assets/do-not-localize/glass.png) [有關新API的詳情，請參閱本頁](new-apis.md)


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

### 功能可用性 {#feature-availability}

某些功能無法用於Campaign的企業(FFDA)部署內容，例如：

* 营销资源管理
* 优惠券
* Web 跟踪
* 调查


**相关主题**

* [数据模型最佳实践](../dev/datamodel-best-practices.md)
