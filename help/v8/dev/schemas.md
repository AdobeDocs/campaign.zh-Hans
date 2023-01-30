---
title: 使用Campaign模式
description: 模式入门
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 5%

---

# 使用模式{#gs-ac-schemas}

应用中所承载数据的物理和逻辑结构以 XML 格式进行描述。它遵循Adobe Campaign特有的语法，称为 **模式**.

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

要更好地了解Campaign内置表及其交互情况，请参阅 [此部分](datamodel.md).

>[!CAUTION]
>
>某些内置的Campaign架构在云数据库上具有关联的架构。 这些架构由 **Xxl** 命名空间和的值不得修改或扩展。

## 架构的语法 {#syntax-of-schemas}

架构的根元素为 **`<srcschema>`**. 它包含 **`<element>`** 和 **`<attribute>`** 子元素。

第一个 **`<element>`** 子元素与实体的根重合。

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

的 **`<element>`** 标记定义实体元素的名称。 **`<attribute>`** 架构的标记定义 **`<element>`** 标记。

## 模式的标识 {#identification-of-a-schema}

数据架构通过其名称及其命名空间进行标识。

命名空间允许您按关注区域对一组架构进行分组。 例如， **木槿** 命名空间用于客户特定的配置(**客户**)。

>[!CAUTION]
>
>作为标准，命名空间的名称必须简洁明了，并且必须只包含根据XML命名规则授权的字符。
>
>标识符不得以数字字符开头。

## 保留的命名空间 {#reserved-namespaces}

某些命名空间是保留的，用于描述操作Adobe Campaign应用程序所需的系统实体。 以下命名空间 **不得使用** 要标识新架构，请使用任何大写/小写组合：

* **xxl**:保留给云数据库架构
* **xtk**:平台系统数据保留
* **nl**:保留给应用程序的整体使用
* **nms**:保留给投放（收件人、投放、跟踪等）
* **ncm**:内容管理保留
* **临时**:保留给临时架构
* **crm**:保留到CRM连接器集成

架构的标识键是使用命名空间和名称以冒号分隔的字符串；例如： **nms:recipient**.

## 创建或扩展Campaign模式 {#create-or-extend-schemas}

要向Campaign中的一个核心数据模式(例如收件人表(nms:recipient))添加字段或其他元素，您必须扩展该模式。

![](../assets/do-not-localize/glass.png) 有关更多信息，请参阅 [扩展模式](extend-schema.md).

要添加Adobe Campaign中不存在的全新数据类型（例如合同表），您可以直接创建自定义架构。

![](../assets/do-not-localize/glass.png) 有关更多信息，请参阅 [创建新架构](create-schema.md).

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
>您还可以使用用户管理的枚举(通常在 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** )以指定给定字段的值。 这些是有效的全局枚举，如果枚举在您正在使用的特定架构之外使用，则最好选择这些枚举。

<!--
## Index {#index} 

In the context of a [FDA Snowflake deployment](../architecture/fda-deployment.md), you need to declare indexes. Indexes are the first elements declared in the main element of the schema. 

They can be unique or not, and reference one or more fields.

Examples:

```
<dbindex name="email" unique="true">
  <keyfield xpath="@email"/>
</dbindex>
```

```
<dbindex name="lastNameAndZip">
  <keyfield xpath="@lastName"/>
  <keyfield xpath="location/@zipCode"/>
</dbindex>
```

The **xpath** attribute points to the field in your schema that you wish to index.

>[!IMPORTANT]
>
>It is important to remember that the SQL query read performance gains provided by indexes also come with a performance hit on writing records. The indexes should therefore be used with precaution.

For more on indexes, refer to the [Indexed fields](database-mapping.md#indexed-fields) section.

-->

## 键 {#keys}

每个表都必须至少具有一个键，并且通常情况下，可使用 **奥托普** 属性设置为 **true**.

此外，在 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，则使用 **@autouuid** 将其设置为 **true**.

还可以使用 **内部** 属性。

示例:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

在本例中，不要让 **@autopk** 或 **@autouuid** 属性会创建一个名为“id”的默认主键，我们将指定自己的“houselId”主键。

>[!CAUTION]
>
>创建新架构或在架构扩展期间，您需要为整个架构保留相同的主键序列值(@pkSequence)。

![](../assets/do-not-localize/glass.png) 了解有关 [此部分](database-mapping.md#management-of-keys).

## 属性（字段） {#attributes--fields-}

利用属性，可定义构成数据对象的字段。 您可以使用 **[!UICONTROL Insert]** 按钮，将空属性模板拖放到XML中光标所在的位置。 在 [此部分](create-schema.md).

![](assets/schemaextension_2.png)

在 `<attribute>` 元素部分 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). 以下是一些最常用的属性： **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, **@notNull**, **@required**, **@ref**, **@xml**, **@type**.

![](../assets/do-not-localize/book.png) 有关每个属性的更多信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### 示例 {#examples}

定义默认值的示例：

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

将通用属性用作字段模板的示例也标记为必填：

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

使用隐藏的计算字段的示例 **@advanced** 属性：

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

XML字段的示例也存储在SQL字段中，该字段具有 **@dataPolicy** 属性。

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

链接在包含 **外键** 链接到的表格。

基数有三种类型：1-1、1-N和N-N默认使用的是1-N类型。

### 示例 {#examples-1}

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
>如果修改不影响数据库结构，您只需重新生成架构即可。 为此，请选择要更新的架构，右键单击并选择 **[!UICONTROL Actions > Regenerate selected schemas...]**.
