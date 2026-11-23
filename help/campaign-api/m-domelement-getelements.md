---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%
---
# getElements

返回属于此元素的具有指定名称的子元素的列表。

```text
getElements ( [tagName ])
```

## 参数

**tagName**&#x200B;搜索元素的名称。 如果忽略此参数，此函数将返回所有子元素。

## 返回值

包含元素列表的表。

## 备注

此方法为每个调用创建一个新表。 因此，最好将表保留在局部变量中，而不是进行多次调用。

## 功能

**类的方法：** [DOMElement](c-domelement.md)

**可用位置：**

* 内容管理
* 投放属性
* 投放消息
* 类型规则
* 导入
* JSSP
* SOAP方法
* WebApp
* 工作流
