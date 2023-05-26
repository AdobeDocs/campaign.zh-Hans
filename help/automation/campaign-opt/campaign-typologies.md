---
product: campaign
title: 营销活动类型入门
description: 了解如何配置和实施活动类型
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 19%

---

# 营销活动类型入门{#about-campaign-typologies}

**活动优化** 是Adobe Campaign模块，用于控制、过滤和监控投放的发送。 为了避免活动之间发生冲突，Adobe Campaign 可以应用特定的限制规则来测试各种活动组合。这可确保所发送的邮件符合客户的需求与期望以及公司的通信政策。

![](assets/do-not-localize/how-to-video.png) [在视频中发现此功能](#typologies-video)

>[!NOTE]
>
>根据您的产品/服务，可包含Campaign Optimization或附加组件。 请核实您的许可协议。

## 分类规则和分类 {#typology-rules}

默认情况下，Campaign附带内置分类和分类规则。

分类是在投放分析期间应用于所有消息的一组验证规则。

活动类型可以包含多个类型规则，但投放只能引用一个类型。

中提供了内置分类规则和分类 **[!UICONTROL Administration > Campaign management > Typology management]** Campaign资源管理器的文件夹。

对于每种分类， **[!UICONTROL Rules]** 选项卡允许您添加、删除或查看要应用的分类规则。

![](assets/campaign_opt_rules_tab.png)

创建分类规则后，这些规则会按活动进行分组 **类型** 在投放中引用的。 [了解详情](#apply-typologies)。


Campaign附带一组默认值 **正在筛选** 和 **控制** 规则：

* **正在筛选** 规则用于根据条件排除部分目标。 [了解详情](filtering-rules.md)。
* **控制** 规则允许您在发送消息之前检查消息的有效性。 [了解详情](control-rules.md)。

Campaign Optimization加载项提供另外两种类型 **类型规则**：

* **压力** 可让您控制营销疲劳的规则。 [了解详情](pressure-rules.md)。
* **容量** 允许您限制负载以确保最佳处理条件的规则。 [了解详情](consistency-rules.md#controlling-capacity)。


>[!NOTE]
>
>如果您使用 **互动** 用于管理优惠的模块，您还可以创建 **优惠呈现** 类型规则，使用表示规则控制优惠建议的流程。 [了解详情](../../v8/interaction/interaction-offer.md#offer-presentation)。


## 创建和使用分类的关键步骤 {#apply-typologies}

要创建和使用投放的分类，请执行以下步骤：

1. 创建分类规则并创建分类以将其引用到其中。
以下部分列出了详细步骤：

   * [筛选规则](filtering-rules.md)
   * [控制规则](control-rules.md)
   * [压力规则](pressure-rules.md)
   * [容量规则](consistency-rules.md)

1. 配置投放以使用创建的分类。 [了解详情](apply-rules.md#apply-a-typology-to-a-delivery)。
1. 通过活动模拟测试和控制行为。 [了解详情](campaign-simulations.md)。

在投放准备期间，如果满足标准，则会排除收件人。 您可以检查日志以监视排除情况。

有关压力类型规则的示例用例，请参见 [此页面](pressure-rules.md#use-cases-on-pressure-rules).

## 教程视频 {#typologies-video}

### 使用类型规则设置疲劳管理

此视频介绍如何在Adobe Campaign中利用类型规则实施疲劳管理。

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### 使用预定义过滤器设置疲劳管理

疲劳管理控制消息传送的频度和数量，以避免过度招徕收件人。如果您的营销活动实例中没有营销活动优化模块，则可以配置一个预定义过滤器，该过滤器将根据收到的消息数过滤目标群体。本视频介绍如何使用过滤器在Adobe Campaign中实施疲劳管理。

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
