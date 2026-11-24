---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 15%
---
# 执行

execute命令的别名。 此函数已过时，请使用[execute()](m-dbengine-execute.md)

```text
exec (command [, value1, ... ])
```

## 参数

**命令** SQL命令。

**value1， ...**&#x200B;命令的变量。

## 返回值

如果适用于执行的命令，则更新或插入的录制数，如果不是零。

## 功能

**类的方法：** [DBEngine](c-dbengine.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
