---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 4%
---
# NormalizeField

```text
NormalizeField ( XML selectedWebApp, XML archivedField, String newSQLName, String tableName, String schemaId, Boolean rename )
```

## 参数

**selectedWebApp**&#x200B;可以包含要标准化的字段的调查列表。

**archivedField**&#x200B;要标准化的字段信息。

**newSQLName**&#x200B;此字段的新SQL名称。

**tableName**&#x200B;将包含新SQL字段的表的名称。

**schemaId**&#x200B;架构标识符（视图），用于添加属于新字段的引用（可选）。

**重命名**&#x200B;同时重命名以前标准化的字段。

## 返回值

无。

## 功能

**架构：** [nms:webApp](s-nms-webapp.md)

**静态：**

是
