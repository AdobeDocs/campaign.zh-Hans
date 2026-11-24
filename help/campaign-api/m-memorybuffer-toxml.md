---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 17%
---
# toXML

返回从[MemoryBuffer](c-memorybuffer.md)的内容获得的XML JavaScript对象。 此函数已过时，请使用[toDocument()](m-memorybuffer-todocument.md)

```text
toXML ( [codePage ])
```

## 参数

**codePage**&#x200B;对所用字符页进行编码的整数。 默认情况下，MemoryBuffer.CODEPAGE\_UTF8。

## 返回值

以XML对象形式表示的图章内容。

## 功能

**类的方法：** [MemoryBuffer](c-memorybuffer.md)

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
