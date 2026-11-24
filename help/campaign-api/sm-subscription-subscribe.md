---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# 订阅

创建或更新信息服务的收件人订阅

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## 参数

**serviceName**&#x200B;信息服务名称列表（以逗号分隔）

**收件人**&#x200B;要注册并可选择创建的收件人

**创建**&#x200B;如果收件人不存在，则创建收件人

## 返回值

无。

## 示例

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## 功能

**架构：** [nms:subscription](s-nms-subscription.md)

**静态：**

是
