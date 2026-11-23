---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 14%
---
# getdatevalue

返回给定XPath引用的节点的date+hour类型值。

```text
getDateValue (xpath)
```

## 参数

**xpath**&#x200B;路径。

## 返回值

与引用的节点值匹配的日期类型对象。

## 备注

XPath的语法只接受XPath语言子集。 如果路径格式错误或值不是有效日期，则会引发异常。

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
