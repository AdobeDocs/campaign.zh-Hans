---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 6%
---
# DeployTriggerMessageSingle

在执行实例上发布事务性消息。 如果发布成功，则返回真，否则返回假。

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## 参数

要部署的投放的&#x200B;**deliveryId** ID

**localPublish**&#x200B;仅在控制实例上发布？

## 返回值

**isSuccess**&#x200B;发布完成

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
