---
title: 使用Adobe Campaign工作流管理和自动化流程
description: 工作流入门
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 8e1401ef0aada30d941905936b45c6c1819c83a7
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 2%

---

# 工作流入门{#gs-with-workflows}

配置Campaign以利用强大的营销活动自动化功能。

您可以设置：

* 工作流
* 周期性活动
* 端到端验证周期
* 警报
* 自动报告发送
* 触发的事件

>[!NOTE]
>
>Adobe Campaign Web UI提供了重新设计的工作流画布，允许创建更动态、更个性化的客户历程。 要了解有关Web UI工作流的详细信息，请参阅[Adobe Campaign Web UI文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/wf/gs-workflows){target=_blank}。


## 设计和使用工作流 {#gs-ac-wf}

使用Adobe Campaign工作流从创建区段、准备消息到投放，提高营销活动各个方面的速度和规模。

了解如何在这些[端到端用例](#end-to-end-uc)中设计工作流。

在以下页面中了解有关工作流用户界面和执行的更多信息：

* [工作流入门](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}

* [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hans){target="_blank"}

* [内置技术工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=zh-Hans){target="_blank"}

* [监视工作流执行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=zh-Hans){target="_blank"}

* [在营销活动工作流中构建受众](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"}

## 工作流活动 {#wf-activities}

在[本节](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=zh-Hans){target="_blank"}中了解关于可用工作流活动的更多信息

工作流活动按类别分组。 提供了四个活动类别：

* [定位活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=zh-Hans){target="_blank"}：查询、读取列表、扩充、合并等
* [流控制活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=zh-Hans){target="_blank"}：调度程序、分支、警报、外部信号等
* [操作活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=zh-Hans){target="_blank"}：跨渠道投放、Javascript代码、CRM活动、更新聚合等
* [事件活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=zh-Hans){target="_blank"}：文件传输、Web下载等

### 更改数据源活动 {#change-data-source-activity}

**[!UICONTROL Change data source]**&#x200B;活动允许您更改工作流&#x200B;**[!UICONTROL Working table]**&#x200B;的数据源。 这为跨不同数据源（如FDA、FFDA和本地数据库）管理数据提供了更大的灵活性。

**[!UICONTROL Working table]**&#x200B;允许Adobe Campaign工作流处理数据并与工作流活动共享数据。
默认情况下，**[!UICONTROL Working table]**&#x200B;与我们查询的数据源在同一数据库中创建。

例如，在查询存储在云数据库上的&#x200B;**[!UICONTROL Profiles]**&#x200B;表时，您将在同一云数据库上创建&#x200B;**[!UICONTROL Working table]**。
若要更改此设置，您可以添加&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活动以为&#x200B;**[!UICONTROL Working table]**&#x200B;选择其他数据源。

请注意，在使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活动时，您需要切换回云数据库以继续执行工作流。

要使用&#x200B;**[!UICONTROL Change Data Source]**&#x200B;活动，请执行以下操作：

1. 创建工作流。

1. 使用&#x200B;**[!UICONTROL Query]**&#x200B;活动查询目标收件人。

   有关&#x200B;**[!UICONTROL Query]**&#x200B;活动的详细信息，请参阅[此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hans){target="_blank"}。

1. 在&#x200B;**[!UICONTROL Targeting]**&#x200B;选项卡中，添加&#x200B;**[!UICONTROL Change data source]**&#x200B;活动并双击该活动以选择&#x200B;**[!UICONTROL Default data source]**。

   随后会将包含查询结果的工作表移动到默认的PostgreSQL数据库。

1. 从&#x200B;**[!UICONTROL Actions]**&#x200B;选项卡中，拖放&#x200B;**[!UICONTROL JavaScript code]**&#x200B;活动以对工作表执行单一操作。

   有关&#x200B;**[!UICONTROL JavaScript code]**&#x200B;活动的详细信息，请参阅[此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=zh-Hans){target="_blank"}。

1. 添加另一个&#x200B;**[!UICONTROL Change data source]**&#x200B;活动以切换回云数据库。

   双击活动并选择&#x200B;**[!UICONTROL Active FDA external account]**，然后选择相应的外部帐户。

1. 您现在可以启动工作流。

## 管理虚拟仓库 {#warehouse}

创建工作流后，您可以使用&#x200B;**[!UICONTROL Properties]**&#x200B;按钮访问其他选项以进行进一步配置。

在[此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=zh-Hans){target="_blank"}中了解有关&#x200B;**工作流属性**&#x200B;的更多信息。

从工作流&#x200B;**[!UICONTROL Properties]**&#x200B;的&#x200B;**[!UICONTROL Execution]**&#x200B;选项卡中，您可以选择将工作流链接到不同的仓库并优化工作负载管理。 有关&#x200B;**仓库**&#x200B;的详细信息，请参阅[Snowflake文档](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}。

![](assets/warehouse.png)

根据工作流的用途，您可以从&#x200B;**[!UICONTROL Warehouse]**&#x200B;下拉列表中选择以下三个仓库：

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**：创建新工作流时默认设置。

* **[!UICONTROL Import / Export]**：应该使用导入或导出工作流进行设置，以优化活动的性能。

* **[!UICONTROL Campaign Burst]**：应使用活动或投放工作流进行设置，以优化投放处理时间。

>[!NOTE]
>
>仅为内置工作流设置&#x200B;**[!UICONTROL System]**&#x200B;仓库。

## 设置循环活动

设计循环工作流并在每次执行工作流时创建新投放实例。 例如，如果您的工作流设计为每周运行一次，那么一年后将产生52次投放。 这也意味着日志将由每个投放实例分隔。

在[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=zh-Hans){target="_blank"}中了解如何创建周期性营销活动。


## 利用触发事件

使用Campaign事务型消息传递可自动执行从信息系统触发的事件生成的消息。 这些事务型消息可以是发票、订单确认、送货确认、密码更改、产品不可用通知、帐户对帐单或网站帐户创建等。 这些消息可以通过电子邮件、短信或推送通知单独或批量发送。

在[本节](../send/transactional.md)中了解有关事务性消息传递功能的更多信息。

连接Adobe Campaign和Adobe Analytics以检索用户操作并发送近乎实时的个性化消息。

请参阅[本节](../start/connect.md)以了解如何将Campaign与其他解决方案集成


## 工作流端到端用例{#end-to-end-uc}

在此部分中，您将找到各种利用Campaign工作流功能的用例。

### 投放 {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [发送生日电子邮件](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hans){target="_blank"}

  此用例介绍了如何计划在收件人生日当天向其列表发送定期电子邮件。

* [加载投放内容](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=zh-Hans){target="_blank"}
当您的投放内容在位于远程服务器的HTML文件中可用时，您可以轻松将此内容加载到Adobe Campaign投放中。

* [跨渠道投放工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html?lang=zh-Hans){target="_blank"}
了解如何构建跨渠道投放工作流。 目标在于将受众从数据库的收件人划分为不同的组，并向第一组发送电子邮件，向另一组发送短信。

* [具有自定义日期字段的电子邮件扩充](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html?lang=zh-Hans){target="_blank"}
了解如何向本月庆祝生日的用户档案发送包含自定义数据字段的电子邮件。 该电子邮件将包含优惠券，有效期限为他们的生日前后一周。

以及Campaign v7文档中的以下页面：

* [自动创建、编辑和发布内容](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html?lang=zh-Hans){target="_blank"}
了解如何使用Campaign内容管理加载项自动创建和交付内容块。

* [A/B测试](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html?lang=zh-Hans){target="_blank"}
了解如何通过定位工作流比较两个电子邮件投放内容。 消息和文本在两种投放中都相同：只有布局发生变化。 目标群体分为三类：两个测试群体和其余群体。 向每个测试组发送投放的不同版本。

### 监控 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [向列表发送报告](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html?lang=zh-Hans){target="_blank"}
了解如何以PDF格式生成每月内置的跟踪指标报告，并将其发送给Campaign操作员的列表。

* [监督您的工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html?lang=zh-Hans){target="_blank"}
了解如何创建工作流，以便您监控一组“已暂停”、“已停止”或“出现错误”的工作流的状态。

* [向操作员发送个性化提醒](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html?lang=zh-Hans){target="_blank"}
了解如何向操作员发送警报，该操作员将包含打开了新闻稿但未单击新闻稿所包含链接的用户档案的名称。

### 数据管理 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [协调数据更新](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html?lang=zh-Hans){target="_blank"}
了解如何检查更新进程是否已在执行其他更新操作之前结束。 为此，我们将设置一个实例变量，并让工作流测试实例是否正在运行，以决定是否继续执行工作流并执行更新。

* [创建摘要列表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html?lang=zh-Hans){target="_blank"}
了解如何创建工作流，在收集文件并完成几项增强后，可让您创建摘要列表。 此示例基于在商店中进行购买的联系人列表。

* [扩充数据](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=zh-Hans){target="_blank"}
了解如何根据参加最新竞争的用户档案得分向其发送个性化投放。

* [使用聚合](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=zh-Hans){target="_blank"}
了解如何识别最后添加到数据库的收件人。

* [使用增量查询每季度更新列表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html?lang=zh-Hans){target="_blank"}
了解如何使用增量查询自动更新收件人列表。

* [设置循环导入工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=zh-Hans){target="_blank"}
了解如何设计一个可重复使用的工作流，用于导入来自Adobe Campaign数据库中CRM的用户档案。

### 定位 {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [查询收件人表](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html?lang=zh-Hans){target="_blank"}
了解如何恢复其电子邮件域为“orange.co.uk”且不在伦敦居住的收件人的姓名和电子邮件。

* [查询投放信息](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html?lang=zh-Hans){target="_blank"}
了解如何定义有关投放信息的查询以检索用户档案的行为。

* [计算聚合](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html?lang=zh-Hans){target="_blank"}
了解如何根据性别统计居住在伦敦的个人资料数量。

* [使用多对多关系进行查询](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html?lang=zh-Hans){target="_blank"}
了解如何查找过去7天内未联系的用户档案。

* [调用查询中的实例变量](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html?lang=zh-Hans){target="_blank"}
了解如何使用实例变量动态计算要对群体应用的分割百分比。

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=zh-Hans#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

