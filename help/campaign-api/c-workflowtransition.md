---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 9%
---
# WorkflowTransition（类）

表示工作流过渡。

过渡是一个不透明对象，它使用诸如或之类的方法恢复，并且用于实现任务过渡。

示例：

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## 功能

**可用位置：**

* 工作流
