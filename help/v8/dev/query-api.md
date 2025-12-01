---
title: 使用queryDef查询数据库
description: 了解如何使用queryDef和NLWS方法查询Campaign数据库
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
source-git-commit: ceab90331fab0725962a2a98f338ac3dc31a2588
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 1%

---

# 使用queryDef查询数据库 {#query-database-api}

[!DNL Adobe Campaign]提供了强大的JavaScript方法，以便使用`queryDef`和`NLWS`对象与数据库交互。 这些基于SOAP的方法允许您使用JSON、XML或SQL加载、创建、更新和查询数据。

>[!NOTE]
>
>本文档介绍了用于以编程方式查询数据库的面向数据的API。 对于REST API，请参阅[开始使用REST API](api/get-started-apis.md)。 有关生成可视查询的信息，请参阅[使用查询编辑器](../start/query-editor.md)。

## 什么是NLWS？ {#what-is-nlws}

`NLWS` (Neolane Web Services)是用于访问[!DNL Adobe Campaign]基于SOAP的API方法的全局JavaScript对象。 架构是`NLWS`对象的属性，允许您以编程方式与Campaign实体交互。

根据[Campaign JSAPI文档](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html){target="_blank"}，“架构是‘NLWS’全局对象。” 访问架构方法的语法遵循以下模式：

```javascript
NLWS.<namespace><SchemaName>.<method>()
```

**示例：**

* `NLWS.nmsRecipient` — 收件人架构的访问方法(`nms:recipient`)
* `NLWS.nmsDelivery` — 投放模式(`nms:delivery`)的访问方法
* `NLWS.xtkQueryDef` — 访问查询数据库的queryDef方法

常见的API方法包括：

* `load(id)` — 按实体ID加载实体。 [了解详情](https://experienceleague.adobe.com/developer/campaign-api/api/f-load.html){target="_blank"}
* `create(data)` — 创建新实体
* `save()` — 将更改保存到实体

**官方文档示例：**

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

>[!NOTE]
>
>**替代语法：**&#x200B;为了向后兼容，您可能还会看到某些文档中的小写命名空间语法（例如，`nms.recipient.create()`、`xtk.queryDef.create()`）。 两种语法都有效，但`NLWS`是官方Campaign JSAPI参考中记录的标准。

## 先决条件 {#prerequisites}

在使用queryDef和NLWS方法之前，您应该熟悉：

* JavaScript
* [!DNL Adobe Campaign]数据模型和架构
* 用于导航架构元素的XPath表达式

**了解Campaign数据模型：**

Adobe Campaign附带预定义的数据模型，其中包含在Cloud数据库中链接在一起的表。 基本结构包括：

* **收件人表** (`nmsRecipient`) — 存储营销用户档案的主表
* **投放表** (`nmsDelivery`) — 存储投放操作和模板，其中包含用于执行投放的参数
* **日志表** — 存储执行日志：
   * `nmsBroadLogRcp` — 发送给收件人的所有邮件的投放日志
   * `nmsTrackingLogRcp` — 跟踪收件人反应（打开、点击）的日志
* **技术表** — 存储系统数据，如运算符(`xtkGroup`)、会话(`xtkSessionInfo`)、工作流(`xtkWorkflow`)

要在Campaign界面中访问架构描述，请浏览到&#x200B;**管理>配置>数据架构**，选择一个资源，然后单击&#x200B;**文档**&#x200B;选项卡。

## 实体架构方法 {#entity-schema-methods}

[!DNL Adobe Campaign] （例如，`nms:recipient`，`nms:delivery`）中的每个架构都包含可通过`NLWS`对象访问的方法。 这些方法提供了与数据库实体进行交互的便捷方法。

### 静态方法 {#static-methods}

静态SOAP方法可通过在表示模式的对象上调用方法来进行访问。 例如，`NLWS.xtkWorkflow.PostEvent()`调用静态方法。

### 非静态方法 {#non-static-methods}

要使用非静态SOAP方法，您必须首先使用相应架构上的`load`或`create`方法检索实体。 请参阅[Campaign JSAPI文档](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html){target="_blank"}以了解详情。

### 加载、保存和创建实体 {#load-save-create}

**按ID加载实体并更新它：**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**使用JSON创建收件人：**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**使用XML创建收件人：**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## QueryDef概述 {#querydef-overview}

`xtk:queryDef`架构提供了生成和执行数据库查询的方法。 您可以使用`NLWS.xtkQueryDef.create()`通过JSON或XML语法生成查询。

**可用操作：**

* `select` — 检索多个记录
* `get` — 检索单个记录(SQL `LIMIT 1`)
* `getIfExists` — 检索单个记录，如果未找到，则返回null
* `count` — 计数符合条件的记录

请参阅[Campaign JSAPI文档](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}以了解有关queryDef方法的更多信息。

## 使用JSON进行查询 {#query-json}

使用`NLWS.xtkQueryDef.create()`通过JSON语法生成查询。 `get`操作检索单个记录(SQL `LIMIT 1`)，而`select`检索多个记录。

**获取单个收件人：**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**使用`getIfExists`避免出现异常：**

如果记录可能不存在，请使用`operation: "getIfExists"`而不是`get`以避免出现异常：

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## 选择多个记录 {#select-multiple}

使用`select`操作检索多个记录。 您可以添加条件、顺序和限制。

**查询包含筛选器和排序的工作流：**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**使用XML语法查询投放：**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>**结果限制：**&#x200B;营销活动自动限制查询结果以防止内存问题：
>* 默认限制因上下文而异（通常为200-10,000条记录）
>* 使用`lineCount`显式设置最大结果数
>* 对于大型数据集（超过1000条记录），请使用工作流而不是queryDef。 工作流旨在高效地处理数百万行。

了解有关[ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html){target="_blank"}和[查询最佳实践](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}的更多信息。

## 查询工作流过渡数据 {#workflow-transition-data}

在工作流中使用JavaScript活动时，您可以使用`vars.targetSchema`和`vars.tableName`查询传入过渡中的数据。

**通过工作流转换查询收件人数据：**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>始终使用参数化的查询，字符串为`$(sz)`，整数为`$(l)`，以防止SQL注入漏洞。 请参阅[Campaign JSAPI文档](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html){target="_blank"}以了解详情。

## 对记录计数 {#count-records}

使用带有别名的`Count(@id)`计算记录。

**正在运行的假设计数：**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**包含多个条件的计数：**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## 值的分布 {#distribution-values}

获取特定字段的值的分布情况，这可用于分析数据模式。

**国家/地区代码的分发：**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## 使用分析查询枚举 {#analyze-enumerations}

`analyze`选项返回枚举值的用户友好名称。 Campaign还将使用“名称”和“标签”后缀返回字符串值和标签，而不是仅返回数值。

**具有枚举分析的查询投放映射：**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:deliveryMapping",
    operation: "get",
    select: {
      node: [
        {expr: "@id"},
        {expr: "@name"},
        {expr: "[storage/@exclusionType]", analyze: true}  // Analyze enumeration
      ]
    },
    where: {
      condition: [{expr: "@name='mapRecipient'"}]
    }
  }
});

var mapping = query.ExecuteQuery();

// Result includes:
// - exclusionType: 2 (numeric value)
// - exclusionTypeName: "excludeRecipient" (string value)
// - exclusionTypeLabel: "Exclude recipient" (display label)
logInfo("Type: " + mapping.$exclusionType);
logInfo("Name: " + mapping.$exclusionTypeName);
logInfo("Label: " + mapping.$exclusionTypeLabel);
```

了解有关[分析选项](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#the-analyze-option){target="_blank"}的更多信息。

## 分页 {#pagination}

使用`lineCount`和`startLine`在大型结果集中分页。

**检索页面中的记录：**

```javascript
// Get records 3 and 4 (skip first 2)
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    lineCount: 2,     // Number of records per page
    startLine: 2,     // Starting position (0-indexed)
    select: {
      node: [
        {expr: "@id"},
        {expr: "@email"}
      ]
    },
    orderBy: {
      node: [{expr: "@id"}]  // Critical: Always use orderBy for pagination
    }
  }
});

var recipients = query.ExecuteQuery();
```

>[!CAUTION]
>
>**分页需要orderBy：**&#x200B;如果没有`orderBy`子句，查询结果不能保证为一致顺序。 后续调用可能会返回不同的页面或重复的记录。 使用分页时始终包括`orderBy`。

了解有关[分页](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#pagination){target="_blank"}的详细信息。

## 动态查询构建 {#dynamic-queries}

通过以编程方式附加条件来动态构建查询。

**将条件附加到现有查询：**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**生成循环中的select和where子句：**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## 高级queryDef方法 {#advanced-methods}

在`ExecuteQuery()`之外，queryDef为高级用例提供了几种专用方法。

### BuildQuery — 生成SQL而不执行 {#build-query}

使用`BuildQuery()`生成SQL语句而不执行它。 这对于调试、记录或将查询传递到外部系统非常有用。

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

了解有关[BuildQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html){target="_blank"}的详细信息。

### BuildQueryEx — 获取带有格式字符串的SQL {#build-query-ex}

`BuildQueryEx()`返回SQL查询和与`sqlSelect()`函数兼容的格式字符串。

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

了解有关[BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html){target="_blank"}的详细信息。

### SelectAll — 添加要选择的所有字段 {#select-all}

`SelectAll()`方法会自动将架构中的所有字段添加到select子句中，从而避免手动列出每个字段。

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

了解有关[全选](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html){target="_blank"}的详细信息。

### 更新 — 成批更新记录 {#mass-update}

`Update()`方法允许您对符合查询条件的记录执行批量更新，而无需单独加载每个记录。

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>成批更新会影响与where子句匹配的所有记录。 始终首先使用select查询测试您的where条件，以验证哪些记录将受到影响。

了解有关[更新](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html){target="_blank"}的详细信息。

### GetInstanceFromModel — 查询模板实例 {#get-instance-from-model}

使用`GetInstanceFromModel()`从从模板创建的实例中检索数据。

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

了解有关[GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html){target="_blank"}的详细信息。

## 批处理操作 {#batch-operations}

批量处理多个记录以提高性能。

**批次更新投放标签：**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## 原始SQL执行 {#raw-sql}

对于复杂的操作，可以直接执行原始SQL。

**执行参数化SQL：**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

使用sqlSelect的&#x200B;**查询：**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>使用原始SQL时：
>
>* 始终验证和整理用户输入
>* 使用具有`$(sz)`、`$(l)`、`$(dt)`等的参数化查询
>* 了解[FFDA部署](../architecture/enterprise-deployment.md)中的本地数据库和云数据库之间的差异

## 最佳实践 {#best-practices}

使用queryDef和NLWS方法时：

* **对大型数据集使用工作流** - QueryDef不是针对大容量数据处理而设计的。 对于包含超过1,000条记录的数据集，请使用可高效处理数百万行的工作流。 请参阅[Campaign SDK文档](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}以了解详情
* **使用参数化查询** — 始终将绑定参数(`$(sz)`， `$(l)`)与`sqlExec`一起使用，以防止SQL注入
* **设置显式限制** — 使用`lineCount`控制结果大小。 Campaign的默认限制因上下文而异（200-10,000条记录）
* **将orderBy与分页一起使用** — 在使用`orderBy`和`startLine`时始终包含`lineCount`子句，以确保分页一致
* **使用getIfExists** — 在记录可能不存在时使用`operation: "getIfExists"`以避免出现异常
* **对枚举使用分析** — 添加`analyze: true`以选择节点以获取用户友好的枚举名称和标签
* **优化查询** — 添加适当的`where`条件以限制结果集
* **批量处理** — 批量处理多个记录以避免内存问题和超时
* **FFDA感知** — 在[企业(FFDA)部署](../architecture/enterprise-deployment.md)中，请注意[!DNL Campaign]可与两个数据库配合使用



## 实际用例 {#use-cases}

### 调试和记录查询 {#debug-queries}

使用`BuildQuery()`在执行之前检查生成的SQL：

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### 使用SelectAll复制记录 {#duplicate-record}

复制记录时使用`SelectAll()`复制所有字段：

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### 批量更新前验证 {#validate-mass-update}

在执行成批更新之前，始终预览受影响的记录：

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## 查询定义语法参考 {#querydef-reference}

`queryDef`对象的完整结构：

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## 相关主题 {#related-topics}

* [Campaign API入门](api.md)
* [Campaign JavaScript SDK — 查询API](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* [queryDef API引用](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}
* [Campaign JSAPI文档](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
* [使用架构](schemas.md)
* [使用查询编辑器](../start/query-editor.md)

