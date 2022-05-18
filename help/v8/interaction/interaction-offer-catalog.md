---
title: Campaign互动优惠目录
description: 了解如何创建优惠目录
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# 创建优惠目录

作为 **选件管理器**，则您负责创建优惠目录。

选件目录与单个预先存在的环境相关联。 此目录中的选件只能与此同一环境中指定的空间关联。

在创建选件之前，您必须先指定 [环境](interaction-env.md) 它包含一组选件的所有特征（资格、目标约束、呈现规则），这些选件按类别排序，以及其空间列表。

## 创建优惠类别{#creating-offer-categories}

选件分为类别/子类别。 类别在 **[!UICONTROL Design]** 环境，并在中自动部署 **[!UICONTROL Live]** 环境（即提供）。 的 **[!UICONTROL Design]** 环境包含用于接收所有选件的默认类别。 可以创建子类别以将层次结构添加到目录选件中。

对于每个类别，您可以定义 **合格日期**，类别中包含的选件可在此期间显示给其目标。 您还可以调整类别的权重，以优先显示选件。

要创建新类别，请执行以下步骤：

1. 浏览到 **[!UICONTROL Offer catalog]** 文件夹。

   ![](assets/offer_cat_create_001.png)

1. 右键单击并选择 **[!UICONTROL Create a new "Offer category" folder]** 从下拉列表中。

   ![](assets/offer_cat_create_002.png)

1. 重新命名类别。 您稍后可以使用 **[!UICONTROL General]** 选项卡。

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >重复这些步骤以创建所需数量的类别。

   之后，您可以根据需要：

   * 分配 **[!UICONTROL Eligibility]** 选项卡。

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** 将过滤器应用到选件目标。

   * 资格规则的回顾。要查看这些规则，请单击 **[!UICONTROL Schedule and eligibility rules of the offer]** 链接。

## 添加回退类别

为了确保所有收件人都收到优惠建议，可以在推荐中系统地添加一个或多个优惠类别。

这些备用选件的权重必须较低（但非空），因此只有在没有较高权重的选件符合条件时，才会考虑这些备用选件。

此外，不得对这些选件应用任何展示规则，以确保始终将它们包含在推荐中。 这意味着，在提出建议期间，如果没有更高权重的选件可用，则收件人将至少收到此类别中的一个选件。

要在推荐中包含回退类别，请执行以下步骤：

1. 浏览到您的优惠目录。
1. 单击 **[!UICONTROL Eligibility]** ，然后选择 **[!UICONTROL Always include this category in the recommendations]** 选项。
1. 单击 **[!UICONTROL Save]**。

   ![](assets/offer_cat_default_001.png)
