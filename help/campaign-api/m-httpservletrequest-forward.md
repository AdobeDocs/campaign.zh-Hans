---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# 转发

无需通过客户端即可将查询重定向到其他页面。

```text
forward (location)
```

## 参数

**位置**&#x200B;重定向URL。

## 返回值

无。

## 备注

forward允许您在将查询转移到另一个将生成响应内容的资源之前执行初步过程。 在转发调用之前，不得将数据作为响应返回客户端，否则将引发错误。

## 功能

**类的方法：** [HttpServletRequest](c-httpservletrequest.md)

**可用位置：**

* JSSP
* WebApp
