---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 17%
---
# SubmitFromModel

从模板提交作业

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## 参数

**架构**&#x200B;作业模板架构

**where**&#x200B;模板选择表达式

**methodName**&#x200B;要调用的方法的名称

要添加到模板的&#x200B;**diff** XML内容

**异步**&#x200B;执行异步作业提交

## 返回值

刚刚创建的作业的&#x200B;**jobId**&#x200B;标识符

## 功能

**架构：** [xtk:job](s-xtk-job.md)

**静态：**

是
