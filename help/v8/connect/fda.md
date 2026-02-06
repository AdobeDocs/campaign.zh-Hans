---
title: 使用Campaign和外部数据库(FDA)
description: 了解如何使用Campaign和外部数据库
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 631c4986d24daeff870412566318adb170ce040f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# 联合数据访问 (FDA){#gs-fda}

使用FDA连接器（联合数据访问）将Campaign连接到一个或多个&#x200B;**外部数据库**，并处理存储在其中的信息而不影响Campaign云数据库数据。 然后，您可以访问外部数据，而无需更改Adobe Campaign数据的结构。

>[!NOTE]
>
>* [兼容性矩阵](../start/compatibility-matrix.md)中列出了用于联合数据访问的兼容数据库。
>
>* 在[企业(FFDA)部署](../../v8/architecture/enterprise-deployment.md)的上下文中，可以使用特定的外部帐户来管理Campaign本地数据库和Snowflake云数据库之间的通信。 此外部帐户由Adobe为您设置，不得修改&#x200B;****。
>
>* 作为托管云服务用户，[联系Adobe](../start/campaign-faq.md#support)以将外部数据库与Campaign连接。


## 最佳实践和限制

FDA选项受您使用的第三方数据库系统的限制的约束。

此外，请注意以下限制和最佳实践：

* FDA选项可用于在工作流中以批处理模式处理外部数据库中的数据。 为了避免出现性能问题，建议不要在单一操作的上下文中使用FDA模块，例如：个性化、交互、实时消息传送等。

* 尽可能避免需要同时使用Adobe Campaign和外部数据库的操作。 为此，您可以：

   * 将Adobe Campaign数据库导出到外部数据库，并仅在将结果重新导入Adobe Campaign之前从外部数据库执行操作。

   * 从外部Adobe Campaign数据库中收集数据，并在本地执行操作。

  如果要使用外部数据库中的数据在投放中进行个性化，请收集要在工作流中使用的数据，以使其在临时表中可用。 然后，使用临时表中的数据将投放个性化。 为此，请使用投放属性的&#x200B;**[!UICONTROL Prepare the personalization data with a workflow]**&#x200B;选项卡中的&#x200B;**[!UICONTROL Analysis]**&#x200B;选项，在专用工作流中预处理消息个性化。 在投放分析期间，此选项会自动创建并执行一个工作流，该工作流会将链接到目标的所有数据（包括链接至外部数据库的表中的数据）存储在临时表中。

  >[!CAUTION]
  >
  >此选项可显着改进执行个性化步骤时的性能。


## 在工作流中使用外部数据

Campaign附带几个工作流活动，您可以使用这些活动与外部数据库中的数据交互：

* **外部数据筛选** — 使用&#x200B;**[!UICONTROL Query]**&#x200B;活动添加外部数据并将其用于定义的筛选配置。

* **创建子集** — 使用&#x200B;**[!UICONTROL Split]**&#x200B;活动创建子集。 您可以使用外部数据来定义要使用的筛选条件。

* **加载外部数据库** — 在&#x200B;**[!UICONTROL Data loading (RDBMS)]**&#x200B;活动中使用外部数据。

* **添加信息和链接** — 使用&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动向工作流的工作表添加其他数据，并链接到外部表。 在这种情况下，它可以使用来自外部数据库的数据。

您也可以从上面列出的所有工作流活动中直接定义与外部数据库的连接，以作为临时用途。 在这种情况下，它将位于本地外部数据库中，仅在当前工作流中使用。

>[!CAUTION]
>
>此类型的配置必须仅用于临时收集数据。 外部帐户配置应首选用于任何其他用途。

例如，在&#x200B;**[!UICONTROL Query]**&#x200B;活动中，您可以定义与外部数据库的临时连接，如下所示：

1. 打开活动并单击&#x200B;**[!UICONTROL Add data...]**
1. 选择&#x200B;**[!UICONTROL External data]**&#x200B;选项
1. 选择&#x200B;**[!UICONTROL Locally defining the data source]**&#x200B;选项
1. 在下拉列表中选择目标数据库引擎。 输入服务器的名称并提供身份验证参数。 同时指定外部数据库的名称。
1. 选择存储数据的表。 您可以直接在相应的字段中输入表的名称，也可以单击编辑图标来访问数据库表的列表。
1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮可定义外部数据库数据与Adobe Campaign数据库中的数据之间的一个或多个协调字段。 通过&#x200B;**[!UICONTROL Edit expression]**&#x200B;和&#x200B;**[!UICONTROL Remote field]**&#x200B;的&#x200B;**[!UICONTROL Local field]**&#x200B;图标，可访问每个表的字段列表。
1. 如有必要，请指定筛选条件和数据排序模式。
1. 选择要在外部数据库中收集的其他数据。 为此，请双击要添加的字段以在&#x200B;**[!UICONTROL Output columns]**&#x200B;中显示它们。
1. 单击&#x200B;**[!UICONTROL Finish]**&#x200B;以确认此配置。
