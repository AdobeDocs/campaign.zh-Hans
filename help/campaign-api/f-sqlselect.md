---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 13%
---
# sqlSelect

执行SQL查询并将结果作为XML文档返回。

```text
sqlSelect (format, query [, dataSource ])
```

## 参数

**format**&#x200B;用逗号分隔的字符串，将预期数据的格式描述为名称:type\[:length\]类型列表docName，\[fieldXPath:type，\]\*

**查询** SQL查询。

**数据源**&#x200B;数据源。

## 返回值

XML对象，其中包含查询结果每行的元素列表。

## 备注

示例：

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
