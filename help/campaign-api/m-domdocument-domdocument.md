---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 33%
---
# DOMDocument

创建新文档。

```text
DOMDocument (name [, namespaceURI ])
```

## 参数

**名称**&#x200B;文档名称。

**namespaceURI**&#x200B;文档命名空间URI。

## 返回值

无。

## 备注

示例：

```javascript
var doc = new DOMDocument("test")
var doc2 = new DOMDocument("html", "http://www.w3.org/1999/xhtml")
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
