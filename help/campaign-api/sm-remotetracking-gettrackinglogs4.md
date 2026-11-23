---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 18%
---
# GetTrackingLogs4

允许使用帖子 4.00 格式检索由远程重定向和 Web 跟踪服务器生成的跟踪日志。

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs4 ( String instance, String dbId, String pointer, Number logCount )
```

## 参数

**实例**&#x200B;短标识符

执行投放的客户的&#x200B;**dbId**&#x200B;数据库标识符

应从中检索日志的&#x200B;**指针**&#x200B;标识符（序列化为int64）。

**logCount**&#x200B;要为请求检索的日志数（0表示默认值），响应返回的日志数。

## 返回值

应从中检索日志的&#x200B;**指针**&#x200B;标识符（序列化为int64）。

**logCount**&#x200B;要为请求检索的日志数（0表示默认值），响应返回的日志数。

**日志**&#x200B;已检索

日志检索请求时服务器处于&#x200B;**srvDate** GMT时间

## 功能

**架构：** [nms:remoteTracking](s-nms-remotetracking.md)

**静态：**

是
