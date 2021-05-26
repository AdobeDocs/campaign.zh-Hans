---
solution: Campaign v8
product: Adobe Campaign
title: 使用Campaign模式
description: 模式入门
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 4%

---

# 使用架构{#gs-ac-schemas}

应用中所承载数据的物理和逻辑结构以 XML 格式进行描述。它遵循Adobe Campaign特有的语法，称为&#x200B;**schema**。

模式是与数据库表关联的XML文档。 它定义了数据结构并描述了表的SQL定义：

* 表的名称
* 字段
* 与其他表的链接

它还描述了用于存储数据的XML结构：

* 元素和属性
* 元素层次结构
* 元素和属性类型
* 默认值
* 标签、描述和其他属性。

通过架构，您可以定义数据库中的实体。 每个实体都有一个架构。

Adobe Campaign采用数据模式：

* 定义应用程序中的数据对象如何与基础数据库表绑定。
* 定义 Campaign 应用程序中不同数据对象之间的链接。
* 定义并描述每个对象中包含的个别字段。

要更好地了解Campaign内置表及其交互，请参阅[此部分](datamodel.md)。

>[!CAUTION]
>
>某些内置的Campaign架构在云数据库上具有关联的架构。 这些架构由&#x200B;**Xxl**&#x200B;命名空间标识，不得修改或扩展。

## 架构{#syntax-of-schemas}的语法

架构的根元素为&#x200B;**`<srcschema>`**。 它包含&#x200B;**`<element>`**&#x200B;和&#x200B;**`<attribute>`**&#x200B;子元素。

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
>实体的根元素与架构同名。

![](assets/schema_and_entity.png)

**`<element>`**&#x200B;标记定义实体元素的名称。 **`<attribute>`** 架构的标记定义它们所链接的标 **`<element>`** 记中属性的名称。

## 架构{#identification-of-a-schema}的标识

数据架构通过其名称及其命名空间进行标识。

命名空间允许您按关注区域对一组架构进行分组。 例如， **cus**&#x200B;命名空间用于特定于客户的配置(**customers**)。

>[!CAUTION]
>
>作为标准，命名空间的名称必须简洁明了，并且必须只包含根据XML命名规则授权的字符。
>
>标识符不得以数字字符开头。

## 保留的命名空间{#reserved-namespaces}

某些命名空间是保留的，用于描述操作Adobe Campaign应用程序所需的系统实体。 在任何大写/小写组合中，不得使用以下命名空间&#x200B;**来标识新架构：**

* **xxl**:保留给云数据库架构
* **xtk**:平台系统数据保留
* **nl**:保留给应用程序的整体使用
* **nms**:保留给投放（收件人、投放、跟踪等）
* **ncm**:内容管理保留
* **临时**:保留给临时架构
* **crm**:保留到CRM连接器集成

架构的标识键是使用命名空间和名称以冒号分隔的字符串；例如：**nms:recipient**。

## 创建或扩展Campaign模式{#create-or-extend-schemas}

要向Campaign中的一个核心数据模式(例如收件人表(nms:recipient))添加字段或其他元素，您必须扩展该模式。

[!DNL :bulb:] 有关更多信息，请参阅 [扩展模式](extend-schema.md)。

要添加Adobe Campaign中不存在的全新数据类型（例如合同表），您可以直接创建自定义架构。

[!DNL :bulb:] 有关更多信息，请参 [阅创建新架构](create-schema.md)。

![](assets/schemaextension_1.png)


创建或扩展架构以在中工作后，最佳做法是按它们在下面显示的顺序定义其XML内容元素。

## 明细列表 {#enumerations}

首先，在架构的主元素之前定义枚举。 利用这些值，可在列表中显示值，以限制用户对给定字段所做的选择。

示例:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

在定义字段时，您随后可以使用此枚举，如下所示：

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>您还可以使用用户管理的枚举（通常位于&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]**&#x200B;下）来指定给定字段的值。 这些是有效的全局枚举，如果枚举在您正在使用的特定架构之外使用，则最好选择这些枚举。

## 键 {#keys}

每个表都必须至少具有一个键，并且通常使用将&#x200B;**@autouuid=true**&#x200B;属性设置为“true”，在架构的主元素中自动建立该键。

也可以使用&#x200B;**internal**&#x200B;属性定义主键。

示例:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

在此示例中，我们不是让&#x200B;**@autouuid**&#x200B;属性创建名为“id”的默认主键，而是指定我们自己的“houselId”主键。

>[!CAUTION]
>
>创建新架构或在架构扩展期间，您需要为整个架构保留相同的主键序列值(@pkSequence)。

[!DNL :bulb:] 在此部分中了解有关键的 [更多信息](database-mapping.md#management-of-keys)。

## 属性（字段）{#attributes--fields-}

利用属性，可定义构成数据对象的字段。 可以使用架构版工具栏中的&#x200B;**[!UICONTROL Insert]**&#x200B;按钮将空属性模板拖放到光标所在的XML中。 在[此部分](create-schema.md)中了解详情。

![](assets/schemaextension_2.png)

在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model)的`<attribute>`元素部分中提供了完整的属性列表。 以下是一些最常用的属性：**@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, ****@required **、**@ref **、**@xml **、**@type **。**

[!DNL :arrow_upper_right:] 有关每个属性的更多信息，请参阅 [Campaign Classicv7文档中的属性描述](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic)。

### 示例 {#examples}

定义默认值的示例：

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

将通用属性用作字段模板的示例也标记为必填：

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
>尽管大多数属性都根据1-1基数链接到数据库的物理字段，但XML字段或计算字段并非如此。\
>XML字段存储在表的Memo字段(“mData”)中。\
>但是，每次启动查询时都会动态创建计算字段，因此它仅存在于应用层中。

## 链接 {#links}

链接是架构主元素中的最后一些元素。 它们定义实例中所有不同架构如何彼此关联。

链接在包含其链接的表&#x200B;**外键**&#x200B;的架构中声明。

基数有三种类型：1-1、1-N和N-N默认使用的是1-N类型。

### 示例{#examples-1}

收件人表（即装即用模式）和自定义事务表之间的1-N链接示例：

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

自定义架构“Car”（位于“cus”命名空间中）与收件人表之间的1-1链接示例：

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

收件人表和地址表之间基于电子邮件地址而非主键的外部连接示例：

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

此处，“xpath-dst”对应于目标架构中的主键，而“xpath-src”对应于源架构中的外键。

## 审核跟踪 {#audit-trail}

您希望在架构底部包含的一个有用元素是跟踪元素（审核跟踪）。

使用以下示例可包含与创建日期、创建数据的用户、日期以及表格中所有数据的上次修改作者相关的字段：

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 更新数据库结构 {#updating-the-database-structure}

完成并保存更改后，任何可能影响SQL结构的更改都需要应用到数据库。 为此，请使用数据库更新助手。

![](assets/schemaextension_3.png)

如需详细信息，请参阅[此部分](update-database-structure.md)。

>[!NOTE]
>
>如果修改不影响数据库结构，您只需重新生成架构即可。 要执行此操作，请选择要更新的架构，右键单击并选择&#x200B;**[!UICONTROL Actions > Regenerate selected schemas...]** 。

