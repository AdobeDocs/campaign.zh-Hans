---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%
---
# Submitdelivery

从场景创建和提交投放（来自其内部名称）。

```text
Number deliveryId = SubmitDelivery ( String scenarioName, XML content )
```

## 参数

投放模板的&#x200B;**scenarioName**&#x200B;内部名称

要添加到模板的&#x200B;**内容** XML内容

## 返回值

新投放的&#x200B;**deliveryId**&#x200B;标识符（即使分析失败也返回）

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
