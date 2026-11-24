---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%
---
# FinalizeMidPreparation

在中间源模式下完成对投放的分析。

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## 参数

**deliveryId**&#x200B;投放标识符

**错误代码**&#x200B;营销数据库分析返回的错误代码（不使用方法级别的错误代码）

**属性**&#x200B;要更新的投放属性

**重试**&#x200B;指定这是否为方法调用的重试。

## 返回值

**fatalError**&#x200B;返回一个错误代码，阻止调用者执行停用。 否则，错误可能是暂时的。

与“fatalError”错误代码关联的&#x200B;**fatalErrorMsg**&#x200B;错误消息。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
