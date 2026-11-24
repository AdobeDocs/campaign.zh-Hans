---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 19%
---
# DumpInstanceStateEx

返回服务器进程的状态

```text
XML monitoring = DumpInstanceStateEx ( String mask, Boolean includeDead, Boolean noDatabaseCheck, Number criticalLevel )
```

## 参数

要考虑的实例的&#x200B;**掩码**&#x200B;掩码

**includeDead**&#x200B;添加无效进程列表

**noDatabaseCheck**&#x200B;不检查来自数据库对象的警报

**criticalLevel**&#x200B;筛选返回警报的严重性

## 返回值

**监视**

## 功能

**架构：** [nl:monitoring](s-nl-monitoring.md)

**静态：**

是
