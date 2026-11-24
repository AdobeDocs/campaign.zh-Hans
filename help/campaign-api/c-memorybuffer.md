---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 6%
---
# MemoryBuffer（类）

表示内存中存储的二进制内容。

是一个中间对象，用于处理往来于文件的数据。

## 方法

| 方法 | 描述 |
| --- | --- |
| [处置](m-memorybuffer-dispose.md) | 释放对象使用的资源。 |
| [加载](m-memorybuffer-load.md) | 将文件的内容加载到缓冲区。 |
| [保存](m-memorybuffer-save.md) | 将缓冲区的内容保存到文件中。 |
| [toXML](m-memorybuffer-toxml.md) | 返回从[MemoryBuffer](c-memorybuffer.md)的内容获得的XML JavaScript对象。 此函数已过时，请使用[toDocument()](m-memorybuffer-todocument.md) |
| [toDocument](m-memorybuffer-todocument.md) | 从该缓冲区的文本内容返回XML文档。 |
| [toString](m-memorybuffer-tostring.md) | 以字符串形式返回[MemoryBuffer](c-memorybuffer.md)的内容。 |
| [fromString](m-memorybuffer-fromstring.md) | 在缓冲区中加载字符串的内容。 |
| [toBase64](m-memorybuffer-tobase64.md) | 转换以base 64编码的缓冲区或部分字符串。 |
| [appendBase64](m-memorybuffer-appendbase64.md) | 将数据从以base 64编码的字符串附加到缓冲区的末尾。 |
| [removeAll](m-memorybuffer-removeall.md) | 刷新缓冲区。 |
| [sha1](m-memorybuffer-sha1.md) | 计算MemoryBuffer内容的SHA-1签名。 |
| [sha224](m-memorybuffer-sha224.md) | 计算MemoryBuffer内容的SHA-2 224位签名。 |
| [sha256](m-memorybuffer-sha256.md) | 计算MemoryBuffer内容的SHA-2 256位签名。 |
| [sha384](m-memorybuffer-sha384.md) | 计算MemoryBuffer内容的SHA-2 384位签名。 |
| [sha512](m-memorybuffer-sha512.md) | 计算MemoryBuffer内容的SHA-2 512位签名。 |
| [fromHexString](m-memorybuffer-fromhexstring.md) | 在缓冲区中加载十六进制字符串的内容。 |
| [toHexString](m-memorybuffer-tohexstring.md) | 将缓冲区转换为十六进制字符串。 |
| [hmac](m-memorybuffer-hmac.md) | 计算缓冲区的MD5、SHA-1或SHA-256哈希值。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [大小](p-memorybuffer-size.md) | 返回缓冲区的大小（字节）。 |
| [isEmpty](p-memorybuffer-isempty.md) | 如果缓冲区为空，则返回true。 |

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
