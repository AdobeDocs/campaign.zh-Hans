---
product: campaign
title: 更新聚合
description: 了解有关更新聚合工作流活动的更多信息
feature: Workflows
role: Data Engineer
level: Beginner
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 3%

---

# 更新聚合{#update-aggregate}

中定义的聚合 [多维数据集](../../v8/reporting/gs-cubes.md) 可以使用特定活动进行更新以用于报告。 A **[!UICONTROL Workflow]** 选项卡。

了解有关 [此部分](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

要更新聚合，请编辑 **[!UICONTROL Update aggregate]** 活动，然后选择要更新的多维数据集和聚合。

您可以配置 **完全更新** 或 **部分更新**.

![](assets/update-aggregate-details.png)

默认情况下，在每次计算期间都会执行完整更新。 要启用部分更新，请选择选项并定义更新条件。

![](assets/update-aggregate-partial.png)

一个好做法是，在 **[!UICONTROL Scheduler]** 活动，以设置计算更新频率。
