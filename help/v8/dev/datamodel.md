---
title: 开始使用 Campaign 数据模型
description: 开始使用 Campaign 数据模型并利用来自您的来源的数据以使您的通信和营销输出受益。
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 5%

---

# 开始使用 Campaign 数据模型 {#gs-ac-datamodel}

Adobe Campaign 提供了预定义的数据模型。本节提供了有关Adobe Campaign数据模型的内置表及其交互的一些详细信息。 Adobe Campaign依赖于包含链接在一起的表的云数据库。

Adobe Campaign数据模型的基本结构可描述如下：

* **收件人表**：数据模型依赖于主表，该主表默认为收件人表(**nmsRecipient**)。 此表存储了所有营销用户档案。 在中了解有关收件人表的更多信息 [本节](#ootb-profiles).

* **投放表**：此表为每个投放操作存储一个记录。 通常为投放表(**NmsDelivery**)。 此表表示投放操作或投放模板。 它包含执行投放所需的所有参数，如目标、内容等。 每个记录都更新多次，以反映投放进度

* **日志表**：这些表存储与活动执行关联的所有日志。

   * 投放日志是跨所有渠道发送给收件人或设备的所有消息。 主投放日志表(**NmsBroadLogRcp**)包含所有收件人的投放日志。
   * 此 **nmsBroadlog** table是系统中最大的表。 它为每条发送的消息存储一条记录，这些记录会被插入、更新以跟踪投放状态，并在历史记录被清除时删除。
   * 主跟踪日志表(**NmsTrackingLogRcp**)存储所有收件人的跟踪日志。 跟踪日志是指收件人的反应，例如电子邮件打开次数和点击次数。 每个反应对应于一个跟踪日志。

  投放日志和跟踪日志会在特定时段后删除，该特定时段在Adobe Campaign中指定并可进行修改。 因此，强烈建议定期导出日志。

* **技术表**：收集用于应用流程的技术数据，包括操作员和用户权限(**xtkGroup**)，用户会话(**xtkSessionInfo**)，浏览器树中的文件夹(**XtkFolder**)，工作流(**xtkWorkflow**)，等等。

>[!NOTE]
>
>要访问每个表的说明，请浏览 **管理>配置>数据架构**，从列表中选择资源，然后单击 **文档** 选项卡。

开始使用Adobe Campaign时，您需要评估默认数据模型，以检查哪个表最适合存储营销数据。

您可以将默认收件人表与现成字段一起使用，如中所述 [本节](#ootb-profiles). 如果需要，您可以使用两种机制来扩展它：

* [扩展现有表](extend-schema.md) 新增字段。 例如，您可以向收件人表添加新的“忠诚度”字段。
* [创建新表](create-schema.md)例如，有一个“Purchase”表，其中列出了数据库的每个用户档案进行的所有购买，并将其链接到收件人表。

在中使用Campaign数据模型时了解最佳实践 [本节](datamodel-best-practices.md).

## 内置配置文件表 {#ootb-profiles}

Adobe Campaign中的内置收件人表(nmsrecipient)为构建数据模型提供了一个良好的起点。 它具有许多可以轻松扩展的预定义字段和表链接。 当您主要定位收件人时，这项功能尤其有用，因为它适合以收件人为中心的简单数据模型。

使用标准收件人表的好处包括：

* 开箱即用地使用关键功能，如订阅、种子列表等
* 提供具有以收件人为中心的数据模型的营销数据库
* 更快的实施
* 由支持和合作伙伴轻松维护

可以扩展收件人表，但不能减少表中的字段或链接数。

了解如何在中扩展现有架构 [本节](extend-schema.md).

在中发现内置收件人表扩展的示例 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#extending-a-table){target="_blank"}

您还可以使用其他收件人表以更好地满足您的业务或功能要求。 此方法具有限制，具体说明见 [本节](custom-recipient.md).

## Campaign表和云数据库

要更好地了解Campaign v8中的表管理，请注意 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，这些表将在Campaign及其Snowflake云数据库之间复制。

了解有关复制策略和机制的更多信息，请参见 [本节](../architecture/replication.md).

**相关主题**

了解如何在中导入用户档案 [本节](../start/import.md)
在中了解有关Campaign受众的更多信息 [本节](../start/audiences.md)
