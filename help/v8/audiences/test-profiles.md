---
title: 在Campaign中创建测试配置文件
description: 了解如何在Adobe Campaign中创建和管理测试配置文件
feature: Audiences, Profiles, Seed Address, Proofs
role: User
level: Beginner
exl-id: 878b5963-100c-4dd7-97a0-c59a62c493b1
source-git-commit: 79d916c4d65c0c55ec20f2f5850fec40fe4e99a3
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 1%

---

# 创建和管理测试用户档案 {#create-test-profiles}

## 什么是种子地址？ {#gs-seeds}

测试配置文件被创建为种子地址。它们用于定位不符合所规定目标标准的收件人。 种子地址允许您通过在发送投放之前发送校样来预览和测试个性化和渲染。

种子地址具有以下优点：

* 使用从收件人用户档案中获取的数据随机替换字段：例如，您可以在种子地址部分仅输入电子邮件地址，并让Campaign自动填写用户档案的其他字段。 了解详情，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.
* 使用具有数据管理功能的工作流时，可在种子地址级别输入投放中已处理的其他数据，以强制使用该值：这可以作为随机值替代的另一做法。
* 系统会自动从以下投放统计信息的报表中排除种子地址： **[!UICONTROL Clicks]**， **[!UICONTROL Opens]**， **[!UICONTROL Unsubscriptions]**.

种子地址可通过导入或直接在投放或营销活动中创建来添加到投放目标。

>[!NOTE]
>
>种子地址不是在收件人表中创建的，而是在单独的表中创建的。 如果使用新数据扩展收件人表，则还必须使用相同数据扩展种子地址表。 否则，种子地址将不考虑这些扩展字段。
>
>有关如何扩展种子地址表的示例，请参见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.



## 创建种子地址

种子地址不是通过标准配置文件和目标进行管理，而是在Adobe Campaign Explorer的专用节点中进行管理： **[!UICONTROL Resources > Campaign management > Seed addresses]**. 您可以创建子文件夹来组织种子地址。

通过Adobe Campaign，您还可以创建种子地址模板，这些模板将导入投放或营销活动中，并根据相关投放和营销活动的具体需求进行调整。 请参阅 [创建种子地址模板](#creating-seed-address-templates).

### 定义地址 {#defining-addresses}

要创建种子地址，请执行以下步骤：

1. 单击 **[!UICONTROL New]** 按钮进行标记。
1. 在的匹配字段中输入链接到地址的数据 **[!UICONTROL Recipient]** 选项卡。 可用字段对应于投放收件人（nms：recipient表）用户档案中的标准字段：姓名、名字和电子邮件等。

   >[!NOTE]
   >
   >地址的标签会自动填入您定义的姓氏和名字。
   >
   >创建种子地址时，无需输入每个选项卡的所有字段。 在投放分析期间随机输入缺少的个性化元素。

1. 在 **[!UICONTROL Address fields]** 选项卡，输入分析阶段中要在投放日志中插入的值 **[!UICONTROL nms:broadLog]** 表格。

1. 在 **[!UICONTROL Additional data]** 选项卡，输入用于在Data Management工作流中创建的投放且要为其分配特定值的个性化数据。

   请确保已定义其他目标数据，并在中以“@”开头的别名 **[!UICONTROL Enrichment]** 工作流活动。 否则，您将无法在投放活动中将它们与种子地址正确一起使用。

### 创建种子地址模板 {#creating-seed-address-templates}

您可以创建地址模板，这些模板可导入并为每次投放进行修改。 此过程与定义新种子地址时的过程相同。 唯一的区别是种子地址模板地址必须存储在“模板”类型文件夹中。

### 直邮投放的种子地址 {#direct-mail-seed-addresses}

对象 [直邮投放](../send/direct-mail.md)，种子地址会在提取期间添加，并在输出文档中混合。

对于直邮投放，提取文件格式必须符合以下限制：

* 它不得使用选项 **[!UICONTROL Handle groupings (GROUP BY+HAVING)]**.

* 如果提取了元素集合，则这些字段的种子地址将具有空值，除非 **[!UICONTROL Single row (expert user)]** 已选中选项。

## 在投放中添加种子地址{#seed-addresses-in-a-delivery}

要为投放添加特定的种子地址，请单击 **[!UICONTROL To]** 链接，然后选择 **[!UICONTROL Seed addresses]** 选项卡。

有三种可能的插入模式：

1. 输入单个种子地址。  要执行此操作，请单击 **[!UICONTROL Add]** 按钮并定义地址字段的内容。 对每个地址重复此操作。

1. 导入 [种子地址模板](#creating-seed-address-template) 并根据您的需求对其进行调整。 要执行此操作，请单击 **[!UICONTROL Import seed templates...]** 链接并选择包含地址模板的文件夹。

   如有必要，在添加这些组件后，您可以双击它们或单击 **[!UICONTROL Detail...]** 按钮以调整每个地址的内容。

1. 创建一个条件以动态选择要插入的控制地址。 要执行此操作，请单击 **[!UICONTROL Edit the dynamic condition...]** 链接，然后输入种子地址选择参数。 例如，您可以包括特定文件夹中包含的所有种子地址，或属于贵组织特定部门的种子地址。

   有关这方面的示例，请参见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

对于投放，您还可以自定义将地址插入到提取文件中的方式。 默认情况下，会按输出文件的排序顺序插入陷阱，但您可以选择在文件末尾或开头插入陷阱，或者在主目标的收件人中随机插入。

## 在营销活动中添加种子地址 {#seed-addresses-in-a-campaign}

要将种子地址添加到营销活动的目标，请选择操作，然后单击 **[!UICONTROL Edit]** 选项卡。

单击 **[!UICONTROL Advanced campaign settings...]** 链接，然后 **[!UICONTROL Seed addresses]** 选项卡。 从营销活动中插入的种子地址将添加到营销活动中每个投放的目标。

## 种子地址和自定义表 {#using-an-external-recipient-table}

如果投放表是外部表，则需要执行其他配置。 此 **[!UICONTROL nms:seedmember]** 必须扩展架构。 向种子地址添加选项卡以定义适当的字段

在这种情况下，要将种子地址添加到投放，请直接在匹配选项卡中输入适当的字段，或导入地址模板。

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->
