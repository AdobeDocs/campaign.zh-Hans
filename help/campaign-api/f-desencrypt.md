---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%
---
# DESencrypt

> 警告：
>
> 此函数已过时，请使用[cryptString()](f-cryptstring.md)。

使用DES算法数字化字符串。

```text
DESencrypt (value [, key ] [, cipher mode ] [, initialization vector ] [, padding ])
```

## 参数

**value**&#x200B;要数字化的字符串

**key**&#x200B;以十六进制表示的密钥。 密钥必须为64位或16个十六进制字符。 默认情况下，使用数据库的标识符。

**密码模式**&#x200B;块编码方法。 一个字符串。 即“CBC”、“ECB”或“EDE”。 默认情况下，“CBC”。

**初始化矢量**&#x200B;以十六进制字符串形式的初始化矢量。 恰好8个八位字节，即16个字符。 默认情况下，为空字符串。

**填充**&#x200B;填充类型。 字符串，即“PKCS5PADDING”或“PKCS7PADDING”。 默认情况下，空字符串，这意味着在要加密的字符串的末尾添加“\\0”。

## 返回值

以base 64表示的数字化字符串。

## 备注

* DES密钥有56个有用位和8个用于奇偶校验的位；这些位将被忽略。
* 通过DES算法有效加密的值将是字符串的8位Windows-1252表示形式，以ASCII 0字符结束，并以二进制零填充到64位的倍数。
* 该数字化的值具有多长64位值。

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
