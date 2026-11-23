---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 33%
---
# GetTrackingInfo

允许远程重定向服务器下载有关投放操作的信息。

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## 参数

**实例**&#x200B;实例名称

执行投放的客户的&#x200B;**dbId**&#x200B;数据库标识符

**deliveryId**&#x200B;投放ID。

## 返回值

**文档**&#x200B;包含此投放的跟踪信息的文档

## 功能

**架构：** [nms:remoteTracking](s-nms-remotetracking.md)

**静态：**

是
