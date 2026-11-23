---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 44%
---
# GenCreateOrUpdateSchemaSequenceDDL

生成用于创建或更新 autoPk 架构序列的 SQL 脚本

```text
String sqlDDL = GenCreateOrUpdateSchemaSequenceDDL ( String schemaId, String newSequence, String oldSequence )
```

## 参数

**schemaId**&#x200B;架构标识符

**newSequence**&#x200B;新序列

**oldSequence**&#x200B;旧序列

## 返回值

**sqlDDL** SQL脚本

## 功能

**架构：** [xtk:builder](s-xtk-builder.md)

**静态：**

是
