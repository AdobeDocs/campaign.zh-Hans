---
solution: Campaign
product: Adobe Campaign
title: 活动交互优惠目录
description: 了解如何创建优惠目录
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 1%

---

# 创建优惠目录

作为&#x200B;**优惠管理器**，您负责创建优惠目录。

优惠目录与单个预先存在的环境关联。 此目录中的优惠只能与在此同一环境中指定的空格关联。

在创建优惠之前，您必须首先指定[环境](interaction-env.md)，其中包含一组优惠的所有特征(资格、目标约束、推荐规则)，这些特征分为类别以及其空间的列表。

## 创建优惠类别{#creating-offer-categories}

优惠分为类别/子类别。 类别在&#x200B;**[!UICONTROL Design]**&#x200B;环境中创建，并在&#x200B;**[!UICONTROL Live]**&#x200B;环境(即，当其包含的优惠被批准时可用)中自动部署。 **[!UICONTROL Design]**&#x200B;环境包含接收所有优惠的默认类别。 可以创建子类别以将层次结构添加到目录优惠。

对于每个类别，您可以定义&#x200B;**资格日期**，即向其目标显示类别中包含的优惠的期间。 您还可以调整类别的权重，以排定优惠演示的优先级。

要创建新类别，请执行以下步骤：

1. 浏览到&#x200B;**[!UICONTROL Offer catalog]**&#x200B;文件夹。

   ![](assets/offer_cat_create_001.png)

1. 右键单击并从下拉列表中选择&#x200B;**[!UICONTROL Create a new "Offer category" folder]**。

   ![](assets/offer_cat_create_002.png)

1. 重新命名类别。 以后可以使用&#x200B;**[!UICONTROL General]**&#x200B;选项卡编辑标签。

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >重复这些步骤，以创建所需数量的类别。

   之后，您可以根据需要：

   * 从&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡分配资格日期。

      ![](assets/offer_cat_create_004.png)

   * 使用&#x200B;**[!UICONTROL Themes]**&#x200B;字段输入可用于从此类别中选择优惠的关键字。

      ![](assets/offer_cat_create_005.png)

      >[!NOTE]
      >
      >调用优惠引擎时，只会选择主题或类别与参数匹配的目录部分。

   * 通过&#x200B;**[!UICONTROL Multiplier weight]**&#x200B;字段暂时“提升”给定时段类别的优惠权重。

      ![](assets/offer_cat_create_006.png)

您可以在合格规则中包含的优惠的仪表板上查阅类别。 要视图它们，请单击&#x200B;**[!UICONTROL Schedule and eligibility rules of the offer]**&#x200B;链接。

## 添加回退类别

为确保所有收件人都能收到优惠建议，可以在建议中系统地添加一个或多个优惠类别。

这些回退优惠必须具有低（但非空）权重，以便仅在没有较高权重优惠符合条件时才考虑这些。

此外，不得对这些优惠适用推荐规则，以确保建议中始终包括这些数据。 这意味着，在提议期间，如果没有更高的权重优惠可用，收件人将从此类别接收至少一个优惠。

要在建议中包含回退类别，请执行以下步骤：

1. 浏览到您的优惠目录。
1. 单击&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡并选择&#x200B;**[!UICONTROL Always include this category in the recommendations]**&#x200B;选项。
1. 单击 **[!UICONTROL Save]**。

   ![](assets/offer_cat_default_001.png)

