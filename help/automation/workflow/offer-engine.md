---
product: campaign
title: 优惠引擎
description: 优惠引擎
feature: Workflows, Interaction
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 4%

---

# 优惠引擎{#offer-engine}

的 **[!UICONTROL Offer engine]** 活动允许您在投放之前定义对选件引擎的调用。

此活动与通过引擎调用扩充活动的原理相同，方法是在投放之前，使用引擎计算的选件扩充集客群体数据。

![](assets/int_offerengine_activity2.png)

配置查询后(请参阅 [部分](query.md)):

1. 添加并打开 **[!UICONTROL Offer engine]** 活动。
1. 填写各种可用字段以指定对选件引擎参数（选件空间、类别或主题、联系日期、要保留的选件数量）的调用。 引擎将根据这些参数自动计算要添加的选件。

   >[!CAUTION]
   >
   >如果您使用此活动，则只会存储投放中使用的选件建议。

   ![](assets/int_offerengine_activity1.png)

1. 然后，配置与您选择的渠道对应的投放活动。 请参阅 [跨渠道投放](cross-channel-deliveries.md).
