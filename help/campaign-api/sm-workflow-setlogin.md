---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 3%
---
# SetLogin

更改执行帐户。

```text
SetLogin ( String workflowId, String login )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

**登录**&#x200B;操作员的登录名或空字符串（如果没有操作员与此工作流关联）。

## 返回值

无。

## 备注

通过与工作流关联的执行帐户，可以将执行权限强制授予特定操作员，而不是启动工作流的操作员。 复制工作流时，执行帐户不会传播。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
