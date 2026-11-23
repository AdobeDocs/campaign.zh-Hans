---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# 移除全部

从集合中删除所有实体。

```text
removeAll ()
```

## 参数

无。

## 返回值

无。

## 备注

示例：

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.removeAll()
delivery.save()
```

## 功能

**类的方法：** [EntityCollection](c-entitycollection.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
