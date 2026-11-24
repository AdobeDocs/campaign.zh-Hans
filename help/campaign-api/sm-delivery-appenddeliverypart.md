---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 13%
---
# AppendDeliveryPart

将一个部分添加到正在准备的投放中。

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## 参数

表示投放部分（或投放部分的集合）的&#x200B;**deliveryPart**&#x200B;文档。

**重试**&#x200B;指定这是否是提交此投放部分的新尝试。

## 返回值

**deliveryPartId**&#x200B;数据库中的投放部分标识符（当它不是集合时）。

**fatalError**&#x200B;返回一个错误代码，阻止调用者执行停用。 否则，错误可能是暂时的。

与“fatalError”错误代码关联的&#x200B;**fatalErrorMsg**&#x200B;错误消息。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
