---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 3%
---
# Evaluatecontent

评估链接到订单的投放内容。 此评估将在使用操作员权限订购时以及在创建本地营销活动之前执行。

```text
XML result = EvaluateContent ( XML order, Number deliveryId, String contentType, Number seedMemberId )
```

## 参数

包含订单信息的&#x200B;**订单**&#x200B;元素。

要评估的投放&#x200B;**deliveryId** ID。

**contentType**&#x200B;要返回的内容类型（电子邮件的html或文本；其他渠道的空字符串）。

用于内容个性化的&#x200B;**seedMemberId**&#x200B;种子地址ID。

## 返回值

**结果**&#x200B;评估的内容。

## 功能

**架构：** [nms:localOrder](s-nms-localorder.md)

**静态：**

是
