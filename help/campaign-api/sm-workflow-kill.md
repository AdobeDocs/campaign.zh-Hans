---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 3%
---
# 终止

无条件停止工作流。

```text
Kill ( String workflowId )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

## 返回值

无。

## 备注

如果无法正常停止工作流，则此方法很有用。 如果工作流或任务具有特定的关联性，或者如果处理此关联性的wfserver模块不再运行，则可能会发生这种情况。 在这种情况下，工作流仍标记为“已请求停止”，并且只能由Kill命令停止。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
