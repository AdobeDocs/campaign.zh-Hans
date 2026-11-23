---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 19%
---
# CreateTrackingInstanceEx

在重定向服务器上创建或配置跟踪实例

```text
CreateTrackingInstanceEx ( String internalPwd, String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword, String host, String imsOrgId )
```

## 参数

**internalPwd**&#x200B;内部密码

跟踪服务器的&#x200B;**serverUrl**&#x200B;外部URL

**secureServerUrl**&#x200B;跟踪服务器的外部安全URL

**serverUrlList**&#x200B;跟踪服务器的内部URL

要创建的实例的&#x200B;**instanceName**&#x200B;名称

**cryptedPassword**&#x200B;加密密码

与实例关联的&#x200B;**主机** DNS掩码

**imsOrgId** IMS组织ID

## 返回值

无。

## 功能

**架构：** [nms:trackingUrl](s-nms-trackingurl.md)

**静态：**

是
