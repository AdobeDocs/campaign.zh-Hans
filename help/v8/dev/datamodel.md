---
solution: Campaign
product: Adobe Campaign
title: Campaign 数据模型快速入门
description: Campaign 数据模型快速入门
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---

# Campaign 数据模型快速入门{#gs-ac-datamodel}

Adobe Campaign 提供了预定义的数据模型。本节提供一些关于Adobe Campaign数据模型的内置表及其交互的详细信息。 Adobe Campaign依赖于包含链接在一起的表的云数据库。

Adobe Campaign数据模型的基本结构可以描述为：

* **收件人表**:数据模型依赖于主表，该主表默认为收件人表(nmsRecipient)。此表可用于存储所有营销用户档案。

   ：灯泡：有关收件人表的详细信息，请参阅[此部分](#ootb-profiles)。

* **投放表**:数据模型还包括专用于存储所有营销活动的部件。通常是投放表(NmsDelivery)。 此表中的每个记录都表示投放操作或投放模板。 它包含执行投放(如目标、内容等)所需的所有参数。

* **日志表**:这些表存储与执行活动相关的所有日志。

   投放日志是所有渠道中发送给收件人或设备的所有消息。 主投放日志表(NmsBroadLog)包含所有收件人的投放日志。
主跟踪日志表(NmsTrackingLog)存储所有收件人的跟踪日志。 跟踪日志指收件人的反应，如电子邮件的开头和点击。 每个反应对应一个跟踪日志。
投放日志和跟踪日志将在某个时间段后删除，该时间段在Adobe Campaign中指定并可以修改。 因此，强烈建议定期出口日志。

* **技术表**:收集用于应用程序流程的技术数据，包括操作符和用户权限(NmsGroup)、文件夹(XtkFolder)。

>[!NOTE]
>
>要访问每个表的说明，请转至“管理”>“配置”>“模式”，从列表中选择资源，然后单击&#x200B;**“文档**”选项卡。

从Adobe Campaign开始，您需要评估默认数据模型以检查最适合存储营销数据的表。

您可以将默认收件人表与现成字段一起使用，如[此部分](#ootb-profiles)中所述。 如果需要，您可以使用两种机制扩展它：

* [用新字段](extend-schema.md) 扩展现有表。例如，您可以向收件人表添加新的“忠诚度”字段。
* [创建一个新表](create-schema.md)，例如，一个“购买”表，列出数据库每个用户档案所购买的所有数据，并将其链接到收件人表。

：灯泡：了解在[本节](datamodel-best-practices.md)中使用活动数据模型时的最佳实践。

## 内置用户档案表{#ootb-profiles}

Adobe Campaign中内置的收件人表(nmsrecipient)为构建数据模型提供了良好的起点。 它包含许多可轻松扩展的预定义字段和表链接。 当您主要针对收件人时，此功能特别有用，因为它适合以收件人为中心的简单数据模型。

使用标准收件人表的好处有：

* 利用订阅、种子列表等主要功能开箱即用
* 为营销数据库提供以收件人为中心的数据模型
* 更快的实施
* 由支持和合作伙伴轻松维护

可以扩展收件人表，但不能减少表中字段或链接的数量。

：灯泡：了解如何扩展[本节](extend-schema.md)中的现有模式。

:arrow_upper_right:查看[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)中内置收件人表扩展的示例

您还可以使用不同的收件人表来更好地满足您的业务或功能需求。 此方法具有局限性，在[本节](custom-recipient.md)中有说明。

## 活动表和云数据库

要更好地了解活动 v8中的表管理，请注意，表是在活动与其Snowflake Cloud数据库之间复制的。

：灯泡：了解有关[本节](../config/replication.md)中复制策略和机制的更多信息。

**相关主题**

：灯泡：了解如何在[此部分](../start/import.md)中导入用户档案
：灯泡：了解有关[本节](../start/audiences.md)中的活动受众的更多信息
