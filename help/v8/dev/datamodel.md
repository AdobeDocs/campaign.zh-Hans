---
title: Campaign 数据模型快速入门
description: Campaign 数据模型快速入门
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 4%

---

# Campaign 数据模型快速入门{#gs-ac-datamodel}

Adobe Campaign 提供了预定义的数据模型。本节详细介绍Adobe Campaign数据模型的内置表及其交互。 Adobe Campaign依赖于包含链接在一起的表的Cloud数据库。

Adobe Campaign数据模型的基本结构可描述如下：

* **收件人表**:数据模型依赖于主表，该主表默认为收件人表(nmsRecipient)。 此表存储了所有营销用户档案。

   ![](../assets/do-not-localize/glass.png) 有关Recipient表的更多信息，请参阅 [此部分](#ootb-profiles).

* **投放表**:数据模型还包括专用于存储所有营销活动的部分。 通常为Delivery表(NmsDelivery)。 此表中的每个记录都表示投放操作或投放模板。 它包含执行投放所需的所有参数，如目标、内容等。

* **日志表**:这些表存储与执行营销活动相关的所有日志。

   投放日志是所有渠道中发送给收件人或设备的所有消息。 主投放日志表(NmsBroadLogRcp)包含所有收件人的投放日志。
主跟踪日志表(NmsTrackingLogRcp)存储所有收件人的跟踪日志。 跟踪日志是指收件人的反应，如电子邮件的打开次数和点击次数。 每个反应都对应一个跟踪日志。
投放日志和跟踪日志将在特定时间段后删除(在Adobe Campaign中指定并可修改)。 因此，强烈建议定期导出日志。

* **技术表**:收集用于应用程序过程的技术数据，包括运算符和用户权限(xtkGroup)、文件夹(XtkFolder)。

>[!NOTE]
>
>要访问每个表的描述，请转到管理员>配置>数据架构，从列表中选择资源，然后单击 **文档** 选项卡。

从Adobe Campaign开始，您需要评估默认数据模型，以检查哪个表最适合存储营销数据。

您可以将默认的“收件人”表与现成字段一起使用，如 [此部分](#ootb-profiles). 如果需要，可以使用两种机制扩展该扩展：

* [扩展现有表](extend-schema.md) 中的“隐藏主体”。 例如，您可以向收件人表中添加新的“忠诚度”字段。
* [创建新表](create-schema.md)，例如“购买”表列出了数据库每个用户档案进行的所有购买，并将其链接到收件人表。

![](../assets/do-not-localize/glass.png) 在中使用Campaign数据模型时了解最佳实践 [此部分](datamodel-best-practices.md).

## 内置配置文件表 {#ootb-profiles}

Adobe Campaign中内置的收件人表(nmsrecipient)为构建数据模型提供了一个良好的起点。 它有许多预定义的字段和表链接，可轻松扩展。 当您主要定向收件人时，这种方法特别有用，因为它适合以收件人为中心的简单数据模型。

使用标准收件人表的好处包括：

* 使用订阅、种子列表等关键功能开箱即用
* 使用以收件人为中心的数据模型提供营销数据库
* 更快的实施
* 由支持人员和合作伙伴轻松维护

可以扩展收件人表，但不能减少表中字段或链接的数量。

![](../assets/do-not-localize/glass.png) 了解如何在 [此部分](extend-schema.md).

![](../assets/do-not-localize/book.png) 探索中内置的收件人表扩展示例 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table){target=&quot;_blank&quot;}

您还可以使用其他收件人表来更好地满足您的业务或功能要求。 此方法存在限制，有关描述请参见 [此部分](custom-recipient.md).

## Campaign表和云数据库

为了更好地了解Campaign v8中的表管理，请注意，在 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，则表会在Campaign及其Snowflake云数据库之间复制。

![](../assets/do-not-localize/glass.png) 进一步了解 [此部分](../architecture/replication.md).

**相关主题**

![](../assets/do-not-localize/glass.png) 了解如何在 [此部分](../start/import.md)
![](../assets/do-not-localize/glass.png) 在 [此部分](../start/audiences.md)
