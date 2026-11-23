---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%
---
# GetQuarantines

检索最新的隔离和隔离出口。

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## 参数

**startDate**&#x200B;检索自此日期以来修改的隔离。 如果为空，则使用指针值。

**pointerName**&#x200B;检索自此指针以来修改的隔离（可选）。

**quarantineCount**&#x200B;要检索的最大隔离数量，前提是它们未在同一秒内更新。

**callerDate**&#x200B;调用方引用日期。 允许您修改隔离日期引用（可选）。

## 返回值

**结果**&#x200B;输出文档，隔离列表。

**nextDate**&#x200B;第一个未检索隔离的日期（严格高于startDate）。

**hasMore**&#x200B;如果是，则仍存在要检索的隔离。

## 功能

**架构：** [nms:address](s-nms-address.md)

**静态：**

是
