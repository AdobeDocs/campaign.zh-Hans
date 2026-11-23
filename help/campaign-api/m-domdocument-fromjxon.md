---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 14%
---
# fromJXON

从JXON对象创建新文档。

```text
fromJXON (obj)
```

## 参数

**obj**&#x200B;表示要创建的XML文档的JXON对象。

## 返回值

无。

## 备注

将DOMDocument或DOMElement作为参数传递的函数也直接接受JXON对象。 无需使用此函数构建中间对象。 如果对象不是有效的JXON对象，则会引发异常。 此函数适用于DOMDocument类。 示例：

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
```

## 功能

**类的方法：** [DOMDocument](c-domdocument.md)

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
