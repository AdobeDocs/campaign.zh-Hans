---
product: campaign
title: SQL 数据管理
description: 了解有关SQL数据管理工作流活动的更多信息
feature: Workflows
Role: User
Level: Experienced
exl-id: a1e08d57-0387-4802-b447-f6d9ad87072a
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 3%

---

# SQL 数据管理{#sql-data-management}

**SQL数据管理**&#x200B;活动允许您编写自己的SQL脚本来创建和填充工作表。

## 先决条件 {#prerequisites}

在配置活动之前，请确保满足以下先决条件：

* 该活动仅适用于远程数据源。
* 出站模式必须存在于数据库中并链接到FDA数据库。


## 配置SQL数据管理活动 {#configuring-the-sql-data-management-activity}

1. 指定活动&#x200B;**[!UICONTROL Label]**。
1. 选择要使用的&#x200B;**[!UICONTROL External account]**，然后选择链接到此外部帐户的&#x200B;**[!UICONTROL Outbound schema]**。

   >[!CAUTION]
   >
   >出站架构是固定的，无法编辑。

1. 添加SQL脚本。

   >[!CAUTION]
   >
   >SQL脚本编写者负责确保SQL脚本正常工作及其引用（字段名称等） 符合出站模式。

   如果要加载现有SQL代码，请选择&#x200B;**[!UICONTROL The SQL script is contained in an entity stored in the database]**&#x200B;选项。 必须在&#x200B;**[!UICONTROL Administration]** / **[!UICONTROL Configuration]** / **[!UICONTROL SQL scripts]**&#x200B;菜单中创建和存储SQL脚本。

   否则，请在专用区域中键入或复制粘贴您的SQL脚本。

   ![](assets/sql_datamanagement.png)

   利用活动，可在脚本中使用以下变量：

   * **activity.tableName**：出站工作表的SQL名称。
   * **task.incomingTransitionByName(&#39;name&#39;)。tableName**：传入过渡所承载要使用的工作表的SQL名称（过渡由其名称标识）。

     >[!NOTE]
     >
     >(“name”)值对应于过渡属性中的&#x200B;**[!UICONTROL Name]**&#x200B;字段。

1. 如果SQL脚本已包含用于创建出站工作表的命令，请取消选择&#x200B;**[!UICONTROL Automatically create work table]**&#x200B;选项。 否则，工作流执行后将自动创建工作表。
1. 单击&#x200B;**[!UICONTROL Ok]**&#x200B;以确认活动配置。

现已配置该活动。工作流中可以随时执行该操作。

>[!CAUTION]
>
>执行活动后，叫客过渡记录计数仅为指示性的。 它可能会根据SQL脚本的复杂性级别而有所不同。
>  
>如果活动重新启动，则将从头开始执行整个脚本，而不管其执行状态如何。

## SQL脚本示例 {#sql-script-samples}

>[!NOTE]
>
>本节中的脚本示例旨在在PostgreSQL下执行。

下面的脚本允许您创建工作表并将数据插入此同一工作表中：

```
CREATE UNLOGGED TABLE <%= activity.tableName %> (
  iRecipientId INTEGER DEFAULT 0,
  sFirstName VARCHAR(100),
  sMiddleName VARCHAR(100),
  sLastName VARCHAR(100),
  sEmail VARCHAR(100)
);

INSERT INTO <%= activity.tableName %>
SELECT iRecipientId, sFirstName, sMiddleName, sLastName, sEmail
FROM nmsRecipient
GROUP BY iRecipientId, sFirstName, sMiddleName, sLastName, sEmail;
```

下面的脚本允许您执行CTAS操作(CREATE TABLE AS SELECT)并创建工作表索引：

```
CREATE TABLE <%= activity.tableName %>
AS SELECT iRecipientId, sEmail, sFirstName, sLastName, sMiddleName
FROM nmsRecipient
WHERE sEmail IS NOT NULL
GROUP BY iRecipientId, sEmail, sFirstName, sLastName, sMiddleName;

CREATE INDEX ON <%= activity.tableName %> (sEmail);

ANALYZE <%= activity.tableName %> (sEmail);
```

下面的脚本允许您合并两个工作表：

```
CREATE TABLE <%= activity.tableName %>
AS SELECT i1.sFirstName, i1.sLastName, i2.sEmail
FROM <%= task.incomingTransitionByName('input1').tableName %> i1
JOIN <%= task.incomingTransitionByName('input2').tableName %> i2 ON (i1.id = i2.id)
```
