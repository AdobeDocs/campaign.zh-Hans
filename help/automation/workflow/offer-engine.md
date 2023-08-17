---
product: campaign
title: 优惠引擎
description: 优惠引擎
feature: Workflows, Interaction
exl-id: d77858e1-3cd5-4372-b1bc-ea4b518c958d
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 4%

---

# 优惠引擎{#offer-engine}

此 **[!UICONTROL Offer engine]** 利用活动，可在投放之前定义对优惠引擎的调用。

此活动的原理与通过引擎调用的扩充活动相同，即在投放前使用引擎计算的优惠扩充集客群体数据。

![](assets/int_offerengine_activity2.png)

配置查询后(请参阅此 [部分](query.md))：

1. 添加并打开 **[!UICONTROL Offer engine]** 活动。
1. 填写各种可用字段以指定调用选件引擎参数（选件空间、类别或主题、联系日期、要保留的选件数）。 引擎将根据这些参数自动计算要添加的选件。

   >[!CAUTION]
   >
   >如果您使用此活动，则只会存储投放中使用的优惠建议。

   ![](assets/int_offerengine_activity1.png)

1. 然后，配置与您选择的渠道对应的投放活动。 请参阅 [跨渠道投放](cross-channel-deliveries.md).
