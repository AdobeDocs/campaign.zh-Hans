---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 20%
---
# fromXMLString

从XML字符字符串创建新文档。

```text
fromXMLString (string)
```

## 参数

**字符串** XML字符字符串。

## 返回值

无。

## 备注

如果参数不是有效的XML文档，则会引发异常。 此函数适用于DOMDocument类。 示例：

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
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
