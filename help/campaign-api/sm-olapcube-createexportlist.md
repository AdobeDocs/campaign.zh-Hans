---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 30%
---
# CreateExportList

创建购物车中的实体将导出到的列表。

```text
Number listId = CreateExportList ( String label, Number folderId )
```

## 参数

**标签**&#x200B;列表的标签

将在其中创建列表的文件夹的&#x200B;**folderId** ID（0表示使用默认文件夹）。

## 返回值

新创建列表的&#x200B;**listId** ID

## 功能

**架构：** [xtk:olapCube](s-xtk-olapcube.md)

**静态：**

是
