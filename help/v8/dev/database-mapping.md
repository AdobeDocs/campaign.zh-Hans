---
title: Campaign数据库映射
description: Campaign数据库映射
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# 数据库映射{#database-mapping}

示例架构的SQL映射提供了以下XML文档：

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## 说明 {#description}

架构的根元素不再是&#x200B;**`<srcschema>`**，而是&#x200B;**`<schema>`**。

这会将我们带到另一种类型的文档，它自动从源架构生成，简称为架构。 Adobe Campaign应用程序将使用此架构。

SQL名称是根据元素名称和类型自动确定的。

SQL命名规则如下：

* 表：架构命名空间和名称的连接

  在我们的示例中，表的名称是通过&#x200B;**sqltable**&#x200B;属性中架构的主元素输入的：

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* 字段：前面有根据类型定义的前缀的元素名称（例如，“i”表示整数，“d”表示双精度，“s”表示字符串，“ts”表示日期等）

  字段名称通过每个键入的&#x200B;**`<attribute>`**&#x200B;和&#x200B;**`<element>`**&#x200B;的&#x200B;**sqlname**&#x200B;属性输入：

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>可以从源架构重载SQL名称。 为此，请在相关元素中填充“sqltable”或“sqlname”属性。

用于创建从扩展模式生成的表的SQL脚本如下所示：

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

SQL字段约束如下：

* 数字和日期字段中没有空值
* 数值字段已初始化为0

## XML字段 {#xml-fields}

默认情况下，任何类型的&#x200B;**`<attribute>`**&#x200B;和&#x200B;**`<element>`**&#x200B;元素均映射到数据架构表的SQL字段。 但是，您可以用XML而不是SQL引用此字段，这意味着数据存储在包含所有XML字段值的表的备注字段(“mData”)中。 这些数据的存储是一个观察模式结构的XML文档。

要在XML中填充字段，您必须将值为“true”的&#x200B;**xml**&#x200B;特性添加到相关元素。

**示例**

* 多行评论字段：

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* HTML格式的数据描述：

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  通过“html”类型，您可以将HTML内容存储在CDATA标记中，并在Adobe Campaign客户端界面中显示特殊的HTML编辑检查。

通过使用XML字段，您无需修改数据库的物理结构即可添加字段。 另一个优点是，您使用的资源较少（分配给SQL字段的大小、每个表的字段数限制等）。
