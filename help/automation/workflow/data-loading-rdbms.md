---
product: campaign
title: 数据加载 (RDBMS)
description: 了解有关数据加载(RDBMS)工作流活动的更多信息
feature: Workflows, Data Management Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2d650573-f630-4aba-bd40-2db88ef1c346
TQID: 'https://experienceleague.adobe.com/3FkutZSFu-yv9yuqmqQoxVrGaEVJrVuErmEC95JbVTM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: 97f7b899-98c8-5133-9446-bfaf99a51b9f
    internal-label: Data Management Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%
---
# 数据加载 (RDBMS){#data-loading-rdbms}



通过&#x200B;**[!UICONTROL Data loading (RDBMS)]**&#x200B;活动，您可以直接访问此外部数据库，并仅收集定位所需的数据。

为了提高性能，我们建议使用查询活动（可在其中使用外部数据库的数据）。 有关详细信息，请参阅[访问外部数据库(FDA)](accessing-an-external-database-fda.md)。

操作如下：

1. 从列表中选择数据源，然后输入包含要提取的数据的表的名称。

   ![](assets/s_advuser_wf_sgbd_sample_1.png)

   在相应字段中输入的表的名称将用作在外部数据库中收集数据的模板。 工作流处理的表的名称可以由数据加载活动的集客过渡计算或传递。 要选择要使用的表，请单击&#x200B;**[!UICONTROL Advanced..]**。 链接并选择&#x200B;**[!UICONTROL Specified in the transition]**&#x200B;或&#x200B;**[!UICONTROL Explicit]**&#x200B;选项。

   ![](assets/s_advuser_wf_sgbd_sample_5.png)

1. 单击&#x200B;**[!UICONTROL Select the columns to extract...]**&#x200B;链接以选择要在数据库中收集的数据。

   ![](assets/s_advuser_wf_sgbd_sample_2.png)

1. 您可以根据此数据定义过滤器。 为此，请单击&#x200B;**[!UICONTROL Edit query....]**&#x200B;链接。

   这样收集的数据可在工作流的整个生命周期中使用。
