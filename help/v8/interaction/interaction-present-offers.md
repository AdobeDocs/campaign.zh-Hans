---
product: campaign
title: 提供优惠（入站互动）
description: 了解如何使用Campaign互动模块展示最佳优惠
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
TQID: https://experienceleague.adobe.com/aC-hN1JwwFkuGc6ZNV0M3uHpM7LcXTHpyC9wCbxKziQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 8%

---

# 提供最佳优惠{#interaction-present-offers}

可以使用[入站或出站渠道](interaction-architecture.md#interaction-types)在各种优惠空间中显示优惠。 本章详细介绍了入站渠道的一些特定功能。

![](assets/inbound-interactions.png)

选件引擎要选择选件，该选件必须获得批准并在实时环境中可用。

有关更多信息，请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content){target="_blank"}。

在入站联系人的上下文中，网站可以识别正在浏览页面的用户，也可以识别不存在的用户。 优惠引擎为已识别的用户档案和匿名用户档案提供不同的优惠。

在入站渠道中提供优惠之前，必须配置优惠引擎调用，以便能够在其中提供优惠。 在大多数情况下，对于入站交互，这是网页。

>[!NOTE]
>
>对于入站交互，您必须专门配置选件引擎以呈现和更新一个或多个选件。
>
>您还必须在优惠空间上启用单一模式。 有关详细信息，请参见[此页面](interaction-offer-spaces.md)。
