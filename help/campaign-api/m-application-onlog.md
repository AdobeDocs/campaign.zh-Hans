---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 6%
---
# onLog

为写入日志的消息添加或删除侦听函数

```text
onLog ( [function ])
```

## 参数

**函数**&#x200B;要添加的拦截函数。 如果省略此参数，则将删除最近添加的函数。

## 返回值

无。

## 备注

首先调用最近添加的函数。 函数采用具有以下属性的和对象作为参数：

* 类型（数字） — 消息类型（0=错误，1=警告，2=信息，3=状态，4=详细）
* 代码（编号） — 错误代码（如果不是错误，则为0）
* 对象（字符串） — 链接到消息的对象（未使用）
* message（字符串） — 消息

函数必须返回布尔值。 值为true将阻止任何后续的侦听函数接收消息。 该函数受到保护以防止重新进入：它不会拦截写入日志本身的消息。 示例：

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

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
