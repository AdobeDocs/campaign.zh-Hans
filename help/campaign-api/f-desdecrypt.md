---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 8%
---
# DESdecrypt

> 警告：
>
> 此函数已过时，请使用[decryptString()](f-decryptstring.md)。

使用DES算法解密数据。

```text
DESdecrypt (value [, key ] [, cipher mode ] [, initialization vector ])
```

## 参数

**value**&#x200B;要数字化的数据，以64为基数表示。

**key**&#x200B;以十六进制表示的密钥。 密钥必须为64位或16个十六进制字符。 默认情况下，使用数据库的标识符。

**密码模式**&#x200B;块编码方法。 一个字符串。 即“CBC”、“ECB”或“EDE”。 默认情况下，“CBC”。

**初始化矢量**&#x200B;以十六进制字符串形式的初始化矢量。 恰好8个八位字节，即16个字符。 默认情况下，为空字符串。

## 返回值

未加密的字符串。

## 备注

* DES密钥有56个有用位和8个用于奇偶校验的位；这些位将被忽略。
* 该数据将在Windows-1252代码页中作为8位字符串进行解密。
* 加密数据的长度必须为64位的倍数。

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
