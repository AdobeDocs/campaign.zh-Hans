---
solution: Campaign v8
product: Adobe Campaign
title: Campaign互动优惠目录
description: 了解如何创建优惠目录
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: 58f294b3d17de5eca64c82fdf7720b2734320bad
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# 创建优惠目录

作为&#x200B;**选件管理器**，您负责创建选件目录。

选件目录与单个预先存在的环境相关联。 此目录中的选件只能与此同一环境中指定的空间关联。

在创建选件之前，您必须先指定一个[环境](interaction-env.md)，其中包含一组选件的所有特征（资格、目标约束、呈现规则），这些选件按类别排序，以及其空格列表。

## 创建优惠类别{#creating-offer-categories}

选件分为类别/子类别。 类别在&#x200B;**[!UICONTROL Design]**&#x200B;环境中创建，并在批准包含的选件时自动部署在&#x200B;**[!UICONTROL Live]**&#x200B;环境（即提供）中。 **[!UICONTROL Design]**&#x200B;环境包含接收所有选件的默认类别。 可以创建子类别以将层次结构添加到目录选件中。

对于每个类别，您可以定义&#x200B;**资格日期**，该日期是类别中包含的选件可向其目标显示的时间段。 您还可以调整类别的权重，以优先显示选件。

要创建新类别，请执行以下步骤：

1. **[!UICONTROL Offer catalog]**&#x200B;文件夹的浏览器。

   ![](assets/offer_cat_create_001.png)

1. 右键单击并从下拉列表中选择&#x200B;**[!UICONTROL Create a new "Offer category" folder]**。

   ![](assets/offer_cat_create_002.png)

1. 重新命名类别。 您稍后可以使用&#x200B;**[!UICONTROL General]**&#x200B;选项卡编辑标签。

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >重复这些步骤以创建所需数量的类别。

   之后，您可以根据需要：

   * 从&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡分配资格日期。

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** 将过滤器应用到选件目标。

   * 资格规则的回顾。要查看这些规则，请单击&#x200B;**[!UICONTROL Schedule and eligibility rules of the offer]**&#x200B;链接。

## 添加回退类别

为了确保所有收件人都收到优惠建议，可以在推荐中系统地添加一个或多个优惠类别。

这些备用选件的权重必须较低（但非空），因此只有在没有较高权重的选件符合条件时，才会考虑这些备用选件。

此外，不得对这些选件应用任何展示规则，以确保始终将它们包含在推荐中。 这意味着，在提出建议期间，如果没有更高权重的选件可用，则收件人将至少收到此类别中的一个选件。

要在推荐中包含回退类别，请执行以下步骤：

1. 浏览到您的优惠目录。
1. 单击&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡并选择&#x200B;**[!UICONTROL Always include this category in the recommendations]**&#x200B;选项。
1. 单击 **[!UICONTROL Save]**。

   ![](assets/offer_cat_default_001.png)

