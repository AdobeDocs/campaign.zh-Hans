---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%
---
# Postevent

从任何类型的活动生成事件。

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

**活动**&#x200B;事件开始的活动的名称

**过渡**&#x200B;要激活的过渡的名称。 如果此名称为空，则事件将在首次有效过渡时发出（忽略到期类型事件）。

**参数** XML元素形式的事件参数。 元素的名称必须为变量。 如果不希望传递变量，则可以使用空元素&lt;variables/>或空字符串“”。

**完成**&#x200B;指定活动的所有挂起任务已完成。

## 返回值

无。

## 备注

* 该命令以异步模式执行，在方法返回后不会立即生效。
* 调用此方法时必须启动目标工作流。 如果未启动，则会将错误写入相应的日志文件。
* 如果在调用方法时暂停目标工作流，则命令将保留在队列中，直到恢复工作流为止。
* 活动没有限制：没有必要让任务正在进行中，甚至没有任务可以完成。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
