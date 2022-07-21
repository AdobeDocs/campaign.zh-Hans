---
product: campaign
title: 活动分类快速入门
description: 了解如何配置和实施Campaign分类
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 22%

---

# 活动分类快速入门{#about-campaign-typologies}

Campaign Optimization是Adobe Campaign模块，可让您控制、过滤和监控投放的发送。 为了避免活动之间发生冲突，Adobe Campaign 可以应用特定的限制规则来测试各种活动组合。这可确保所发送的邮件符合客户的需求与期望以及公司的通信政策。

![](assets/do-not-localize/how-to-video.png) [在视频中发现此功能](#typologies-video)

>[!NOTE]
>
>根据您的产品，可以包含促销活动优化或加载项。 请核实您的许可协议。

## 分类规则和分类 {#typology-rules}

借助Adobe Campaign，您可以设计并应用四种类型的 **类型规则**:

* **筛选** 规则来排除部分目标。 [了解详情](filtering-rules.md)。
* **压力** 用于控制营销疲劳度的规则。 [了解详情](pressure-rules.md)。
* **容量** 用于限制加载以保证最佳处理条件的规则。 [了解详情](consistency-rules.md#controlling-capacity)。
* **控制** 规则，用于在发送消息之前检查消息的有效性。 [了解详情](control-rules.md)。

创建分类规则后，便会将其分组到营销活动中 **分类** 在投放中引用。 [了解详情](#apply-typologies)。

营销活动分类可以包含多个分类规则，但投放只能引用一个分类。

在 **[!UICONTROL Administration > Campaign management > Typology management]** Campaign Explorer节点。

对于每个分类， **[!UICONTROL Rules]** 选项卡，可添加、删除或查看要应用的分类规则。

![](assets/campaign_opt_rules_tab.png)

## 应用分类的关键步骤 {#apply-typologies}

下面列出了创建分类并将其应用于投放的关键步骤：

1. 创建分类规则并创建分类以将其引用到其中。
以下部分列出了详细步骤：
   * [压力规则](pressure-rules.md)
   * [筛选规则](filtering-rules.md)
   * [容量规则](consistency-rules.md)
   * [控制规则](control-rules.md)

1. 配置投放以使用您创建的分类。 [了解详情](apply-rules.md#apply-a-typology-to-a-delivery)。
1. 通过促销活动模拟测试和控制行为。 [了解详情](campaign-simulations.md)。

在投放准备期间，如果满足标准，则会排除收件人。 您可以检查日志以监视排除情况。

有关压力分类规则的示例用例，请参阅 [本页](pressure-rules.md#use-cases-on-pressure-rules).

## 教程视频 {#typologies-video}

### 使用类型规则设置疲劳管理

此视频介绍如何利用分类规则在Adobe Campaign中实施疲劳管理。

>[!VIDEO](https://video.tv.adobe.com/v/25090?quality=12)

### 使用预定义过滤器设置疲劳管理

疲劳管理控制消息传送的频度和数量，以避免过度招徕收件人。如果您的促销活动实例中没有促销活动优化模块，则可以配置一个预定义的过滤器，该过滤器将按收到的消息数过滤目标群体。此视频介绍如何使用过滤器在Adobe Campaign中实施疲劳管理。

>[!VIDEO](https://video.tv.adobe.com/v/25091?quality=12)
