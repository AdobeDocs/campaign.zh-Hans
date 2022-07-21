---
product: campaign
title: 创建营销活动
description: 了解如何创建和执行营销活动
feature: Campaigns, Cross Channel Orchestration, Programs
exl-id: 90dd2dad-1380-490e-b958-4a28a7d930ed
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 3%

---

# 创建项目和营销策划{#create-programs-and-campaigns}

活动编排组件可在 **[!UICONTROL Campaigns]** 选项卡：在这里，您可以看到营销项目和营销策划及其相关元素的概述。

营销计划由营销策划组成，营销策划由投放、资源等组成。 有关投放、预算、审阅人和链接文档的所有信息都归入营销活动。

![](assets/campaigns-create-from-home.png)

![](assets/do-not-localize/how-to-video.png) [在视频中发现项目和营销策划](#video)

## 使用方案和计划{#work-with-plan-and-program}

### 创建计划和方案层次结构 {#create-plan-and-program}

每个营销活动都属于属于某个计划的项目。 所有计划、项目和营销策划均可通过 **[!UICONTROL Campaign calendar]** 菜单 **促销活动** 选项卡。

在开始构建营销活动和投放之前，请为营销计划和项目配置文件夹层次结构。

1. 单击 **资源管理器** 图标。
1. 右键单击要在其中创建计划的文件夹。
1. 选择 **添加新文件夹> Campaign Management >计划**.

   ![](assets/create-new-plan-folder.png)

1. 重命名计划。
1. 右键单击新创建的计划，然后选择 **属性……**.
1. 在 **常规** ，修改 **内部名称** 以避免在资源包导出期间出现重复。

   ![](assets/plan-properties.png)

1. 单击&#x200B;**保存**。
1. 右键单击新创建的计划，然后选择 **创建新的“程序”文件夹**.

   ![](assets/program-folder.png)

1. 重复上述步骤以重命名新的程序文件夹及其内部名称。


### 配置程序 {#edit-a-program}

编辑程序时，请使用下面描述的选项卡浏览并配置该程序。

* 的 **计划** 选项卡显示月、周或日的项目日历，具体取决于您在日历标题中单击的选项卡。 您可以从此页面创建营销策划、项目或任务。 [了解详情](#campaign-calendar)

* 的 **编辑** 选项卡，您可以个性化项目：名称、开始和结束日期、预算、链接的文档等。

   ![](assets/new-program-edit-tab.png)

## 使用营销活动{#work-with-campaigns}

### 创建营销策划 {#create-a-campaign}

您可以通过营销活动列表创建营销活动。 要显示此视图，请选择 **[!UICONTROL Campaigns]** 菜单 **[!UICONTROL Campaigns]** 功能板，然后单击 **[!UICONTROL Create]**.

的 **[!UICONTROL Program]** 字段中，您可以选择要将营销策划附加到的项目。 此信息是强制性的。

![](assets/new-campaign-settings.png)

营销策划也可通过营销策划或项目日历创建。 [了解详情](#campaign-calendar)

在营销活动创建窗口中，选择营销活动模板并添加营销活动的名称和描述。 您还可以指定营销活动开始和结束日期。

单击 **[!UICONTROL OK]** 创建营销活动。 它会添加到项目计划和营销策划列表中。

然后，您可以编辑刚刚创建的营销活动并定义其参数。 要打开和配置此营销活动，Ypu可以：

1. 浏览营销活动日历并选择要显示的营销活动，然后单击 **[!UICONTROL Open]** 链接。
1. 浏览 **[!UICONTROL Schedule]** 选项卡，选择营销策划并将其打开。
1. 浏览营销活动列表，并点击要编辑的营销活动名称。

所有这些操作都会将您引导至营销活动仪表板。

![](assets/campaigns-dashboard-approve.png)

访问以下部分，了解如何配置营销活动：

* [添加投放](marketing-campaign-deliveries.md)
* [管理资产和文档](marketing-campaign-assets.md)
* [构建目标受众](marketing-campaign-target.md)
* [设置审批流程](marketing-campaign-approval.md)
* [管理库存和预算](providers--stocks-and-budgets.md)


### 编辑营销活动设置 {#campaign-settings}

营销活动通过营销活动模板创建。 您可以配置可重复使用的模板，其中已为其选择某些选项并保存其他设置。

对于每个营销活动，都提供以下功能：

* 参考文档和资源：您可以将文档与营销活动（简介、报告、图像等）关联。 支持所有文档格式。 [了解详情](marketing-campaign-deliveries.md#manage-associated-documents)。
* 定义成本：对于每个营销活动，Adobe Campaign允许您定义可在创建营销活动时使用的成本条目和成本计算结构。 例如：印刷成本、使用外部代理、房租等。 [了解详情](providers--stocks-and-budgets.md#defining-cost-categories)。
* 定义目标：您可以为营销活动定义可量化的目标，例如订阅者数量、业务量等。 此信息稍后会用在营销活动报表中。
* 管理种子地址和控制组。 [了解详情](marketing-campaign-deliveries.md#defining-a-control-group)).
* 管理批准：您可以选择要批准的处理，并根据需要选择审核运算符或运算符组。 [了解详情](marketing-campaign-approval.md#checking-and-approving-deliveries)。

>[!NOTE]
>
>要访问和更新营销活动设置，请浏览 **[!UICONTROL Advanced campaign parameters...]** 链接 **[!UICONTROL Edit]** 选项卡。

### 监控营销活动 {#monitor-a-campaign}

对于每个营销活动，作业、资源和投放都集中在功能板中。 通过此界面，您可以管理和编排营销活动。

借助Adobe Campaign，您可以设置协作流程，以创建和批准营销活动的各个步骤：预算、目标、内容等的审批 此编排详见 [此部分](marketing-campaign-approval.md).

![](assets/campaigns-dashboard-approval-tab.png)

>[!NOTE]
>
>营销活动中可用的组件取决于其模板。 营销活动模板配置在 [此部分](marketing-campaign-templates.md#campaign-templates).

完成营销活动后，使用 **[!UICONTROL Reports]** 链接以访问营销活动报告。

![](assets/campaigns-reports-dashboard.png)

## 营销活动日历 {#campaign-calendar}

营销活动日历显示所有项目、计划、营销活动和投放。

要编辑计划、项目、营销策划或投放，请在日历中浏览其名称，然后使用 **[!UICONTROL Open]** 链接。 随后，它会显示在新选项卡中，如下所示：

![](assets/campaign-calendar.png)

您可以过滤营销活动日历中显示的信息。 为此，请单击 **[!UICONTROL Filter]** 链接，然后选择筛选条件。

![](assets/campaign_planning_filter.png)

>[!NOTE]
>
>当您按日期过滤时，所有开始日期晚于指定日期和/或结束日期早于指定日期的营销活动都会显示。 使用每个字段右侧的日历选择日期。

您还可以使用 **[!UICONTROL Search]** 字段来筛选显示的项目。

链接到每个项目的图标允许您查看其状态：已完成、正在进行、正在编辑等。

要过滤要显示的营销活动，请单击 **[!UICONTROL Filter]** 链接，然后选择要显示的营销活动状态。

![](assets/calendar-filter-options.png)

浏览日历时，您还可以创建项目或营销策划。

![](assets/campaign-create-from-calendar.png)

当您通过 **[!UICONTROL Schedule]** 选项卡，营销活动会自动链接到相关项目。 的 **[!UICONTROL Program]** 字段。


## 使用Web界面 {#use-the-web-interface-}

您可以通过Internet浏览器访问Adobe Campaign控制台屏幕，以查看所有营销活动和投放，以及有关数据库中用户档案的报告和信息。 此访问不启用记录创建。 根据操作员权限，您可以查看和/或对数据库中的数据执行操作。 例如，您可以批准营销活动内容和定位、重新启动或停止投放等。

1. 与往常一样，通过https://登录`<your instance>:<port>/view/home`.
1. 使用菜单访问概述。

   ![](assets/web-access-campaigns.png)

除了在营销活动中导航和查看外，您还可以执行以下类型的任务：

* 监控实例上的活动
* 参与验证流程，例如批准或拒绝投放内容
* 执行其他快速操作，例如暂停工作流
* 访问所有报表功能
* 参加论坛讨论

此表汇总了您可以通过浏览器对营销活动执行的操作：

| 页面  | 操作 |
| --- | --- |
| 营销活动、投放、选件等的列表。 | 删除列表项 |
| 营销活动 | 取消营销活动 |
| 投放 | 批准投放内容和目标<br/>提交投放内容<br/>确认投放<br/>暂停和停止投放 |
| Web应用程序 | 创建Web应用程序<br/>编辑应用程序内容和属性<br/>将应用程序内容另存为模板<br/>发布应用程序 |
| 优惠 | 批准选件内容和资格<br/>禁用在线选件 |
| 任务 | 完成任务<br/>取消任务 |
| 营销资源 | 批准资源<br/>锁定和解锁资源 |
| Campaign包 | 提交资源包以供审批<br/>批准或拒绝资源包<br/>取消资源包 |
| 营销活动订单 | 创建订单<br/>接受或拒绝订单 |
| Stock | 删除库存行 |
| 优惠模拟 | 启动和停止模拟 |
| 定位工作流 | 启动、暂停和停止工作流 |
| 报告 | 在报表历史记录中保存当前数据 |
| 论坛 | 添加讨论<br/>在讨论中回复留言<br/>进行讨论并退订 |

### 管理批准

可以通过Web访问来批准目标或投放内容。

![](assets/web-access-approval.png)

您还可以使用通知消息中包含的链接。 如需详细信息，请参阅[此部分](marketing-campaign-approval.md#checking-and-approving-deliveries)。


## 教程视频 {#video}

此视频演示如何创建营销计划、项目和营销策划。

>[!VIDEO](https://video.tv.adobe.com/v/333810?quality=12)
