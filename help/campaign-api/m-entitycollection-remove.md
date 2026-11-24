---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 20%
---
# 移除

从收藏集中删除实体。

```text
remove (index|object)
```

## 参数

**index\|object**&#x200B;要删除的实体的索引或实体本身。

## 返回值

无。

## 备注

示例：

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
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
