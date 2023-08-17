---
product: campaign
title: 使用增量查询每季度更新列表
description: 在此使用案例中，增量查询用于自动更新收件人列表。
feature: Workflows
exl-id: eedc796a-865f-47a8-8807-5980546b8adf
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 5%

---

# 使用增量查询每季度更新列表 {#quarterly-list-update}



在以下示例中， [增量查询](incremental-query.md) 用于自动更新收件人列表。 这些收件人作为季节性营销活动的一部分进行定位。

由于这些促销活动在每个季初启动以提供相关的体育活动，因此这些列表每季度更新一次。 但是，此营销活动只能每9个月定位此处的收件人一次。 这样，您就可以安排收件人的资格频度，并在这些年中针对不同的季节提供活动。

![](assets/incremental_query_example.png)

1. 将增量查询和列表更新活动添加到新工作流中。
1. 配置 **[!UICONTROL Incremental query]** 选项卡中指定的活动 [创建查询](query.md#creating-a-query).
1. 选择 **[!UICONTROL Scheduling & History]** 选项卡，然后指定270天的历史记录。 已定向的收件人在270天（即大约9个月）内将不再被定向。

   然后单击 **[!UICONTROL Change...]** 按钮。

1. 要确保列表在每个季节开始之前更新，请选择 **[!UICONTROL Monthly]**.
1. 在下一个屏幕上，选择3月、6月、9月和12月。 选择每月的20日，然后选择要启动工作流的时间。
1. 接下来，选择查询的有效期。 例如，如果希望此活动永久处于活动状态，请选择 **[!UICONTROL Permanent validity]**.

1. 批准增量查询后，按照中的说明配置列表更新活动 [列表更新](list-update.md).

因此，该工作流将在每个季节开始之前自动启动。 列表将更新为符合条件的新收件人以接收优惠。
