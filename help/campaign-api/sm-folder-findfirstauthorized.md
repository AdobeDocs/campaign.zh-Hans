---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# FindFirstAuthorized

为当前用户查找满足 folderFilter 条件的第一个合格文件夹。

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## 参数

**folderFilter**&#x200B;文件夹筛选器

**writeAccess**&#x200B;返回的文件夹必须可写

**orgUnit**&#x200B;返回的文件夹必须与指定的组织实体兼容

## 返回值

**folderEntity**&#x200B;返回关联的文件夹实体（null表示未找到文件夹）

## 功能

**架构：** [xtk:folder](s-xtk-folder.md)

**静态：**

是
