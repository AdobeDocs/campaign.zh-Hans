---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# getAsModel

```text
XML parentOut = getAsModel ( String refIdName, Number refIdValue, XML selection, XML parentIn )
```

## 参数

**refIdName**&#x200B;包含要关联的实体标识符的属性（例如“delivery-id”）

要关联的实体的&#x200B;**refIdValue**&#x200B;标识符（“refIdName”的值）

**selection**&#x200B;包含所选模板标识符的元素

包含现有种子地址的&#x200B;**parentIn**&#x200B;元素

## 返回值

**parentOut**&#x200B;返回添加了新模板的元素

## 功能

**架构：** [nms:seedMember](s-nms-seedmember.md)

**静态：**

是
