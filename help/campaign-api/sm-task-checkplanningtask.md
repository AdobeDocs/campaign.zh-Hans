---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 6%
---
# 检查计划任务

用于检查任务运算符计划内的重载的内部函数（在重载的情况下返回“true”）。 此功能还会检查相关任务计划的一致性，并在必要时对其进行更新。

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## 参数

**taskId**&#x200B;任务标识符。

## 返回值

**workloadAlert**&#x200B;资源过载警告

## 功能

**架构：** [nms:task](s-nms-task.md)

**静态：**

是
