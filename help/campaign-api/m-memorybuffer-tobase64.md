---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# toBase64

转换以base 64编码的缓冲区或部分字符串。

```text
toBase64 ( [start ] [, length ])
```

## 参数

**start**&#x200B;在缓冲区开头要忽略的字节数。 第一个字节对应于值0 （默认值）。

**长度**&#x200B;要转换的字节数。 默认情况下，会考虑剩余的所有字节。

## 返回值

以base 64编码的缓冲区的内容。

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
