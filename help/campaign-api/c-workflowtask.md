---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%
---
# WorkflowTask（类）

工作流任务的状态。

⌐`WorkflowTask`是无法实例化的类，在名为`task`的工作流活动中只有一个可访问的单个实例。

## 方法

| 方法 | 描述 |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | 将任务标记为已完成。 |
| [postEvent](m-workflowtask-postevent.md) | 激活过渡。 |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | 强制任务处理下一个日期。 |
| [doneTransition](m-workflowtask-donetransition.md) | 返回活动的“完成”过渡。 |
| [errorTransition](m-workflowtask-errortransition.md) | 返回活动的“错误”过渡。 |
| [transitionByType](m-workflowtask-transitionbytype.md) | 返回与给定类型对应的过渡。 |
| [transitionByName](m-workflowtask-transitionbyname.md) | 返回与给定名称对应的过渡。 |
| [过渡](m-workflowtask-transitions.md) | 返回活动的过渡列表。 |
| [等待](m-workflowtask-wait.md) | 等待信号。 |

## 功能

**可用位置：**

* 工作流
