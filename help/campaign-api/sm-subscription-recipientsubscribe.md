---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 31%
---
# RecipientSubscribe

为选定的收件人订阅/取消订阅信息服务列表。

```text
XML confirmationIds = RecipientSubscribe ( XML recipientList, XML serviceList, Boolean subscribe, XML sendConfirmation )
```

## 参数

**recipientList**&#x200B;收件人列表

**serviceList**&#x200B;服务列表

**订阅**&#x200B;订阅/取消订阅收件人

**sendConfirmation**&#x200B;发送确认消息

## 返回值

**confirmationIds**&#x200B;确认标识列表

## 功能

**架构：** [nms:subscription](s-nms-subscription.md)

**静态：**

是
