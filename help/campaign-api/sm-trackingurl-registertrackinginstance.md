---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 28%
---
# RegisterTrackingInstance

审批重定向服务器上的跟踪实例（通过设置数据库标识符）。

```text
RegisterTrackingInstance ( String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword )
```

## 参数

跟踪服务器的&#x200B;**serverUrl**&#x200B;外部URL

**secureServerUrl**&#x200B;跟踪服务器的外部安全URL

**serverUrlList**&#x200B;跟踪服务器的内部URL

要批准的实例的&#x200B;**instanceName**&#x200B;名称

**cryptedPassword**&#x200B;加密密码

## 返回值

无。

## 功能

**架构：** [nms:trackingUrl](s-nms-trackingurl.md)

**静态：**

是
