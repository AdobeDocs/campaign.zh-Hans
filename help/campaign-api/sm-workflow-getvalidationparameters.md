---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 2%
---
# GetValidationParameters

返回正在进行的工作流任务的参数。

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

**taskIdentifier**&#x200B;审批类型任务的标识符（@taskIdentifier字段）。

## 返回值

**content**&#x200B;包含参数的XML文档。

## 备注

返回的文档包含与验证相关的所有信息，哪些人做出了回应，哪些人仍可能做出回应。

* title、creationDate、processingDate、timeout、status、abortReason和completionDate属性对应于验证任务中的属性。
* isAssignee：当前操作员在分配给此任务的组中。
* hasResponded：当前操作员已响应。
* canReply：当前操作员可以响应(要么还没有人响应，要么已授权多个响应。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
