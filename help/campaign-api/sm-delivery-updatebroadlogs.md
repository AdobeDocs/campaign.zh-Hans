---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 31%
---
# UpdateBroadLogs

更新投放日志的状态，执行错误处理并更新投放计数器。

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## 参数

**deliveryId**&#x200B;投放标识符

**日志**&#x200B;包含要更新的nms:broadLog记录的集合（必须指定@id、@status、@eventDate和@lastModified）

**deliveryMustExist**&#x200B;指定是否针对无效的投放标识符引发错误。

## 返回值

无。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
