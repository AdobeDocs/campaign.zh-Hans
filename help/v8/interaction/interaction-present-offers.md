---
product: campaign
title: 提供优惠（入站互动）
description: 了解如何使用Campaign交互模块展示最佳选件
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# 提供最佳优惠{#interaction-present-offers}

选件可以使用 [入站或出站渠道](interaction-architecture.md#interaction-types). 本章详细介绍集客渠道的某些特定功能。

![](assets/inbound-interactions.png)

要使选件引擎选择该选件，该选件必须获得批准并在实时环境中可用。

![](../assets/do-not-localize/book.png) 有关更多信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content)

在集客联系人的上下文中，网站是否可以识别正在浏览页面的用户。 选件引擎会为已识别的用户档案和匿名用户档案提供不同的选件。

在集客渠道上显示选件之前，必须配置选件引擎调用，以便在其中显示选件。 在大多数情况下，集客交互为网页。

>[!NOTE]
>
>对于集客交互，您必须专门配置选件引擎以显示和更新一个或多个选件。
>
>您还必须在选件空间上启用统一模式。 有关详细信息，请参见[此页面](interaction-offer-spaces.md)。
