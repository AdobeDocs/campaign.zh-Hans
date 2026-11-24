---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 2%
---
# 等待

等待信号。

```text
wait (timeout)
```

## 参数

**超时**&#x200B;等待时间（以毫秒为单位）。

## 返回值

如果在等待时间到期之前收到信号，则布尔值为true。

## 备注

信号由[Wakeup](sm-workflow-wakeup.md)和[WakeupTask](sm-workflow-wakeuptask.md) SOAP方法发出。 使用的协议(UDP)不保证消息接收。 此信号仅对更快地执行操作有用。 警告：在子工作流中永远不会收到此信号。 示例：以下是典型的用法示例：循环处理来自队列的操作(poll())，然后在每个操作之间等待一定的时间。 为强制工作流钝化，还增加了其他延迟。

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## 功能

**类的方法：** [WorkflowTask](c-workflowtask.md)

**可用位置：**

* 工作流
