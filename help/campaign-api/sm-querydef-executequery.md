---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 34%
---
# 执行查询

从查询中检索数据

```text
XML output = queryDef.ExecuteQuery () const
```

## 参数

无。

## 返回值

**输出**&#x200B;输出XML文档

## 备注

查询支持四种类型的操作：

* 选择
* get
* getIfExists
* count

## 示例

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## 功能

**架构：** [xtk:queryDef](s-xtk-querydef.md)

**静态：**

否

**常量：**

是

仅&#x200B;**键：**

否
