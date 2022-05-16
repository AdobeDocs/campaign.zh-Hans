---
title: 扩展Campaign模式
description: 了解如何扩展Campaign模式
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# 扩展模式{#extend-schemas}

作为技术用户，您可以自定义Campaign数据模型以满足您的实施需求：向现有架构添加元素、修改架构中的元素或删除元素。

自定义Campaign数据模型的关键步骤包括：

1. 创建扩展模式
1. 更新Campaign数据库
1. 调整输入表单

>[!CAUTION]
>不得直接修改内置架构。 如果您需要调整内置架构，则必须扩展该架构。

![](../assets/do-not-localize/glass.png) 要更好地了解Campaign内置表及其交互情况，请参阅 [本页](datamodel.md). 另请参阅在中创建新架构时的建议 [本页](create-schema.md).

要扩展架构，请执行以下步骤：

1. 导航到 **[!UICONTROL Administration > Configuration > Data schemas]** 文件夹。
1. 单击 **新建** 按钮，选择 **[!UICONTROL Extend the data in a table using an extension schema]**.

   ![](assets/extend-schema-option.png)

1. 确定要扩展的内置架构并将其选中。

   ![](assets/extend-schema-select.png)

   按照惯例，将扩展架构命名为与内置架构相同的架构，并使用自定义命名空间。  请注意，某些命名空间仅是内部命名空间。 [了解详情](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. 进入架构编辑器后，使用上下文菜单添加所需的元素，然后进行保存。

   ![](assets/extend-schema-edit.png)

   在以下示例中，我们将 **会员年** 属性，为姓氏设置长度限制（此限制将覆盖默认的姓氏），并从内置架构中删除出生日期。

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. 断开与Campaign的连接并重新连接，以在 **[!UICONTROL Structure]** 选项卡。

   ![](assets/extend-schema-structure.png)

1. 更新数据库结构以应用更改。 [了解详情](update-database-structure.md)

1. 在数据库中实施更改后，您可以调整收件人输入表单以使更改可见。 [了解详情](forms.md)
