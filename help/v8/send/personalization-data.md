---
title: 个性化数据源
description: 了解哪些源可用于个性化
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---


# 个性化数据源{#personalization-data}

可从各种类型的源中检索个性化数据：Campaign数据库数据源、外部文件数据源或外部数据库数据源。

## Campaign数据库数据源

在最常见的情况下，个性化数据存储在数据库中。 例如，“收件人个性化字段”是在收件人表中定义的所有字段，即标准字段(通常为：姓氏、名字、地址、城市、出生日期等) 或自定义字段。

![电子邮件中的促销活动个性化字段](assets/perso-campaign-datasource.png)


## 外部文件数据源

您可以使用包含列中定义的所有字段的外部文件。 在消息投放定义期间，此文件将用作输入。 您可以选择是否在数据库中插入这些用户档案。

要选择要用作数据源的文件，请浏览到消息创建窗口中的“收件人”链接，然后选择 **在外部文件中定义** 选项。 加载文件后，从个性化选项中访问收件人数据 **文件中的字段** 中。

![来自文件的个性化数据](assets/perso-from-file.png)


## FDA数据源

个性化数据可通过 [联合数据访问](../connect/fda.md).  如果要使用外部数据库中的数据在投放中进行个性化，请收集要在工作流中使用的数据，以在临时表格中提供。

要执行此操作，请添加 **查询** 活动，并使用 **添加数据……** 链接以选择外部数据库。 详细过程可在 [此部分](../../automation/workflow/query.md#adding-data).

然后，使用临时表格中的数据对投放进行个性化。 配置查询活动后，从 **Target扩展** 中。

![来自外部数据库的个性化数据](assets/perso-external-db.png)

使用在FDA中访问的外部数据时，建议在专用工作流中使用 **使用工作流准备个性化数据** 选项。

### 优化个性化 {#optimize-personalization}

您可以使用专用选项优化个性化： **[!UICONTROL Prepare the personalization data with a workflow]**，在 **[!UICONTROL Analysis]** 选项卡。

在投放分析期间，此选项会自动创建并执行一个工作流，该工作流将链接到目标的所有数据存储在临时表格中，包括来自FDA中链接表格的数据。

选中此选项可在处理大量数据时大大提高投放分析性能，尤其是当个性化数据通过FDA来自外部表时。 [了解详情](../connect/fda.md)。

要使用此选项，请执行以下步骤：

1. 创建营销策划.
1. 在 **[!UICONTROL Targeting and workflows]** 的 **查询** 活动。
1. 添加 **[!UICONTROL Email delivery]** 活动，并将其打开。
1. 转到 **[!UICONTROL Analysis]** 选项卡 **[!UICONTROL Delivery properties]** ，然后选择 **[!UICONTROL Prepare the personalization data with a workflow]** 选项。
1. 配置投放并启动工作流以启动分析。

完成分析后，个性化数据会通过临时技术工作流存储在临时表格中，该工作流在分析过程中会即时创建。

此工作流在Adobe Campaign界面中不可见。 它仅是快速存储和处理个性化数据的技术手段。

分析完成后，转到工作流 **[!UICONTROL Properties]** ，然后选择 **[!UICONTROL Variables]** 选项卡。 在此处，您可以看到可用于进行SQL调用以显示其所包含ID的临时表的名称。

## 工作流中的个性化数据

在工作流的上下文中创建投放时，您可以使用临时工作流表中的数据。 工作流临时工作表中存储的数据可用于个性化任务。 数据可在个性化字段中使用。

此数据分组在 **[!UICONTROL Target extension]** 菜单。 如需详细信息，请参阅[此部分](../../automation/workflow/use-workflow-data.md#target-data)。




