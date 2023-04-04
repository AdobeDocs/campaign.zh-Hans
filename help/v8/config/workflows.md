---
title: 使用Adobe Campaign工作流管理和自动化各个流程
description: 工作流入门
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: b323dbf9504e39cca78f7082089b864544ee1633
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 4%

---

# 工作流入门{#gs-with-workflows}

配置Campaign以利用强大的营销活动自动化功能。

您可以设置：

* 工作流
* 定期促销活动
* 端到端验证周期
* 警报
* 自动发送报表
* 触发的事件

## 设计和使用工作流{#gs-ac-wf}

使用Adobe Campaign工作流可提高营销活动各个方面（从创建区段和准备消息到交付）的速度和规模。

了解如何在这些工作流中设计工作流 [端到端用例](#end-to-end-uc).

在以下页面中了解有关工作流用户界面和执行的更多信息：

* [工作流入门](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans)

* [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html)

* [内置技术工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html)

* [监控工作流执行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html)

* [在营销活动工作流中构建受众](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans)

## 工作流活动 {#wf-activities}

了解有关 [此部分](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html)

工作流活动按类别进行分组。 提供了四个活动类别：

* [定位活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html):查询、读取列表、扩充、并集等
* [流量控制活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html):调度程序、分支、警报、外部信号等
* [操作活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html):跨渠道投放、Javascript代码、CRM活动、更新聚合等
* [事件活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html):文件传输、Web下载等

### 更改数据源活动 {#change-data-source-activity}

的 **[!UICONTROL Change data source]** 活动，用于更改工作流的数据源 **[!UICONTROL Working table]**. 这为跨不同数据源（如FDA、FFDA和本地数据库）管理数据提供了更大的灵活性。

的 **[!UICONTROL Working table]** 允许Adobe Campaign工作流处理数据并与工作流活动共享数据。
默认情况下， **[!UICONTROL Working table]** 创建于与我们查询的数据源相同的数据库中。

例如，在查询 **[!UICONTROL Profiles]** 表，存储在云数据库上，您将创建一个 **[!UICONTROL Working table]** 在同一云数据库上。
要更改此设置，您可以将 **[!UICONTROL Change Data Source]** 活动，为您的 **[!UICONTROL Working table]**.

请注意，在使用 **[!UICONTROL Change Data Source]** 活动时，您需要切换回云数据库以继续执行工作流。

使用 **[!UICONTROL Change Data Source]** 活动：

1. 创建工作流.

1. 使用 **[!UICONTROL Query]** 活动。

   有关 **[!UICONTROL Query]** 活动，请参阅 [本页](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).

1. 从 **[!UICONTROL Targeting]** 选项卡，添加 **[!UICONTROL Change data source]** 活动，并双击该活动以选择 **[!UICONTROL Default data source]**.

   将包含查询结果的工作表移到默认的PostgreSQL数据库。

1. 从 **[!UICONTROL Actions]** 选项卡，拖放 **[!UICONTROL JavaScript code]** 对工作表执行统一操作的活动。

   有关 **[!UICONTROL JavaScript code]** 活动，请参阅 [本页](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html).

1. 添加其他 **[!UICONTROL Change data source]** 活动切换回云数据库。

   双击您的活动，然后选择 **[!UICONTROL Active FDA external account]** 然后是相应的外部帐户。

1. 您现在可以启动工作流。

## 管理虚拟仓库 {#warehouse}

创建工作流后，您可以使用 **[!UICONTROL Properties]** 按钮以进一步配置。

详细了解 **工作流属性** in [本页](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html).

从 **[!UICONTROL Execution]** 的 **[!UICONTROL Properties]**，您可以选择将工作流链接到不同的仓库并优化工作量管理。 有关 **仓库**，请参阅 [Snowflake文档](https://docs.snowflake.com/en/user-guide/warehouses-overview.html).

![](assets/warehouse.png)

根据工作流的用途，您可以从 **[!UICONTROL Warehouse]** 下拉列表：

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**:默认设置。

* **[!UICONTROL Import / Export]**:应使用导入或导出工作流进行设置，以优化活动的性能。

* **[!UICONTROL Campaign Burst]**:应使用营销活动或投放工作流进行设置，以优化投放处理时间。

>[!NOTE]
>
>的 **[!UICONTROL System]** 仅为内置工作流设置仓库。

## 设置定期促销活动

设计定期工作流，并在每次执行工作流时创建新投放实例。 例如，如果您的工作流设计为每周运行一次，则一年后将产生52次投放。 这也意味着日志将由每个投放实例分隔。

了解如何在 [本页](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=zh-Hans)


## 利用触发器事件

使用Campaign事务型消息传递自动化从信息系统触发的事件生成的消息。 例如，这些事务型消息可以是发票、订单确认、发运确认、密码更改、产品不可用通知、帐户对帐单或网站帐户创建。 这些消息可以单独或批量通过电子邮件、短信或推送通知发送。

![](../assets/do-not-localize/glass.png) 在 [此部分](../send/transactional.md).

连接Adobe Campaign和Adobe Analytics以检索用户操作并发送近乎实时的个性化消息。

![](../assets/do-not-localize/glass.png) 了解如何在 [此部分](../start/connect.md)


## 工作流端到端用例{#end-to-end-uc}

在此部分中，您将发现利用Campaign工作流功能的各种用例。

### 投放 {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [发送生日电子邮件](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hans)

   此用例介绍如何计划在收件人生日当天向收件人列表发送定期电子邮件。

* [加载投放内容](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html)
如果投放内容位于远程服务器上的HTML文件中，则可以轻松地将此内容加载到Adobe Campaign投放中。

* [跨渠道投放工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)
了解如何构建跨渠道投放工作流。 目标是将来自数据库收件人的受众划分为不同的组，并向第一个组发送电子邮件，向另一个组发送短信。

* [具有自定义日期字段的电子邮件扩充](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)
了解如何向本月庆祝生日的用户档案发送包含自定义数据字段的电子邮件。 该电子邮件将包含一个优惠券，其有效期为生日前后一周。

Campaign v7文档中的以下页面：

* [自动创建、编辑和发布内容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target="_blank"}
了解如何使用Campaign内容管理加载项自动创建和交付内容块。

* [A/B测试](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target="_blank"}
了解如何通过定位工作流比较两个电子邮件投放内容。 消息和文本在两个投放中都相同：只有布局发生更改。 目标群体分为三个：两个测试组和其余群体。 投放的不同版本会发送到每个测试组。

### 监测 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [向列表发送报表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html)
了解如何以PDF格式生成每月内置的跟踪指标报告，并将其发送到Campaign运算符列表。

* [监督工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html)
了解如何创建工作流，以便监视“已暂停”、“已停止”或“有错误”的一组工作流的状态。

* [向运营商发送个性化提醒](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html)
了解如何向操作员发送警报，该操作员将包含打开新闻稿但未单击新闻稿所包含链接的用户档案名称。

### 数据管理 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [坐标数据更新](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html)
了解如何在执行另一个更新操作之前检查更新过程是否已结束。 为此，我们将设置一个实例变量，并让工作流测试实例是否正在运行，以决定是否继续执行工作流并执行更新。

* [创建摘要列表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html)
了解如何创建工作流，在收集文件并进行多项扩充后，该工作流允许您创建摘要列表。 此示例基于在商店中购物的联系人列表。

* [丰富数据](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=zh-Hans)
了解如何根据参与最新竞争的用户档案的得分向其发送个性化投放。

* [使用聚合](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html)
了解如何识别添加到数据库的最后一个收件人。

* [使用增量查询每季度更新列表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html)
了解如何使用增量查询自动更新收件人列表。

* [设置定期导入工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html)
了解如何设计可重复使用的工作流，以导入来自Adobe Campaign数据库CRM的用户档案。

### 设定目标 {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [查询收件人表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html)
了解如何恢复电子邮件域名为“orange.co.uk”且不居住在伦敦的收件人的姓名和电子邮件。

* [查询投放信息](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html)
了解如何定义投放信息查询以检索用户档案的行为。

* [计算聚合](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html)
了解如何根据性别计算伦敦居民的档案数量。

* [使用多对多关系进行查询](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html)
了解如何查找过去7天内未联系的用户档案。

* [在查询中调用实例变量](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html)
了解如何使用实例变量动态计算要应用于群体的拆分百分比。

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

