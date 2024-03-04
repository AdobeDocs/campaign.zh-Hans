---
title: Campaign数据库中的密钥管理
description: 了解Adobe Campaign架构中的密钥管理
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---


# 密钥管理 {#management-of-keys}

与数据模式相关联的每个表必须具有至少一个用于标识表中记录的键。

从数据架构的主元素中声明了一个键。

```sql
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

当键是架构中第一个要填充的键时，或者如果键包含 `internal` 属性设置为“true”。

键可以引用表中的一个或多个字段。

**示例**：

* 向电子邮件地址和城市添加密钥：

  ```sql
  <srcSchema name="recipient" namespace="cus">
    <element name="recipient">
      <key name="email">
        <keyfield xpath="@email"/> 
        <keyfield xpath="location/@city"/> 
      </key>
  
      <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
      <element name="location" label="Location">
        <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
      </element>
    </element>
  </srcSchema>
  ```

  生成的架构：

  ```sql
  <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
    <element name="recipient" sqltable="CusRecipient">    
     <key name="email">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="location/@city"/>    
     </key>    
  
     <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
     <element label="Location" name="location">      
       <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
     </element>  
    </element>
  </schema>
  ```

* 在“id”名称字段中添加主键或内部键：

  ```sql
  <srcSchema name="recipient" namespace="cus">
    <element name="recipient">
      <key name="id" internal="true">
        <keyfield xpath="@id"/> 
      </key>
  
      <key name="email">
        <keyfield xpath="@email"/> 
      </key>
  
      <attribute name="id" type="long" label="Identifier"/>
      <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
    </element>
  </srcSchema>
  ```

  生成的架构：

  ```sql
  <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
    <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
        <keyfield xpath="@email"/>    
      </key>  
  
      <key internal="true" name="id">      
       <keyfield xpath="@id"/>    
      </key>    
  
      <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
    </element>
  </schema>
  ```

## 主键 — 标识符{#primary-key}

在上下文中 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，Adobe Campaign表的主键是 **通用唯一ID (UUID)** 由数据库引擎自动生成。 键值在整个数据库中是唯一的。 密钥的内容在插入记录时自动生成。

**示例**

在以下示例中，我们在源架构中声明了一个增量密钥：

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

生成的架构：

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

除了键的定义之外，还向扩展架构中添加了名为“id”的数字字段，以包含自动生成的主键。

>[!CAUTION]
>
>创建表时，主键设置为0的记录会自动插入。 此记录用于避免外部联接，这对于卷表无效。 默认情况下，所有外键都使用值0进行初始化，这样，当数据项未填充时，就始终可以在连接上返回结果。

