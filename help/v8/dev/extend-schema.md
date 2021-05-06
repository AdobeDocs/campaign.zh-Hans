---
solution: Campaign Classic
product: campaign
title: 扩展活动模式
description: 了解如何扩展活动模式
translation-type: tm+mt
source-git-commit: 779542ab70f0bf3812358884c698203bab98d1ce
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# 扩展模式{#extend-schemas}

本文介绍如何配置扩展模式，以扩展Adobe Campaign库的概念数据模型。

：灯泡：要更好地了解活动内置表及其交互，请参阅[此页](datamodel.md)。

应用中所承载数据的物理和逻辑结构以 XML 格式进行描述。它遵循特定于Adobe Campaign的语法，称为&#x200B;**模式**。

模式是与数据库表关联的XML文档。 它定义数据结构并描述表的SQL定义：

* 表的名称
* 字段
* 与其他表的链接

还描述了用于存储数据的XML结构：

* 元素和属性
* 元素层次
* 元素和属性类型
* 默认值
* 标签、说明和其他属性。

模式允许您在数据库中定义实体。 每个实体都有一个模式。

## 模式{#syntax-of-schemas}的语法

模式的根元素为&#x200B;**`<srcschema>`**。 它包含&#x200B;**`<element>`**&#x200B;和&#x200B;**`<attribute>`**&#x200B;子元素。

第一个&#x200B;**`<element>`**&#x200B;子元素与实体的根重合。

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>实体的根元素与模式同名。

![](assets/schema_and_entity.png)

**`<element>`**&#x200B;标签定义实体元素的名称。 **`<attribute>`** 模式的标签定义已链接到的标 **`<element>`** 签中属性的名称。

## 模式{#identification-of-a-schema}的标识

数据模式由其名称和命名空间标识。

命名空间允许您按目标区域对一组模式进行分组。 例如，**cus**&#x200B;命名空间用于特定于客户的配置(**customers**)。

>[!CAUTION]
>
>作为标准，命名空间的名称必须简洁明了，并且必须只包含符合XML命名规则的授权字符。
>
>标识符不能以数字字符开头。

某些命名空间保留以说明操作Adobe Campaign应用程序所需的系统实体：

* **xxl**:关于云数据库模式,
* **xtk**:关于平台系统数据，
* **nl**:关于申请的全面使用，
* **nms**:投放(收件人、投放、跟踪等),
* **ncm**:关于内容管理,
* **temp**:为临时模式保留。

模式的标识键是使用命名空间和冒号分隔的名称构建的字符串；例如：**nms:收件人**。
