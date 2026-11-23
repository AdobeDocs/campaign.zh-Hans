---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateRequestByName

使用命名空间内部名称创建新的 GDPR 请求

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending )
```

## 参数

**namespaceName**&#x200B;命名空间内部名称

**reconciliationValue**&#x200B;协调值

**类型**&#x200B;协调值

**confirmDeletePending**&#x200B;删除数据前请求确认

## 返回值

新创建的请求的&#x200B;**id** ID

## 功能

**架构：** [nms:gdprRequest](s-nms-gdprrequest.md)

**静态：**

是
