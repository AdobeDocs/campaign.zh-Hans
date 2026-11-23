---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 14%
---
# EntityCollection（类）

表示实体的集合。

此类对象无法直接实例化。 必须使用create()、get()或load()方法。

集合的元素可以使用`for`或`for each`枚举。 此示例显示链接到投放操作的文件的枚举。

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## 方法

| 方法 | 描述 |
| --- | --- |
| [添加](m-entitycollection-add.md) | 向集合中添加新实体。 |
| [移除](m-entitycollection-remove.md) | 从收藏集中删除实体。 |
| [removeAll](m-entitycollection-removeall.md) | 从集合中删除所有实体。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [长度](p-entitycollection-length.md) | 返回集合的实体编号。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
