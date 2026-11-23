---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 25%
---
# GetAvailableReportsEx

恢复不带历史记录的报告列表，并考虑数据排序条件和页码

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## 参数

**activeContext**&#x200B;活动上下文（选择，全局）

涉及&#x200B;**架构**&#x200B;架构

**选择**&#x200B;选定实体的ID，以“，”分隔

**where**&#x200B;正在筛选“where”节点

**orderBy**&#x200B;排序“orderBy”节点

**editionMode**&#x200B;编辑期间，未发布的报告也可见

**lineCount**&#x200B;要收集的报告数

要应用于页码的&#x200B;**startLine**&#x200B;偏移量

**locationName**

## 返回值

**个报告**&#x200B;合格报告列表

## 功能

**架构：** [xtk:report](s-xtk-report.md)

**静态：**

是
