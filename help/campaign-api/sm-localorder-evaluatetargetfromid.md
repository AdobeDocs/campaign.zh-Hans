---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%
---
# EvaluateTargetFromId

评估与订单关联的每个活动投放的活动定位。 此评估将在使用操作员权限订购时以及在创建本地营销活动之前执行。

```text
XML result = EvaluateTargetFromId ( Number orderId )
```

## 参数

**orderId**&#x200B;订单ID。

## 返回值

**结果**&#x200B;每个活动投放的计数结果。

## 功能

**架构：** [nms:localOrder](s-nms-localorder.md)

**静态：**

是
