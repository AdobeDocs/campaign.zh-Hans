---
title: Campaign中的密钥管理
description: 密钥管理入门
feature: Configuration, FFDA
role: Developer
level: Intermediate
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: 9d500f185a9e706b6558135978c4f8c79d92d0d4
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 3%

---

# 密钥管理和唯一性 {#key-management}

在[Enterprise (FFDA)部署](enterprise-deployment.md)的上下文中，主键是一个通用唯一标识符(UUID)，它是一个字符串。 要创建此UUID，架构的主元素必须包含设置为&#x200B;**true**&#x200B;的&#x200B;**autouuid**&#x200B;和&#x200B;**autopk**&#x200B;属性。

Adobe Campaign v8使用[!DNL Snowflake]作为核心数据库。 [!DNL Snowflake]数据库的分布式架构不提供机制来确保表中密钥的唯一性：最终用户负责Adobe Campaign数据库中的密钥一致性。

要保持关系数据库的一致性，必须避免键上（尤其是主键上）出现重复项。 主键上的重复导致数据管理工作流活动出现问题，例如&#x200B;**查询**、**协调**、**更新数据**&#x200B;等。 这对于在更新[!DNL Snowflake]表时定义适当的协调条件至关重要。


>[!CAUTION]
>
>重复的密钥不限于UUID。 在ID中，可能会发生这种情况，包括在自定义表中创建的自定义键。


## Unicity Service{#unicity-service}

Unicity Service是一个Cloud Database Manager组件，可帮助用户保留和监控Cloud Database表中唯一键约束的完整性。 这样，您就可以降低插入重复键值的风险。

由于Cloud Database不强制执行unicity约束，因此Unicity Service在使用Adobe Campaign管理数据时降低了插入重复项的风险。

### 唯一性工作流{#unicity-wf}

Unicity Service附带专用的&#x200B;**[!UICONTROL Unicity alerting]**&#x200B;内置工作流，用于监视唯一性约束并在检测到重复项时发出警报。

此技术工作流可从Campaign Explorer的&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]**&#x200B;节点中获取。 **不能修改**。

此工作流会检查所有自定义和内置模式以检测重复行。

![](assets/unicity-alerting-wf.png)

如果&#x200B;**[!UICONTROL Unicity alerting]** (ffdaUnicity)工作流检测到一些重复的键，则会将它们添加到特定的&#x200B;**Audit Unicity**&#x200B;表中，该表包括架构名称、键类型、受影响的行数和日期。 您可以从&#x200B;**[!UICONTROL Administration > Audit > Key Unicity]**&#x200B;节点访问重复的键。

![](assets/unicity-table.png)

作为数据库管理员，您可以使用SQL活动删除重复项或联系Adobe客户关怀部门以获取更多指导。

### 警报{#unicity-wf-alerting}

检测到重复的键时，会向&#x200B;**[!UICONTROL Workflow Supervisors]**&#x200B;操作员组发送特定通知。 可以在&#x200B;**[!UICONTROL Unicity alerting]**&#x200B;工作流的&#x200B;**警报**&#x200B;活动中更改此警报的内容和受众。

![](assets/wf-alert-activity.png)


## 附加护栏 {#duplicates-guardrails}

Campaign提供了一组新护栏，以防止在[!DNL Snowflake]数据库中插入重复的键。

>[!NOTE]
>
>从Campaign v8.3开始提供这些护栏。要检查您的版本，请参阅[此部分](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### 投放准备 {#remove-duplicates-delivery-preparation}

在投放准备期间，Adobe Campaign会自动从受众中删除任何重复的UUID。 此机制可防止在准备投放时出现任何错误。 作为最终用户，您可以在投放日志中检查此信息：由于密钥重复，可以从主目标中排除某些收件人。 在这种情况下，将显示以下警告： `Exclusion of duplicates (based on the primary key or targeted records)`。

![](assets/exclusion-duplicates-log.png)

### 更新工作流中的数据 {#duplicates-update-data}

在[Enterprise (FFDA)部署](enterprise-deployment.md)的上下文中，不能选择内部密钥(UUID)作为字段来更新工作流中的数据。

![](assets/update-data-no-internal-key.png)

### 查询包含重复项的架构 {#query-with-duplicates}

当工作流开始在架构上运行查询时，Adobe Campaign会检查[审核唯一性表](#unicity-wf)中是否报告了任何重复记录。 如果是这样，工作流会记录一条警告，因为对重复数据的后续操作可能会影响工作流结果。

![](assets/query-with-duplicates.png)

此检查在下列工作流活动中执行：

* 查询
* 增量查询
* 读取列表


>[!NOTE]
>
>如果您要从其他Campaign版本进行过渡，则必须删除重复项、排除故障和清理数据，以避免影响您的过渡。
