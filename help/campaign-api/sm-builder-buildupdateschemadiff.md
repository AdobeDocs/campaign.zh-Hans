---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 41%
---
# BuildUpdateSchemaDiff

生成文档，其中描述了实际数据库结构与其逻辑描述之间的差异。

```text
XML sqlSchemaDiff = BuildUpdateSchemaDiff ( XML parameters, Boolean useNamingConventions )
```

## 参数

**参数**&#x200B;更新参数

**useNamingConventions**&#x200B;使用SQL命名约定计算新字段的路径。

## 返回值

**sqlSchemaDiff**&#x200B;生成的架构

## 功能

**架构：** [xtk:builder](s-xtk-builder.md)

**静态：**

是
