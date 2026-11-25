---
product: campaign
title: 更新聚合
description: 了解有关更新聚合工作流活动的更多信息
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: 'https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%
---
# 更新聚合{#update-aggregate}

可以使用特定活动更新[多维数据集](../../v8/reporting/gs-cubes.md)中为报告目的定义的聚合。 配置聚合时&#x200B;**[!UICONTROL Workflow]**&#x200B;选项卡可用。

了解有关[多维数据集聚合](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates)中的多维数据集和聚合的更多信息。

要更新聚合，请编辑&#x200B;**[!UICONTROL Update aggregate]**&#x200B;活动并选择要更新的多维数据集和聚合。

您可以配置&#x200B;**完整更新**&#x200B;或&#x200B;**部分更新**。

![使用多维数据集和聚合字段以及完全更新或部分更新选项更新聚合活动。](assets/update-aggregate-details.png)

默认情况下，在每次计算期间都会执行完全更新。 要启用部分更新，请选择选项并定义更新条件。

![使用当前日期减1个月后的创建日期上的筛选器编辑更新条件窗口。](assets/update-aggregate-partial.png)

好的做法是添加&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动以设置计算更新的频率。
