---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 1%
---
# SchemaNode（类）

表示架构的元素

## 方法

| 方法 | 描述 |
| --- | --- |
| [findNode](m-schemanode-findnode.md) | 返回[SchemaNode](c-schemanode.md)的实例，如果节点不存在并且mustExist参数设置为false，则返回null。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [子项](p-schemanode-children.md) | 返回一个对象，其中每个属性都是一个按其名称编制索引的子节点。 |
| [computeString](p-schemanode-computestring.md) | 返回由当前节点计算的字符串。 |
| [数据策略](p-schemanode-datapolicy.md) | 返回提供当前节点的数据策略的字符串。 |
| [描述](p-schemanode-description.md) | 返回描述当前节点的字符字符串。 |
| [defaultValue](p-schemanode-defaultvalue.md) | 返回提供当前节点的默认值的字符串。 |
| [editType](p-schemanode-edittype.md) | 返回指定当前节点的编辑类型的字符串。 |
| [枚举](p-schemanode-enumeration.md) | 返回[枚举](c-enumeration.md)对象，该对象是链接到当前节点的枚举，如果没有枚举，则返回null。 |
| [枚举图像](p-schemanode-enumerationimage.md) | 以字符串形式返回当前节点的图像名称。 |
| [文件夹模型](p-schemanode-foldermodel.md) | 仅在根节点上，返回包含文件夹模板的字符串。 在其他节点上，它将返回undefined。 |
| [图像](p-schemanode-image.md) | 以字符串形式返回图像的名称。 |
| [完整性](p-schemanode-integrity.md) | 返回链接完整性类型。 |
| [键](p-schemanode-keys.md) | 返回包含当前节点的[SchemaKey](c-schemakey.md)键的定义的表。 |
| [hasEnumeration](p-schemanode-hasenumeration.md) | 返回一个布尔值，指示当前节点的值是否链接到枚举。 |
| [childrenCount](p-schemanode-childrencount.md) | 返回一个数字，用于指定子节点的数量。 |
| [hasSQLTable](p-schemanode-hassqltable.md) | 返回一个布尔值，它指示当前节点是否链接到SQL表。 |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | 返回一个布尔值，指示当前节点的值是否链接到用户枚举。 |
| [帮助](p-schemanode-help.md) | 返回帮助字符串。 |
| [架构](p-schemanode-schema.md) | 返回此节点的父[架构](c-schema.md)对象的实例。 |
| [isAdvanced](p-schemanode-isadvanced.md) | 返回一个布尔值，指示当前节点是否为高级节点。 |
| [isAnyType](p-schemanode-isanytype.md) | 返回指示当前节点是否为普通节点的布尔值。 |
| [isAttribute](p-schemanode-isattribute.md) | 返回指示当前节点是否为属性的布尔值。 |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | 返回一个布尔值，指示当前节点的值是否自动递增。 |
| [isAutoPK](p-schemanode-isautopk.md) | 返回指示当前节点是否为主键的布尔值。 |
| [isBlob](p-schemanode-isblob.md) | 返回指示当前节点是否为BLOB的布尔值。 |
| [isCalculated](p-schemanode-iscalculated.md) | 返回一个布尔值，指示当前节点的值是否为计算的结果。 |
| [isCDATA](p-schemanode-iscdata.md) | 返回一个布尔值，指示当前节点是否从CDATA类型XML进行映射。 |
| [isCollection](p-schemanode-iscollection.md) | 返回一个布尔值，指示当前节点是否为子元素和/或属性的集合。 |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | 返回布尔值。 如果添加的值为vrai，则在记录删除重复期间，默认值（在defaultValue中定义）将在记录期间自动重新应用。 |
| [isElementOnly](p-schemanode-iselementonly.md) | 返回一个布尔值，指示当前节点是否是架构的逻辑子分区。 |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | 如果节点是链接且连接是外部的，则为True。 |
| [isFeature](p-schemanode-isfeature.md) | 返回一个布尔值，指示节点是否为功能。 |
| [isLink](p-schemanode-islink.md) | 返回一个布尔值，指示节点是否为链接。 |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | 返回一个布尔值，指示节点是否为XML映射。 |
| [isMemo](p-schemanode-ismemo.md) | 返回指示当前节点是否由Memo映射的布尔值。 |
| [isMemoData](p-schemanode-ismemodata.md) | 返回一个布尔值，指示当前节点是否由MemoData映射。 |
| [isNotNull](p-schemanode-isnotnull.md) | 返回一个布尔值，指示当前节点是否可以考虑空值。 |
| [isRequired](p-schemanode-isrequired.md) | 返回指示当前节点的值是否为必填值的布尔值。 |
| [isRoot](p-schemanode-isroot.md) | 返回一个布尔值，指示节点是否是架构的根。 |
| [isSQL](p-schemanode-issql.md) | 返回一个布尔值，指示当前节点是否在SQL中映射。 |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | 返回一个布尔值，指示该表是否为临时表。 在数据库创建期间不会创建表。 |
| [isUnbound](p-schemanode-isunbound.md) | 返回一个布尔值，指示当前节点是否具有无限数量的相同类型的子节点。 |
| [isUser](p-schemanode-isuser.md) | 返回指示节点是否为用户类型的布尔值。 |
| [joinParts](p-schemanode-joinparts.md) | 返回一个SchemaNode实例的表，其中每个元素代表连接的条件。 |
| [标签](p-schemanode-label.md) | 返回当前节点的描述所对应的字符串。 |
| [名称](p-schemanode-name.md) | 返回当前节点名称的字符串。 |
| [节点路径](p-schemanode-nodepath.md) | 返回一个字符串，该字符串是当前节点的绝对路径。 |
| [父级](p-schemanode-parent.md) | 返回作为父对象的[SchemaNode](c-schemanode.md)对象，如果没有，则返回null。 |
| [PKSequence](p-schemanode-pksequence.md) | 返回一个字符串，该字符串提供用于主键的序列的名称。 |
| [packageStatus](p-schemanode-packagestatus.md) | 返回用于提供包状态的数字。 |
| [reverseLink](p-schemanode-reverselink.md) | 如果元素是链接，则返回表示反向链接的[SchemaNode](c-schemanode.md)对象（通过目标架构）。 如果未定义，则属性不会定义。 |
| [SQLName](p-schemanode-sqlname.md) | 字段的SQL名称。 如果对象不是SQL类型字段，则属性为空字符串。 |
| [SQLTable](p-schemanode-sqltable.md) | 表的SQL名称。 如果对象不是主元素或架构映射不是SQL类型，则属性为空字符串。 |
| [大小](p-schemanode-size.md) | 字符串类型的大小。 |
| [tableDefinition](p-schemanode-tabledefinition.md) | [SchemaNode](c-schemanode.md)的实例，该实例是包含当前节点的表的描述，如果没有节点，则为null。 |
| [目标](p-schemanode-target.md) | 链接目标架构的主要元素。 如果对象不是链接，则属性未定义。 |
| [类型](p-schemanode-type.md) | 返回提供当前节点的值类型的字符串。 |
| [用户枚举](p-schemanode-userenumeration.md) | 返回一个字符串，该字符串是当前节点使用的用户枚举的名称。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
