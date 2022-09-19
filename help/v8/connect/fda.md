---
title: 使用Campaign和外部数据库(FDA)
description: 了解如何使用Campaign和外部数据库
feature: Federated Data Access
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: bb03c804c1c65322d275d0a2ca1db0bfe974636d
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# 联合数据访问 (FDA){#gs-fda}

使用FDA连接器（联合数据访问）将Campaign连接到一个或多个 **外部数据库** 并处理存储在其中的信息，而不影响您的Campaign云数据库数据。 然后，您便可以访问外部数据，而无需更改Adobe Campaign数据的结构。

![](../assets/do-not-localize/speech.png)   作为托管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support) 使用Campaign实施Experience Cloud触发器。


>[!NOTE]
>
>* 联合数据访问的兼容数据库列在 [兼容性矩阵](../start/compatibility-matrix.md).
>
>* 在 [企业(FFDA)部署](../architecture/enterprise-deployment.md)，可使用特定外部帐户管理Campaign本地数据库与Snowflake云数据库之间的通信。 此外部帐户是按Adobe和 **必须** 修改。
>



## 最佳实践和限制

FDA选项受您使用的第三方数据库系统的限制。

此外，请注意以下限制和最佳实践：

* FDA选项用于在工作流中以批处理模式处理外部数据库中的数据。 为避免出现性能问题，不建议在统一操作的背景下使用FDA模块，例如：个性化、互动、实时消息传送等。

* 尽量避免同时使用Adobe Campaign和外部数据库所需的操作。 为此，您可以：

   * 将Adobe Campaign数据库导出到外部数据库，并仅在从外部数据库执行操作后再将结果重新导入Adobe Campaign。

   * 从外部Adobe Campaign数据库收集数据并在本地执行操作。
   如果要使用外部数据库中的数据在投放中进行个性化，请收集要在工作流中使用的数据，以在临时表格中提供。 然后，使用临时表格中的数据对投放进行个性化。 要执行此操作，请在专用工作流中使用 **[!UICONTROL Prepare the personalization data with a workflow]** 选项(在 **[!UICONTROL Analysis]** 选项卡。 在投放分析期间，此选项会自动创建并执行一个工作流，该工作流将链接到目标的所有数据存储在临时表中，包括来自外部数据库中链接的表的数据。

   >[!CAUTION]
   >
   >此选项可显着提高执行个性化步骤时的性能。


## 在工作流中使用外部数据

Campaign附带了多个工作流活动，您可以使用这些活动与来自外部数据库的数据进行交互：

* **对外部数据进行过滤**  — 使用 **[!UICONTROL Query]** 活动添加外部数据，并将其用在定义的过滤器配置中。

* **创建子集**  — 使用 **[!UICONTROL Split]** 活动以创建子集。 您可以使用外部数据定义要使用的筛选条件。

* **加载外部数据库**  — 在 **[!UICONTROL Data loading (RDBMS)]** 活动。

* **添加信息和链接**  — 使用 **[!UICONTROL Enrichment]** 活动向工作流的工作台添加其他数据，并链接到外部表。 在此上下文中，它可以使用外部数据库中的数据。

您还可以直接从上面列出的所有工作流活动定义与外部数据库的连接，以便用于临时用途。 在这种情况下，它将位于本地外部数据库上，仅在当前工作流中使用。

>[!CAUTION]
>
>此类配置只能临时用于收集数据。 对于任何其他用法，最好使用外部帐户配置。

例如，在 **[!UICONTROL Query]** 活动时，您可以定义与外部数据库的临时连接，如下所示：

1. 打开活动，然后单击 **[!UICONTROL Add data...]**
1. 选择 **[!UICONTROL External data]** 选项
1. 选择 **[!UICONTROL Locally defining the data source]** 选项
1. 在下拉列表中选择目标数据库引擎。 输入服务器的名称并提供身份验证参数。 还指定外部数据库的名称。
1. 选择存储数据的表。 您可以直接在相应的字段中输入表的名称，也可以单击编辑图标以访问数据库表的列表。
1. 单击 **[!UICONTROL Add]** 按钮，在外部数据库数据与Adobe Campaign数据库中的数据之间定义一个或多个协调字段。 的 **[!UICONTROL Edit expression]** 图标 **[!UICONTROL Remote field]** 和 **[!UICONTROL Local field]** 允许您访问每个表的字段列表。
1. 如有必要，请指定筛选条件和数据排序模式。
1. 选择要在外部数据库中收集的附加数据。 为此，请双击要添加以在 **[!UICONTROL Output columns]**.
1. 单击 **[!UICONTROL Finish]** 以确认此配置。
