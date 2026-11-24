---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 39%
---
# DeclareTableSpaces

在 Adobe Campaign 数据库中声明使用可通过外部帐户访问的远程数据库中的特定表空间所需的选项。

```text
DeclareTableSpaces ( String extAccountId, String tableSpace, String tableSpaceIndex )
```

## 参数

**extAccountId**&#x200B;外部帐户的内部名称或主键

**tableSpace**&#x200B;用于远程工作表的表空间的名称

**tableSpaceIndex**&#x200B;用于索引的表空间的名称

## 返回值

无。

## 功能

**架构：** [nms:extAccount](s-nms-extaccount.md)

**静态：**

是
