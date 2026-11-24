---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%
---
# 回复

响应正在进行的验证类型任务。

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

**taskIdentifier**&#x200B;审批类型任务的标识符（@taskIdentifier字段）。

**响应**&#x200B;与响应关联的注释。

**choice**&#x200B;响应的选择。 此选项必须与要激活的过渡名称匹配。

## 返回值

无。

## 备注

当前操作员必须在分配给任务的组中。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
