---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# logError

向工作流实例的日志添加一条错误消息，并暂停脚本的执行。

```text
logError (message)
```

## 参数

**消息**&#x200B;要添加到日志中的消息。

## 返回值

无。

## 备注

正在进行的任务的行为就像发生了错误一样：标记了错误并暂停了工作流。 因此，此函数在明确引发工作流错误并暂停该工作流时非常有用。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 投放消息
* 类型规则
* 导入
* JSSP
* SOAP方法
* WebApp
* 工作流
