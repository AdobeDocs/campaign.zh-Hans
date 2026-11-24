---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 4%
---
# 获取状态

获取作业处理进度信息。 警告：此API不保证返回唯一日志条目的列表（调用方必须使用其ID删除重复项）。

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## 参数

**id**&#x200B;作业标识符

**lastLogId**&#x200B;上次调用中返回的最后一个日志条目的标识符

**maxLogCount**&#x200B;要发送的日志条目的最大数量

## 返回值

**状态**&#x200B;作业状态

**returnLogs**&#x200B;日志消息

**属性**&#x200B;属性（进度……）

## 功能

**架构：** [xtk:job](s-xtk-job.md)

**静态：**

是
