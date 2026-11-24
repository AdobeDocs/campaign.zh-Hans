---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%
---
# 模糊处理

将整数模糊化为字符串。 可以通过调用[unobfuscate](f-unobfuscate.md)恢复原始值。

```text
obfuscate (value [, size ] [, version ])
```

## 参数

**value**&#x200B;要模糊处理的整数。

**size**&#x200B;因模糊处理而导致的字符串大小。 介于6和10之间的整数。 默认情况下，为6。

**版本**&#x200B;要应用的模糊处理版本。 默认情况下，为0。

## 返回值

一个字符串，它表示经过模糊处理的整数。

## 功能

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
