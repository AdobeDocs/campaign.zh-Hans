---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 33%
---
# GetDlStatusAndLogs

从日志中检索最后的日志和投放状态。

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## 参数

**deliveryId**&#x200B;投放标识符

**lastLogId**&#x200B;上次调用中返回的最后一个日志条目的标识符

## 返回值

**deliveryState**&#x200B;投放状态

**returnLogs**&#x200B;日志消息

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
