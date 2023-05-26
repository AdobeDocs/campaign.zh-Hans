---
product: campaign
title: 营销活动资产、文档和投放概要
description: 了解有关营销活动文档和投放概要的更多信息
feature: Campaigns
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# 管理资源和文档 {#manage-assets-documents}

您可以将各种文档与营销活动关联：报表、照片、网页、图表等。 这些文档可以是任何格式。

在营销策划中，您还可以参考其他项目，例如促销优惠券、与特定品牌或商店相关的特殊优惠等。 当这些元素包含在大纲中时，它们可以与直邮投放相关联。 [了解详情](#associating-and-structuring-resources-linked-via-a-delivery-outline)。


>[!CAUTION]
>
>此功能专为小型资产和文档而设计。

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## 添加文档 {#add-documents}

文档可以在营销活动级别（上下文文档）或项目群级别（常规文档）关联。

对于营销策划， **[!UICONTROL Documents]** 选项卡包含：

* 内容所需的所有文档（模板、图像等）的列表 Adobe Campaign操作员通过适当权限可本地下载的广告文件、
* 包含路由器信息的文档（如果有）。

这些文档通过以下方式链接到项目或营销策划 **[!UICONTROL Edit > Documents]** 选项卡。

![](assets/op_add_document.png)

您还可以从功能板中的专用链接将文档添加到营销活动。

![](assets/add_a_document_in_op.png)

单击 **[!UICONTROL Detail...]** 图标以查看文件内容和添加信息：

![](assets/add_document_details.png)

在功能板中，与活动关联的文档将分组到 **[!UICONTROL Document(s)]** 部分，如以下示例所示：

![](assets/edit_documents.png)

也可以从此视图编辑和修改它们。

## 使用投放概要 {#delivery-outlines}

投放概要是结构化的一组元素（文档、商店、促销优惠券等） 由公司和为特定营销活动创建。 它在直邮投放的上下文中使用。

这些元素在投放概要中进行分组，每个投放概要都将与一个投放关联；将在发送到的提取文件中引用该投放概要。 **服务提供商** 以便附加到投放中。 例如，您可以创建一个投放概要，其中引用单位及其使用的营销手册。

对于营销活动，投放大纲允许您根据特定条件构建要与投放关联的外部元素：相关单位、已授予的促销优惠、本地活动邀请函等。

>[!CAUTION]
>
>投放大纲仅限于直邮营销活动。

### 创建投放概要 {#create-an-outline}

要创建投放概要，请单击 **[!UICONTROL Delivery outlines]** 中的子选项卡 **[!UICONTROL Edit > Documents]** 相关营销活动的选项卡。

![](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>如果您看不到此选项卡，则此功能对此营销活动不可用，或者在您的实例中未启用直邮投放。 请参阅 [营销活动模板配置](marketing-campaign-templates.md#campaign-templates) 或您的许可协议。

接下来，单击 **[!UICONTROL Add a delivery outline]** 并为营销活动创建大纲的层次结构：

1. 右键单击树的根并选择 **[!UICONTROL New > Delivery outlines]**.
1. 右键单击刚刚创建的大纲，然后选择 **[!UICONTROL New > Item]** 或 **[!UICONTROL New > Personalization fields]**.

![](assets/del-outline-add-new-item.png)

大纲可以包含项目、个性化字段和选件：

* 项目可以是物理文档，例如，此处引用和描述的文档，并将附加到投放。
* 通过个性化字段，您可以创建与投放而非收件人相关的个性化元素。 因此，可以创建值以用于特定目标的投放（欢迎优惠、折扣等） 它们在Adobe Campaign中创建，并通过导入到大纲中 **[!UICONTROL Import personalization fields...]** 链接。

   ![](assets/del-outline-perso-field.png)

   也可以通过单击 **[!UICONTROL Add]** 图标（位于列表区域的右侧）。

   ![](assets/add-del-outline-button.png)


### 选择大纲 {#select-an-outline}

对于每个投放，您可以从为提取大纲保留的部分中选择要关联的大纲，如下例所示：

![](assets/select-delivery-outline.png)

然后，所选轮廓将显示在窗口的下部。 可使用字段右侧的图标编辑或使用下拉列表进行更改：

![](assets/delivery-outline-selected.png)

此 **[!UICONTROL Summary]** 投放的选项卡也会显示以下信息：

![](assets/delivery-outline-in-dashboard.png)

### 提取结果 {#extraction-result}

在提取并发送到服务提供商的文件中，大纲的名称以及适当时其特征（成本、描述等） 根据与服务提供商关联的导出模板中的信息添加到内容中。

在以下示例中，与投放关联的大纲的标签、预计成本和描述将添加到提取文件中。

![](assets/campaign-export-template.png)

导出模型必须与为相关投放选择的服务提供商关联。 请参阅[此小节](providers--stocks-and-budgets.md#creating-service-providers-and-their-cost-structures)。
