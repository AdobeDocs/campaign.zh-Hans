---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# GetMidBroadLogs

检索在中间源模式下最后修改的投放日志。

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## 参数

**startDate**&#x200B;检索自此日期以来修改的日志（在中间源服务器上）。

**logCount**&#x200B;要检索的最大日志数，前提是这些日志没有在同一秒内更新。

发行服务器的&#x200B;**emitterDate**&#x200B;参考日期。 用于调整投放日志日期。

## 返回值

**结果**&#x200B;输出文档，投放日志列表。

**nextDate**&#x200B;检索到的第一个日志的日期（大于startDate）。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
