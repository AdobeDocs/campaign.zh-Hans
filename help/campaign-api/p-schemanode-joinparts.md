---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%
---
# joinParts

返回一个SchemaNode实例的表，其中每个元素代表连接的条件。

```text
joinParts
```

## 备注

表中的每个元素都有两个属性：

* source — 表示源表字段的元素。
* 目标 — 表示目标表的字段的元素。

示例：

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
}
```

## 功能

**类的属性：** [SchemaNode](c-schemanode.md)

**只读：**

是

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
