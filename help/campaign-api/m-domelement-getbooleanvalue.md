---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%
---
# getbooleanvalue

返回给定XPath引用的布尔节点值。

```text
getBooleanValue (xpath)
```

## 参数

**xpath**&#x200B;路径。

## 返回值

如果引用节点的文本值为“true”或“1”，则为true；如果值为“false”或“0”，则为false。

## 备注

XPath的语法只接受XPath语言子集。 值测试不区分大小写。 如果路径格式错误或值不是有效的布尔值，则会引发异常。

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
