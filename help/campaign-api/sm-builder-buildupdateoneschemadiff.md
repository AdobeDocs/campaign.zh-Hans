---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 48%
---
# BuildUpdateOneSchemaDiff

生成文档，其中描述了物理数据库中的表与该表的逻辑描述之间的差异。

```text
XML sqlSchemaDiff = BuildUpdateOneSchemaDiff ( String schemaId, Boolean useNamingConventions )
```

## 参数

**schemaId**&#x200B;架构标识符

**useNamingConventions**&#x200B;使用SQL命名约定计算新字段的路径。

## 返回值

**sqlSchemaDiff**&#x200B;生成的架构

## 功能

**架构：** [xtk:builder](s-xtk-builder.md)

**静态：**

是
