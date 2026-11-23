---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 22%
---
# StoreMirrorPageInfoEx

添加信息以生成一组投放部分的镜像页面。

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfoEx ( Number deliveryId, Boolean notification, Number partsCount, Number firstPartId, Number notificationId )
```

## 参数

**deliveryId**&#x200B;投放标识符

**通知**&#x200B;是否为通知？

**partsCount**&#x200B;部件数

**firstPartId**&#x200B;第一部分标识符

**notificationId**&#x200B;通知标识符

## 返回值

**fatalError**&#x200B;返回一个错误代码，阻止调用者执行停用。 否则，错误可能是暂时的。

与“fatalError”错误代码关联的&#x200B;**fatalErrorMsg**&#x200B;错误消息。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
