---
title: 使用Adobe Campaign工作流管理和自动化流程
description: 工作流快速入门
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 4%

---

# 工作流快速入门{#gs-with-workflows}

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
>Adobe Campaign Web User界面提供了重新设计的工作流画布，允许创建更加动态和个性化的客户历程。 要了解有关Web UI工作流的详细信息，请参阅[Adobe Campaign Web UI文档](https://experienceleague.adobe.com/en/docs/campaign-web/v8/wf/gs-workflows){target=_blank}。


## 设计和使用工作流 {#gs-ac-wf}

使用Adobe Campaign工作流从创建区段、准备消息到投放，提高营销活动各个方面的速度和规模。

在以下页面中了解有关工作流用户界面和执行的更多信息：

* [工作流入门](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}

* [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

* [内置技术工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

* [监视工作流执行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

* [在营销活动工作流中构建受众](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"}

## 工作流活动 {#wf-activities}

在[本节](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=zh-Hans){target="_blank"}中了解关于可用工作流活动的更多信息

工作流活动按类别分组。 提供了四个活动类别：

* [定位活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}：查询、读取列表、扩充、合并等
* [流控制活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}：调度程序、分支、警报、外部信号等
* [操作活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}：跨渠道投放、Javascript代码、CRM活动、更新聚合等
* [事件活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}：文件传输、Web下载等

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

## 管理虚拟仓库 {#warehouse}

创建工作流后，您可以使用&#x200B;**[!UICONTROL Properties]**&#x200B;按钮访问其他选项以进行进一步配置。

在&#x200B;**此页面**&#x200B;中了解有关[工作流属性](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html){target="_blank"}的更多信息。

从工作流&#x200B;**[!UICONTROL Execution]**&#x200B;的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中，您可以选择将工作流链接到不同的仓库并优化工作负载管理。 有关&#x200B;**仓库**&#x200B;的详细信息，请参阅[Snowflake文档](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}。

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

在本节[中了解利用活动工作流功能](../../automation/workflow/workflow-use-cases.md)的用例。
