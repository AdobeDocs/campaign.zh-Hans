---
title: 通过Campaign交互发送优惠
description: 了解如何发送优惠
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: d39b1768-4c39-4d64-b9b6-d9c9424a2b0d
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '1265'
ht-degree: 3%

---

# 发送优惠{#send}

为了让优惠引擎选择优惠，该优惠已获得批准，并且可在 **实时** 环境。 [了解详情](interaction-offer.md#approve-offers)

通过出站通信渠道进行的优惠呈现通过直邮、电子邮件或移动投放进行。 您还可以将统一模式与事务性消息传递（消息中心）结合使用。

## 在投放中插入优惠 {#offer-into-a-delivery}

要在投放中插入优惠建议，请执行以下步骤：

1. 在投放窗口中，单击 **选件** 图标。

   ![](assets/offer_delivery_001.png)

1. 选择与优惠环境匹配的空间。

   ![](assets/offer_delivery_002.png)

1. 要优化引擎的选件选择，请选择要显示的选件所属类别或一个/多个主题。 我们建议一次只使用这些字段之一，以避免超出限制。

   ![](assets/offer_delivery_003.png)

   ![](assets/offer_delivery_004.png)

1. 指定要插入到投放主体中的选件数。

   ![](assets/offer_delivery_005.png)

1. 选择 **[!UICONTROL Exclude non-eligible recipients]** 选项（如有必要）。 [了解详情](#parameters-for-calling-offer-engine)

   ![](assets/offer_delivery_006.png)

1. 如果需要，请选择 **[!UICONTROL Do not display anything if no offers are selected]** 选项。 [了解详情](#parameters-for-calling-offer-engine)

   ![](assets/offer_delivery_007.png)

1. 使用合并字段将属性插入投放内容。 可用建议的数目取决于引擎调用的配置方式，其顺序取决于优惠的优先级。

   ![](assets/offer_delivery_008.png)

1. 完成内容，测试并发送投放。

   ![](assets/offer_delivery_010.png)


### 优惠引擎的参数 {#parameters-for-calling-offer-engine}

* **[!UICONTROL Space]** ：必须选择用于激活优惠引擎的优惠环境的空间。
* **[!UICONTROL Category]** ：用于对选件进行排序的特定文件夹。 如果未指定类别，则除非选择了主题，否则选件引擎将会考虑环境中包含的所有选件。
* **[!UICONTROL Themes]** ：在类别中上游定义的关键字。 这些功能用作过滤器，允许您通过在一组类别中选择选件来优化要呈现的选件数量。
* **[!UICONTROL Number of propositions]** ：引擎返回的可插入到投放主体中的选件数。 如果未将选件插入到消息中，则仍会生成选件，但不会显示选件。
* **[!UICONTROL Exclude non-eligible recipients]** ：利用此选项可激活或取消激活对没有足够的合格优惠的收件人的排除。 合格建议的数目可能低于请求的建议数目。 如果选中此框，则将从投放中排除没有足够建议的收件人。 如果不选择此选项，则不会排除这些收件人，但他们不会具有所请求的建议数量。
* **[!UICONTROL Do not display anything if no offer is selected]** ：利用此选项可选择在某个建议不存在时如何处理消息。 选中此框后，将不显示缺少的建议的表示形式，并且此建议的消息中不会出现任何内容。 如果未选中该框，则在发送期间将取消邮件本身，收件人将不再收到任何邮件。

## 在工作流中发送优惠{#offer-via-wf}

利用几个工作流活动，可定义优惠的显示方式：

* 扩充
* 优惠引擎
* 单元格优惠

### 扩充 {#enrichment}

此 **扩充** 利用活动，可将优惠或链接添加到投放收件人的优惠中。[了解详情](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html)

例如，您可以在投放之前扩充收件人查询的数据。

![](assets/int_enrichment_offer1.png)

指定优惠建议的方法有两种。

* 指定选件或选件引擎调用。
* 引用优惠的链接。

#### 指定优惠或调用优惠引擎 {#specifying-an-offer-or-a-call-to-the-offer-engine}

配置后 **查询** 活动：

1. 添加并打开 **扩充** 活动。
1. 在 **[!UICONTROL Enrichment]** 选项卡中，选择 **[!UICONTROL Add data]**。
1. 选择 **[!UICONTROL An offer proposition]** 在要添加的数据类型中。

   ![](assets/int_enrichment_offer2.png)

1. 指定要添加的建议标识符和标签。
1. 指定选件选择。 对此有两种可能的选项：

   * **[!UICONTROL Search for the best offer in a category]** ：选中此选项并指定选件引擎调用参数（选件空间、类别或主题、联系日期、要保留的选件数）。 引擎将根据这些参数自动计算要添加的选件。 我们建议您完成 **[!UICONTROL Category]** 或 **[!UICONTROL Theme]** 字段，而不是同时执行两者。

     ![](assets/int_enrichment_offer3.png)

   * **[!UICONTROL A pre-defined offer]** ：选中此选项并指定选件空间、特定选件和联系日期，以直接配置要添加的选件，而无需调用选件引擎。

     ![](assets/int_enrichment_offer4.png)

1. 然后，配置与您选择的渠道对应的投放活动。 [了解详情](#offer-into-a-delivery)

   >[!NOTE]
   >
   >可用于预览的建议数量取决于在扩充活动中执行的配置，而不是直接在投放中执行的任何可能的配置。

#### 引用到优惠的链接 {#referencing-a-link-to-an-offer}

您还可以引用中选件的链接 **扩充** 活动。

为此请执行以下操作步骤：

1. 选择 **[!UICONTROL Add data]** 在活动的 **[!UICONTROL Enrichment]** 选项卡。
1. 在选择要添加的数据类型的窗口中，选择 **[!UICONTROL A link]**.
1. 选择要建立的链接类型及其目标。 在本例中，目标是选件架构。

   ![](assets/int_enrichment_link1.png)

1. 指定扩充活动（此处为收件人表）中的集客表数据与选件表之间的联接。 例如，您可以将优惠代码链接到收件人。

   ![](assets/int_enrichment_link2.png)

1. 然后，配置与您选择的渠道对应的投放活动。 [了解详情](#offer-into-a-delivery)

   >[!NOTE]
   >
   >可用于预览的建议数量取决于投放中执行的配置。

#### 存储优惠排名和权重 {#storing-offer-rankings-and-weights}

默认情况下，当 **扩充** 活动用于提供优惠，其排名和权重不会存储在建议表中。

>[!NOTE]
>
>此 **[!UICONTROL Offer engine]** 默认情况下，活动会存储此信息。

但是，您可以按如下方式存储此信息：

1. 在查询之后和投放活动之前放置的扩充活动中创建对优惠引擎的调用。 [了解详情](#specifying-an-offer-or-a-call-to-the-offer-engine)
1. 在活动的主窗口中，选择 **[!UICONTROL Edit additional data...]**.

   ![](assets/ita_enrichment_rankweight_1.png)

1. 添加 **[!UICONTROL @rank]** 排名和列 **[!UICONTROL @weight]** 选件权重。

   ![](assets/ita_enrichment_rankweight_2.png)

1. 确认添加并保存工作流。

投放会自动存储优惠的排名和权重。 此信息在投放的 **[!UICONTROL Offers]** 选项卡。

### 优惠引擎 {#offer-engine}

此 **[!UICONTROL Offer engine]** 利用活动，您还可在投放之前指定对选件引擎的调用。

欲知详情，请参阅 **优惠引擎** 活动，请参阅 [此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/offer-engine.html)

本练习的原理与 **扩充** 使用引擎调用进行的活动，方法是在投放之前使用引擎计算的优惠扩充集客群体数据。

![](assets/int_offerengine_activity2.png)

配置后 **查询** 活动：

1. 添加并打开 **[!UICONTROL Offer engine]** 活动。
1. 填写各种可用字段以指定对优惠引擎参数的调用（优惠空间、类别或主题、联系日期、要保留的优惠数量）。 引擎将根据这些参数自动计算要添加的选件。

   >[!CAUTION]
   >
   >如果您使用此活动，则只会存储投放中使用的优惠建议。

   ![](assets/int_offerengine_activity1.png)

1. 然后，配置与您选择的渠道对应的投放活动。 [了解详情](#inserting-an-offer-proposition-into-a-delivery)

### 单元格优惠 {#offers-by-cell}

此 **[!UICONTROL Offers by cell]** 利用活动，可将集客群体（例如从查询）分配到多个区段，并指定要为每个区段呈现的选件。

欲知详情，请参阅 **单元格优惠** 活动，请参阅 [此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/offers-by-cell.html)

为此，请使用以下流程：

1. 添加 **[!UICONTROL Offers by cell]** 指定目标群体后，请打开该群体。
1. 在 **[!UICONTROL General]** 选项卡上，选择要显示选件的选件空间。
1. 在 **[!UICONTROL Cells]** 选项卡，使用 **[!UICONTROL Add]** 按钮：

   * 使用可用的筛选和限制规则指定子集群体。
   * 然后，选择要提供给子集的选件。 可用的优惠是在上一步骤中选择的优惠环境中符合条件的优惠。

     ![](assets/int_offer_per_cell1.png)

1. 然后，配置与您选择的渠道对应的投放活动。

<!--

## Delivering with delivery outlines {#delivering-with-delivery-outlines}

You can also present offers in a delivery using delivery outlines.

For more information on delivery outlines, refer to the Campaign - MRM guide.

1. Create a new campaign or access an existing campaign.
1. Access the delivery outlines via the campaign's **[!UICONTROL Edit]** > **[!UICONTROL Documents]** tab.
1. Add an outline then insert as many offers as you like into it by right-clicking on the outline and selecting **[!UICONTROL New]** > **[!UICONTROL Offer]**, then save the campaign.


1. Create a delivery whose delivery outlines you have access to (for example, a direct mail delivery).
1. When editing the delivery, click **[!UICONTROL Select a delivery outline]**.

   >[!NOTE]
   >
   >Depending on the type of delivery, this option can be found in the **[!UICONTROL Properties]** > **[!UICONTROL Advanced]** menu (for email deliveries for example).


1. Using the **[!UICONTROL Offers]** button, you can then configure the offer space as well as the number of offers to present in the delivery.


1. Add the propositions into the delivery body using the personalization fields (for more on this, refer to the [Inserting an offer proposition into a delivery](#inserting-an-offer-proposition-into-a-delivery) section), or in the case of a direct mail delivery, by editing the extraction file format.

   Propositions will be selected from the offers referenced in the delivery outline.

   >[!NOTE]
   >
   >Information regarding the offer rankings and weights is only saved in the proposition table if the offers are generated directly in the delivery.
-->
