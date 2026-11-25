---
product: campaign
title: 呈现规则
description: 呈现规则
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: f9dd9ad6-48da-4a80-9405-109a433a1ed5
TQID: 'https://experienceleague.adobe.com/s2QV1BGLtUfyWg1BfYuryciF9STRK3HpIXNc6oQ0ATY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---
# 呈现规则{#presentation-rules}



## 创建推荐规则 {#creating-a-presentation-rule}

在我们的数据库中，有数种针对欧洲、非洲、美国和加拿大的旅行优惠。 我们希望发送赴加拿大旅行的聘用，但如果收件人拒绝此类聘用，我们便不希望再次向其发送聘用。

我们将配置规则，以便每个收件人仅提供一次加拿大之行，如果被拒绝，则不再提供加拿大之行。

1. 在Adobe Campaign树中，转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Typology management]** > **[!UICONTROL Typology rules]**&#x200B;节点。
1. 创建新的&#x200B;**[!UICONTROL Offer presentation]**&#x200B;类型规则。

   ![规则类型列表已打开且已选择优惠呈现的类型规则创建表单](assets/offer_typology_example_001.png)

1. 根据需要更改其标签及其描述。

   ![类型规则“常规”选项卡，带有标签、优惠呈现类型、电子邮件渠道和输入的描述](assets/offer_typology_example_002.png)

1. 选择&#x200B;**[!UICONTROL All channels]**&#x200B;选项以将规则扩展到所有渠道。

   ![已选择所有渠道的分类规则的渠道列表](assets/offer_typology_example_003.png)

1. 单击&#x200B;**[!UICONTROL Edit expression]**&#x200B;链接并选择&#x200B;**[!UICONTROL Category]**&#x200B;节点作为表达式。

   ![使用Select查询窗口，并打开表达式对话框以选择“类别”字段](assets/offer_typology_example_004.png)

1. 选择与您的加拿大旅行优惠匹配的类别，然后单击&#x200B;**[!UICONTROL OK]**&#x200B;以关闭查询窗口。

   ![在等于加拿大的类别上查询，并在旅行优惠类别树中选择“加拿大”文件夹](assets/offer_typology_example_005.png)

1. 在&#x200B;**[!UICONTROL Offer presentation]**&#x200B;选项卡中，选择与环境中配置的维度相同的维度。

   ![显示与环境匹配的“定位”维度和存储维度的“选件”演示选项卡](assets/offer_typology_example_006.png)

1. 指定应用规则的时段。

   ![包含滑动周期的优惠呈现选项卡，周期考虑字段设置为10d](assets/offer_typology_example_007.png)

1. 将建议限制为一个，以便已拒绝加拿大旅行的收件人不会收到另一个类似的建议。

   ![建议最大数量数量字段设置为1](assets/offer_typology_example_008.png)的优惠呈现选项卡

1. 选择&#x200B;**[!UICONTROL Offers for the same category]**&#x200B;筛选器以排除&#x200B;**加拿大**&#x200B;类别中的所有选件。

   建议中的![选件下拉列表与所选同一类别的选件一起计数](assets/offer_typology_example_020.png)

1. 选择&#x200B;**[!UICONTROL Rejected propositions]**&#x200B;筛选器以仅考虑收件人拒绝的建议。

   在要计算且已选择被拒绝的建议的建议中的![建议状态下拉列表](assets/offer_typology_example_021.png)

1. 选择要应用此规则的收件人。

   在本例中，我们将选择&#x200B;**频繁出差者**&#x200B;收件人。

   ![编辑筛选查询向导选择Frequent travelers收件人文件夹作为规则目标](assets/offer_typology_example_009.png)

1. 在优惠类型中引用规则。

   使用“添加类型”对话框列出所选优惠类型的![规则的“类型”选项卡](assets/offer_typology_example_013.png)

1. 转到优惠环境（**环境 — 此示例中为Recipient**）并引用刚刚使用&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡中的下拉列表创建的新分类。

   使用优惠呈现类型列表显示优惠的优惠环境的![资格选项卡](assets/offer_typology_example_014.png)

## 应用呈现规则 {#applying-the-presentation-rule}

以下是之前创建的分类规则的应用程序示例。

我们希望发送属于加拿大类别的第一个优惠建议。 如果任何收件人拒绝了选件一次，则不会再次向其提供该选件。

1. 在&#x200B;**常客**&#x200B;收件人文件夹中，选择一个用户档案以检查其符合条件的优惠：单击&#x200B;**[!UICONTROL Propositions]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡。

   在我们的示例中，**Tim Ramsey**&#x200B;有资格获得属于&#x200B;**美洲**&#x200B;类别的优惠。

   ![收件人建议选项卡，预览子选项卡，列出适用于美洲类别的优惠](assets/offer_typology_example_015.png)

1. 首先，创建电子邮件投放，将选件定位到&#x200B;**频繁出差者**&#x200B;的收件人。
1. 选择优惠引擎调用参数。

   在我们的示例中，选择了&#x200B;**Travel in America**&#x200B;类别，该类别包含&#x200B;**Canada**&#x200B;和&#x200B;**United States**&#x200B;子类别。

   ![具有美洲类别的电子邮件投放的选件管理对话框，每封邮件2个建议](assets/offer_typology_example_016.png)

1. 在消息正文中插入优惠并发送投放。 有关更多信息，请参阅[关于出站渠道](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/offers/interaction-send-offers){target="_blank"}（Campaign v8文档）。

   收件人已收到他们符合条件的优惠。

1. 收件人拒绝了加拿大的报价，如建议历史记录中所示。

   ![加拿大雪地车优惠的收件人建议历史记录处于已拒绝状态](assets/offer_typology_example_018.png)

1. 检查他们现在有资格享受的优惠。

   我们可以看到，没有选择加拿大的优惠。

   ![收件人预览选项卡显示纽约和大峡谷的合格优惠，无加拿大优惠](assets/offer_typology_example_019.png)
