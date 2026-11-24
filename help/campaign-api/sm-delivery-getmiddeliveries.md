---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 19%
---
# GetMidDeliveries

检索在中间源模式下最后修改的投放状态。

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## 参数

**startDate**&#x200B;检索自此日期以来的修改（在中间源服务器上）。

**maxCount**&#x200B;要检索的最大投放数，前提是它们未在同一秒内更新。

发行服务器的&#x200B;**emitterDate**&#x200B;参考日期。 用于调整投放日期。

## 返回值

**结果**&#x200B;输出文档，投放列表已更新。

下一次调用的&#x200B;**nextDate**&#x200B;开始日期。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
