---
product: campaign
title: 更新聚合
description: 了解有关更新聚合工作流活动的更多信息
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%

---

# 更新聚合{#update-aggregate}

聚合在多维数据集级别定义，用于报告。 A **[!UICONTROL Workflow]** 选项卡。

有关Adobe Campaign中多维数据集和使用聚合的更多信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html){target=&quot;_blank&quot;}。


要更新聚合，请编辑 **[!UICONTROL Update aggregate]** 活动，然后选择要更新的多维数据集和聚合。

您可以执行 **完全更新** 或&#x200B;**部分更新**.

默认情况下，在每次计算期间都会执行完整更新。 要启用部分更新，请选择相关选项并定义更新条件。

**良好做法**:a **[!UICONTROL Scheduler]** 活动可用于指定计算更新的频率。

![](assets/scheduler-and-cube-aggregate.png)
