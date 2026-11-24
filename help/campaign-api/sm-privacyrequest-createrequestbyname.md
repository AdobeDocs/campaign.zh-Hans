---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%
---
# CreateRequestByName

使用命名空间内部名称创建新的隐私请求

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## 参数

**namespaceName**&#x200B;命名空间内部名称

**reconciliationValue**&#x200B;协调值

**类型**&#x200B;协调值

**confirmDeletePending**&#x200B;删除数据前请求确认

**法规**&#x200B;法规类型具有以下值：

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## 返回值

新创建的请求的&#x200B;**id** ID

## 功能

**架构：** [nms:privacyRequest](s-nms-privacyrequest.md)

**静态：**

是
