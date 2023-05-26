---
title: 使用Campaign和外部数据库（联合数据访问）
description: 了解如何使用Campaign和外部数据库
feature: Federated Data Access
role: Admin
level: Beginner, Intermediate
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# 联合数据访问 (FDA){#gs-fda}

使用FDA连接器（联合数据访问）将Campaign连接到一个或多个 **外部数据库** 并处理存储到其中的信息，而不会影响您的Campaign云数据库数据。 然后，您可以访问外部数据，而无需更改Adobe Campaign数据的结构。

![](../assets/do-not-localize/speech.png)   作为托管Cloud Services用户， [联系人Adobe](../start/campaign-faq.md#support) 以将外部数据库与Campaign连接。


>[!NOTE]
>
>* 用于联合数据访问的兼容数据库列在 [兼容性矩阵](../start/compatibility-matrix.md).
>
>* 在上下文中 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，可以使用特定的外部帐户管理Campaign本地数据库和Snowflake云数据库之间的通信。 此外部帐户按Adobe和为您设置 **不得** 将被修改。
>



## 最佳实践和限制

FDA选项受您使用的第三方数据库系统的限制。

此外，请注意以下限制和最佳实践：

* FDA选项可用于在工作流中以批处理模式处理外部数据库中的数据。 为了避免出现性能问题，建议不要在单一操作（例如：个性化、交互、实时消息传送等）的上下文中使用FDA模块。

* 尽可能避免需要同时使用Adobe Campaign和外部数据库的操作。 要执行此操作，您可以：

   * 将Adobe Campaign数据库导出到外部数据库，并仅在将结果重新导入Adobe Campaign之前从外部数据库执行操作。

   * 从外部Adobe Campaign数据库中收集数据并在本地执行操作。
   如果要使用外部数据库中的数据在投放中实施个性化，请收集要在工作流中使用的数据，以使其在临时表中可用。 然后，使用临时表中的数据将投放个性化。 要执行此操作，请使用在专用工作流中预先处理消息个性化 **[!UICONTROL Prepare the personalization data with a workflow]** 选项，可在 **[!UICONTROL Analysis]** 选项卡中显示的投放属性。 在投放分析期间，此选项会自动创建并执行一个工作流，该工作流会将链接到目标的所有数据（包括链接在外部数据库中的表中的数据）存储在临时表中。

   >[!CAUTION]
   >
   >此选项可显着改进执行个性化步骤时的性能。


## 在工作流中使用外部数据

Campaign附带多个工作流活动，您可以使用这些活动与外部数据库中的数据交互：

* **筛选外部数据**  — 使用 **[!UICONTROL Query]** 活动，用于添加外部数据并在定义的过滤器配置中使用它。

* **创建子集**  — 使用 **[!UICONTROL Split]** 创建子集的活动。 您可以使用外部数据来定义要使用的筛选条件。

* **加载外部数据库**  — 使用中的外部数据 **[!UICONTROL Data loading (RDBMS)]** 活动。

* **添加信息和链接**  — 使用 **[!UICONTROL Enrichment]** 活动，用于将其他数据添加到工作流的工作表，以及指向外部表的链接。 在这种情况下，它可以使用来自外部数据库的数据。

您也可以从上面列出的所有工作流活动中直接定义到外部数据库的连接，以供临时使用。 在这种情况下，它将在本地外部数据库上，仅在当前工作流中使用。

>[!CAUTION]
>
>此类型的配置必须仅用于临时收集数据。 外部帐户配置应首选用于任何其他用途。

例如，在 **[!UICONTROL Query]** 活动时，可以定义与外部数据库的临时连接，如下所示：

1. 打开活动并单击 **[!UICONTROL Add data...]**
1. 选择 **[!UICONTROL External data]** options
1. 选择 **[!UICONTROL Locally defining the data source]** option
1. 在下拉列表中选择目标数据库引擎。 输入服务器的名称并提供身份验证参数。 同时指定外部数据库的名称。
1. 选择存储数据的表。 您可以直接在相应的字段中输入表的名称，或者单击编辑图标以访问数据库表的列表。
1. 单击 **[!UICONTROL Add]** 按钮来定义外部数据库数据与Adobe Campaign数据库中的数据之间的一个或多个协调字段。 此 **[!UICONTROL Edit expression]** 图标 **[!UICONTROL Remote field]** 和 **[!UICONTROL Local field]** 允许您访问每个表的字段列表。
1. 如有必要，请指定筛选条件和数据排序模式。
1. 选择要在外部数据库中收集的其他数据。 要执行此操作，请双击要添加的字段，以在 **[!UICONTROL Output columns]**.
1. 单击 **[!UICONTROL Finish]** 以确认此配置。
