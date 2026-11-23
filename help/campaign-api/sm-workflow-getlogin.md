---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 2%
---
# GetLogin

从执行帐户返回信息。

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

## 返回值

**id**&#x200B;操作员的标识符，如果没有操作员与此工作流关联，则为0。

**登录**&#x200B;操作员的登录名或空字符串（如果没有操作员与此工作流关联）。

**cs**&#x200B;运算符的描述字符串或空字符串（如果没有运算符与此工作流关联）。

## 备注

通过与工作流关联的执行帐户，可以将执行权限强制授予特定操作员，而不是启动工作流的操作员。 复制工作流时，执行帐户不会传播。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
