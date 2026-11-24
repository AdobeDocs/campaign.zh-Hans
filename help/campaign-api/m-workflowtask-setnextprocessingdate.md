---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# setNextProcessingDate

强制任务处理下一个日期。

```text
setNextProcessingDate (timestamp)
```

## 参数

**时间戳**&#x200B;下一个处理日期。 如果为空，则下次处理将立即进行。

## 返回值

无。

## 备注

* 如果由调度程序指定，则使用此方法会覆盖下一个处理日期。
* 下一个处理始终由\*\_recall()函数执行。

## 功能

**类的方法：** [WorkflowTask](c-workflowtask.md)

**可用位置：**

* 工作流
