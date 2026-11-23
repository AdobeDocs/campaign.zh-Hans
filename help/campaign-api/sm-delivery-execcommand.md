---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 26%
---
# 执行命令

在投放时执行命令。

```text
Number newState = ExecCommand ( String deliveryId, String command )
```

## 参数

**deliveryId**&#x200B;投放标识符

**命令**&#x200B;命令名称（“播放”、“暂停”或“停止”）

## 返回值

命令执行后&#x200B;**newState**&#x200B;投放状态

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
