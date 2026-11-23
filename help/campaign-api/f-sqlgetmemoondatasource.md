---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 11%
---
# sqlGetMemoOnDataSource

返回由数据源上的SQL查询生成的Memo字段。

```text
sqlGetMemoOnDataSource (query, dataSource [, value1, ... ])
```

## 参数

**查询** SQL查询。

**数据源**&#x200B;数据源。

**value1， ...** SQL查询的变量。

## 返回值

与查询匹配的“备注”字段。

## 备注

在[sqlExecOnDataSource(query， dataSource， value1， ...)](f-sqlexecondatasource.md)中定义了“数据源”参数 函数作为此函数的参数设置的可选变量在[sqlGetString(query， value1， ...)](f-sqlgetstring.md)中定义

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
