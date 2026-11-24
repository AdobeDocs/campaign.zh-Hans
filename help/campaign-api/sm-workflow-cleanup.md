---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 5%
---
# 清理

清除工作流历史记录。

```text
Cleanup ( String workflowId )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

## 返回值

无。

## 备注

删除所有已处理的事件、完成的任务、失败的任务和日志消息。 如果工作流已完成，也会从图中删除进度。 此方法仅删除工作流引擎不再使用的数据，并且不会影响工作流的行为。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
