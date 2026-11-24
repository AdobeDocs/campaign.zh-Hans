---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%
---
# GetReportData

```text
XML result = GetReportData ( Number cubeId, String queryDef, Boolean selectAll, Boolean useAggregates, XML cube )
```

## 参数

**cubeId**&#x200B;多维数据集标识符。 如果多维数据集作为参数传递，则可以设置为0。

报告中定义了&#x200B;**queryDef** QueryDef

**全选** Select全部

**useAggregates**&#x200B;启用聚合使用

描述多维数据集的&#x200B;**多维数据集** XML。

## 返回值

**结果**&#x200B;结果

## 功能

**架构：** [xtk:olapCube](s-xtk-olapcube.md)

**静态：**

是
