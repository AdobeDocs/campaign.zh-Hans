---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%
---
# onTrace

添加或删除跟踪消息拦截函数。

```text
onTrace ( [function ])
```

## 参数

**函数**&#x200B;要添加的拦截函数。 如果省略此参数，则将删除最近添加的函数。

## 返回值

无。

## 备注

函数采用具有以下属性的和对象作为参数：

* 重力（字符串） — 消息的严重性（“错误”、“警告”、“信息”、“状态”、“详细”）
* 类型（字符串） — 消息类型（“日志”、“wdbc”等）
* message（字符串） — 消息

该函数受保护以防止重新进入：它不会截获它自己创建的跟踪消息。 示例：

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

file.close()
```

## 功能

**类的方法：** [应用程序](c-application.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
