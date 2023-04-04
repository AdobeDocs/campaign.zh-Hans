---
product: campaign
title: 在工作流中更改维度
description: 了解如何使用更改维度活动
feature: Workflows, Targeting Activity
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# 更改维度{#change-dimension}

使用 **[!UICONTROL Change dimension]** 活动，以在构建受众时更改定向维度。 此活动会根据数据模板和输入维度来移动轴。 例如，您从“合同”维度切换到“客户”维度。

您还可以使用此活动来定义新目标的附加列，并定义重复数据删除条件。

配置 **[!UICONTROL Change dimension]** 活动，请应用以下步骤：

1. 通过 **[!UICONTROL Change dimension]** 字段。

   ![](assets/s_user_change_dimension_param1.png)

1. 在维度更改期间，您可以保留所有元素或选择要保留在输出中的元素。 在以下示例中，为max。 重复项数量设置为2。

   ![](assets/s_user_change_dimension_limit.png)

   如果选择仅保留一条记录，则工作架构中会显示一个集合：此集合表示在最终结果中不会定向的所有记录（因为只保留一个记录）。 与所有其他集合一样，此集合允许您计算聚合或恢复列中的信息。

   例如，如果您将 **[!UICONTROL Customers]** 维度 **[!UICONTROL Recipients]** 维度中，则可以定位特定商店的客户，同时添加购买次数。

1. 如果选择不保留所有这些信息，则可以配置复制管理模式。

   ![](assets/s_user_change_dimension_param2.png)

   蓝色箭头允许您定义重复的处理优先级。

   在以上示例中，收件人首先会在其电子邮件地址上删除重复项，然后根据需要在其帐号上删除重复项。

1. 的 **[!UICONTROL Result]** 选项卡，您可以添加其他信息。

   例如，您可以使用 **子字符串** 类型函数。 操作步骤：

   * 单击 **[!UICONTROL Add data...]** 链接并选择 **[!UICONTROL Data linked to the filtering dimension]**.

      ![](assets/wf_change-dimension_sample_01.png)

      >[!NOTE]
      >
      >有关创建和管理其他列的信息，请参阅 [添加数据](query.md#add-data).

   * 选择上一个定向维度（在轴切换之前），然后选择 **[!UICONTROL Zip Code]** 在收件人的 **[!UICONTROL Location]** 子树，然后单击 **[!UICONTROL Edit expression]**.

      ![](assets/wf_change-dimension_sample_02.png)

   * 单击 **[!UICONTROL Advanced selection]** 选择 **[!UICONTROL Edit the formula using an expression]**.

      ![](assets/wf_change-dimension_sample_03.png)

   * 使用列表中提供的函数并指定要执行的计算。

      ![](assets/wf_change-dimension_sample_04.png)

   * 最后，输入刚刚创建的列的标签。

      ![](assets/wf_change-dimension_sample_05.png)

1. 执行工作流以查看此配置的结果。 比较更改维度活动前后表格中的数据，并比较工作流表的结构，如以下示例所示：

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)
