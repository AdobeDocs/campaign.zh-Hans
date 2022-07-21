---
product: campaign
title: 营销活动资产、文档和投放概述
description: 进一步了解营销活动文档和投放概述
feature: Campaigns
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# 管理资产和文档 {#manage-assets-documents}

您可以将各种文档与营销活动关联：报表、照片、网页、图表等。 这些文档可以采用任何格式。

在营销活动中，您还可以参考其他项目，例如促销优惠券、与特定品牌或商店相关的特惠等。 当这些元素包含在大纲中时，它们可以与直邮投放相关联。 [了解详情](#associating-and-structuring-resources-linked-via-a-delivery-outline)。


>[!CAUTION]
>
>此功能专为小资产和文档而设计。

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## 添加文档 {#add-documents}

文档可以在营销策划级别（上下文文档）或项目级别（常规文档）进行关联。

对于营销活动， **[!UICONTROL Documents]** 选项卡包含：

* 内容所需的所有文档的列表（模板、图像等） 可由Adobe Campaign运营商在本地下载，
* 包含路由器信息的文档（如果有）。

文档通过 **[!UICONTROL Edit > Documents]** 选项卡。

![](assets/op_add_document.png)

您还可以从仪表板的专用链接向营销策划添加文档。

![](assets/add_a_document_in_op.png)

单击 **[!UICONTROL Detail...]** 图标以查看文件内容并添加信息：

![](assets/add_document_details.png)

在功能板中，与营销活动关联的文档分组在 **[!UICONTROL Document(s)]** 部分，如以下示例中所示：

![](assets/edit_documents.png)

也可以从此视图编辑和修改它们。

## 使用投放大纲 {#delivery-outlines}

投放大纲是由元素（文档、商店、促销优惠券等）组成的结构化集合 由公司创建，用于特定营销活动。 它用于直邮投放的上下文。

这些元素按投放大纲进行分组，每个投放大纲都将与投放相关联；它将在发送到的提取文件中引用 **服务提供商** 以便附在投放上。 例如，您可以创建一个投放大纲，以引用一个单位及其使用的营销手册。

对于营销活动，投放大纲允许您根据特定条件构建要与投放关联的外部元素：相关单位、已授予的促销优惠、参加当地活动的邀请等。

>[!CAUTION]
>
>投放大纲仅限于直邮营销活动。

### 创建投放大纲 {#create-an-outline}

要创建投放大纲，请单击 **[!UICONTROL Delivery outlines]** 子选项卡 **[!UICONTROL Edit > Documents]** 选项卡。

![](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>如果看不到此选项卡，则此功能对于此营销活动不可用，或者实例中未启用直邮投放。 请参阅 [活动模板配置](marketing-campaign-templates.md#campaign-templates) 或您的许可协议。

接下来，单击 **[!UICONTROL Add a delivery outline]** 和为营销活动创建大纲层次结构：

1. 右键单击树的根并选择 **[!UICONTROL New > Delivery outlines]**.
1. 右键单击刚刚创建的大纲并选择 **[!UICONTROL New > Item]** 或 **[!UICONTROL New > Personalization fields]**.

![](assets/del-outline-add-new-item.png)

大纲可以包含项目、个性化字段和选件：

* 项目可以是实物文档，例如，此处引用和描述的物体文档，将附加到投放。
* 个性化字段允许您创建与投放相关的个性化元素，而不是收件人。 因此，可以创建用于特定目标（欢迎选件、折扣等）投放的值 这些配置文件将在Adobe Campaign中创建，并通过 **[!UICONTROL Import personalization fields...]** 链接。

   ![](assets/del-outline-perso-field.png)

   也可以通过单击 **[!UICONTROL Add]** 图标。

   ![](assets/add-del-outline-button.png)


### 选择大纲 {#select-an-outline}

对于每个投放，您可以从为提取大纲保留的部分中选择要关联的大纲，如以下示例中所示：

![](assets/select-delivery-outline.png)

选定的轮廓随后显示在窗口的下部。 可以使用字段右侧的图标进行编辑，也可以使用下拉列表进行更改：

![](assets/delivery-outline-selected.png)

的 **[!UICONTROL Summary]** 的选项卡中，还会显示以下信息：

![](assets/delivery-outline-in-dashboard.png)

### 提取结果 {#extraction-result}

在提取并发送给服务提供商的文件中，大纲的名称，并在适当情况下，其特征（成本、描述等） 根据与服务提供商关联的导出模板中的信息，被添加到内容中。

在以下示例中，将与投放关联的大纲的标签、估计成本和描述将添加到提取文件中。

![](assets/campaign-export-template.png)

导出模型必须与为相关投放选择的服务提供商关联。 请参阅[此小节](providers--stocks-and-budgets.md#creating-service-providers-and-their-cost-structures)。
