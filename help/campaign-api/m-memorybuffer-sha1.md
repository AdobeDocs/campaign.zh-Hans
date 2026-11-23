---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%
---
# sha1

计算MemoryBuffer内容的SHA-1签名。

```text
sha1 ()
```

## 参数

无。

## 返回值

一个字符串，它是SHA-1签名的十六进制表示形式。

## 备注

示例：

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

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
