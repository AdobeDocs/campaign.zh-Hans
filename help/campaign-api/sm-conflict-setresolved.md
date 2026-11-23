---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%
---
# SetResolved

声明一个实体不再有冲突。

```text
SetResolved ( String conflictId )
```

## 参数

**conflictId**&#x200B;冲突标识符。

## 返回值

无。

## 备注

解决所有冲突后，此方法使您可以将图元放回其正常位置。 调用此方法之前，必须解决所有冲突的属性和元素。

## 功能

**架构：** [xtk:conflict](s-xtk-conflict.md)

**静态：**

是
