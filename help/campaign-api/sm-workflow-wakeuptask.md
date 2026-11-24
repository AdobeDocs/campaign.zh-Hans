---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 3%
---
# WakeupTask

强制提前处理一个或多个待处理任务。

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

**taskIdentifier**&#x200B;任务的标识符（@taskIdentifier字段）或空字符串强制提前处理与给定活动关联的所有待处理任务。

**activityName**&#x200B;强制提前处理所有关联任务的活动名称或空字符串。

## 返回值

无。

## 备注

如果既没有指定taskIdentifier，也没有指定activityName，则会考虑所有待处理任务。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
