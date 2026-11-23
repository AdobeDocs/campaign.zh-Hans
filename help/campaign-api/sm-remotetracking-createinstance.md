---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 15%
---
# 创建实例

> 警告：此函数适用于内部部署环境。

用于创建跟踪实例

```text
CreateInstance ( String instanceName, String hosts, String dbId, String cryptedPwd, String lang )
```

## 参数

要创建的实例的&#x200B;**instanceName**&#x200B;名称

**主机**&#x200B;与实例关联的DNS掩码

执行投放的客户的&#x200B;**dbId**&#x200B;数据库标识符

**cryptedPwd**&#x200B;用于跟踪的加密密码

**lang**&#x200B;实例语言

## 返回值

无。

## 功能

**架构：** [nms:remoteTracking](s-nms-remotetracking.md)

**静态：**

是
