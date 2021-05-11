---
solution: Campaign
product: Adobe Campaign
title: 使用活动模式
description: 开始使用模式
translation-type: tm+mt
source-git-commit: e31b7e16cb4d5ed01d615e71fc15485b4e4a1859
workflow-type: tm+mt
source-wordcount: '1242'
ht-degree: 4%

---

# 使用模式{#gs-ac-schemas}

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

Adobe Campaign使用数据模式来：

* 定义应用程序中数据对象与基础数据库表的绑定方式。
* 定义 Campaign 应用程序中不同数据对象之间的链接。
* 定义并描述每个对象中包含的个别字段。

要更好地了解活动内置表及其交互，请参阅[本节](datamodel.md)。

>[!CAUTION]
>
>某些内置活动模式在云数据库上具有关联模式。 这些模式由&#x200B;**Xxl**&#x200B;命名空间标识，不得修改。

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

## 保留命名空间

某些命名空间保留用于描述操作Adobe Campaign应用程序所需的系统实体。 以下命名空间&#x200B;**不得在任何大小写组合中用于标识新模式:**

* **xxl**:保留到Cloud数据库模式,
* **xtk**:预留给平台系统数据，
* **nl**:保留给应用程序的整体使用，
* **nms**:保留给投放(收件人、投放、跟踪等),
* **ncm**:保留给内容管理,
* **temp**:保留给临时模式。

模式的标识键是使用命名空间和冒号分隔的名称构建的字符串；例如：**nms:收件人**。

## 创建或扩展活动模式{#create-or-extend-schemas}

要向活动中某个核心模式(如收件人表(nms:收件人))添加字段或其他元素，必须扩展该模式。

：灯泡：有关详细信息，请参阅[扩展模式](extend-schema.md)。

要添加Adobe Campaign中不存在的全新模式类型（例如合同表），您可以直接创建自定义数据。

：灯泡：有关详细信息，请参阅[创建新模式](create-schema.md)。

![](assets/schemaextension_1.png)


创建或扩展模式后，最佳做法是按如下顺序定义其XML内容元素。

## 明细列表 {#enumerations}

明细列表首先在模式的主元素之前定义。 它们允许您在列表中显示值，以限制用户对给定字段的选择。

示例:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

在定义字段时，您随后可以按如下方式使用此明细列表:

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>您还可以使用用户管理的明细列表（通常在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]**&#x200B;下）来指定给定字段的值。 这些是有效的全局明细列表，如果您的明细列表可能在您所使用的特定模式之外使用，则还是一个更好的选择。

## 键{#keys}

每个表必须至少有一个键，并且通常使用设置为“true”的&#x200B;**@autouuid=true**&#x200B;属性在模式的主元素中自动建立该键。

主键也可以使用&#x200B;**internal**&#x200B;属性进行定义。

示例:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

在此示例中，我们指定的不是让&#x200B;**@autouuid**&#x200B;属性创建名为“id”的默认主键，而是自己的“househId”主键。

>[!CAUTION]
>
>在创建新模式或在模式扩展期间，您需要为整个模式保留相同的主键序列值(@pkSequence)。

：灯泡：了解有关[本节](database-mapping.md#management-of-keys)中的键的更多信息。

## 属性（字段）{#attributes--fields-}

属性允许您定义构成数据对象的字段。 可以使用模式版工具栏中的&#x200B;**[!UICONTROL Insert]**&#x200B;按钮将空属性模板放置到光标所在的XML中。 请阅读[本节](create-schema.md)了解更多信息。

![](assets/schemaextension_2.png)

在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model)的`<attribute>`元素部分中，可以找到属性的完整列表。 以下是一些最常用的属性：**@advanced**、**@dataPolicy**、**@default**、**@desc**、**@enum**、**@expr**、**@label**、**@length**、**@name**、**@notNull**、&lt;a20/@required>**、&lt;a22/@ref>、&lt;a24/@xml>**,&lt;a26/@type>**。**********

:arrow_upper_right:有关每个属性的详细信息，请参阅[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic)中的“属性”说明。

### 示例{#examples}

定义默认值的示例：

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

将公用属性用作字段模板的示例，该字段也标记为必填：

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

使用&#x200B;**@advanced**&#x200B;属性隐藏的计算字段示例：

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

XML字段的示例也存储在SQL字段中，该字段具有&#x200B;**@dataPolicy**&#x200B;属性。

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>尽管大多数属性都根据1-1基数链接到数据库的物理字段，但XML字段或计算字段的情况并非如此。\
>XML字段存储在表的备注字段(“mData”)中。\
>但是，每次启动查询时都动态地创建计算字段，因此它仅存在于应用层中。

## 链接 {#links}

链接是您的模式主元素中最后的一些元素。 它们定义实例中所有不同模式之间的关联方式。

链接在包含其链接的表的&#x200B;**外键**&#x200B;的模式中声明。

有三种类型的基数：1-1、1-N和N-N。默认情况下使用的是1-N类型。

### 示例{#examples-1}

收件人表(现成模式)和自定义事务表之间的1-N链接示例：

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

自定义模式“Car”(在“cus”命名空间中)与收件人表之间的1-1链接示例：

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

收件人表和地址表之间基于电子邮件地址（而非主键）的外部连接示例：

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

此处“xpath-dst”对应于目标模式中的主键，而“xpath-src”对应于源模式中的外键。

## 审核跟踪 {#audit-trail}

您可能希望在模式底部包含的一个有用元素是跟踪元素（审计跟踪）。

请使用下面的示例包括与创建日期、创建数据的用户、日期以及表格中所有数据的上次修改的作者相关的字段：

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 更新数据库结构 {#updating-the-database-structure}

完成并保存更改后，任何可能影响SQL结构的更改都需要应用到数据库。 为此，请使用数据库更新助手。

![](assets/schemaextension_3.png)

如需详细信息，请参阅[此部分](update-database-structure.md)。

>[!NOTE]
>
>当修改不影响数据库结构时，您只需重新生成模式。 为此，请选择要更新的模式，右键单击并选择&#x200B;**[!UICONTROL Actions > Regenerate selected schemas...]**。

