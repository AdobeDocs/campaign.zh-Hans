---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%
---
# findNode

返回[SchemaNode](c-schemanode.md)的实例，如果节点不存在并且mustExist参数设置为false，则返回null。

```text
findNode (name [, strict ] [, mustExist ])
```

## 参数

**name** XPath表示要搜索的节点的名称

**strict**&#x200B;布尔值，指示是否(strict to false)，当路径中最后一个项的名称不按原样存在时，应作为属性或元素进行搜索。 默认为true。

**mustExist**&#x200B;布尔值，指示如果节点不存在是否必须引发异常。 默认为true。

## 返回值

如果可以找到节点，则返回[SchemaNode](c-schemanode.md)实例；如果mustExist参数设置为false，则返回null。

## 备注

示例：

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

结果：

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## 功能

**类的方法：** [SchemaNode](c-schemanode.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
