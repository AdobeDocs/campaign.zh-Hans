---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 41%
---
# 取消订阅

为收件人退订信息服务

```text
Unsubscribe ( String serviceName, XML recipient )
```

## 参数

**serviceName**&#x200B;信息服务名称列表（以逗号分隔）

**收件人**&#x200B;收件人

## 返回值

无。

## 示例

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## 功能

**架构：** [nms:subscription](s-nms-subscription.md)

**静态：**

是
