---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 12%
---
# getNewIds

返回内部数据库键的ID列表。

```text
getNewIds (count [, sequence ])
```

## 参数

**count**&#x200B;方法必须返回的ID数。

**序列**&#x200B;要使用的序列的名称。

## 返回值

包含ID列表的表：

## 备注

此方法等效于NLWS.xtkSession.GetNewIds()和NLWS.xtkSession.GetNewIdsEx() SOAP方法，但效率更高。

## 功能

**类的方法：** [应用程序](c-application.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
