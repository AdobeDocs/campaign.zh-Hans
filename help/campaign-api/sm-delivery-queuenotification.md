---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 21%
---
# 队列通知

请求对引用投放模板的通知进行排队。

```text
QueueNotification ( String scenarioName, XML target )
```

## 参数

**scenarioName**&#x200B;模板的内部名称

**目标**&#x200B;投放目标人群

## 返回值

无。

## 备注

此API只能在Web应用程序/在线调查的上下文中使用。 与SubmitNotification不同，QueueNotification使用专用线程处理排队通知。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
