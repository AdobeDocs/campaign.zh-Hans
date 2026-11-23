---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 11%
---
# hmac

计算缓冲区的MD5、SHA-1或SHA-256哈希值。

```text
hmac (key [, algo ])
```

## 参数

**key**&#x200B;键，以缓冲区的形式。

要使用的&#x200B;**算法**&#x200B;哈希类型。 可能的值为“MD5”、“SHA1”或“SHA256”。 这些值不区分大小写，因此可以使用小写或大写形式输入值。 默认情况下，如果未指定参数，将选择值“SHA1”。

## 返回值

缓冲区的哈希MD5、SHA-1或SHA-256（根据选择的哈希类型）。

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
