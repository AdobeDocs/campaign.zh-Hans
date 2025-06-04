---
title: 使用工作流数据
description: 了解如何使用工作流数据
feature: Workflows, Data Management
version: Campaign v8, Campaign Classic v7
exl-id: 5014c2ed-2a74-4122-b7b9-d3703db7ab12
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 8%

---

# 使用工作流数据{#how-to-use-workflow-data}

您可以使用工作流活动执行多个任务。 查找以下使用示例，这些示例用于通过创建列表来更新数据库、管理订阅、通过工作流发送消息，或丰富您的投放及其受众。

[此部分](workflow-use-cases.md)中提供了一组工作流用例。

## 数据生命周期 {#data-life-cycle}

### 工作流临时工作表 {#work-table}

在工作流中，从一个活动传输到另一个活动的数据存储在临时工作表中。

通过右键单击相应的过渡，可以显示和分析此数据。

![](assets/wf-right-click-analyze.png)

要实现此目的，请选择相关菜单：

* **[!UICONTROL Display the target...]**

  此菜单显示目标群体的可用数据。

  ![](assets/wf-right-click-display.png)

  您可以在&#x200B;**[!UICONTROL Schema]**&#x200B;选项卡中访问工作表的结构。

  ![](assets/wf-right-click-schema.png)

  如需详细信息，请参阅[此小节](monitor-workflow-execution.md#worktables-and-workflow-schema)。

* **[!UICONTROL Analyze target...]**

  使用此菜单可访问描述性分析向导，该向导允许您生成有关过渡数据的统计和报告。

  请参阅[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/analyzing-populations/about-descriptive-analysis.html?lang=zh-Hans){target="_blank"}以了解如何使用描述性分析向导。

在执行工作流时清除目标数据。 只能访问最后一个工作表。 您可以配置工作流以使所有工作表保持可访问状态：选中工作流属性中的&#x200B;**[!UICONTROL Keep the result of interim populations between two executions]**&#x200B;选项。

![](assets/wf-purge-data-option.png)

>[!CAUTION]
>
>**不得**&#x200B;在&#x200B;**生产**&#x200B;工作流中选中此选项。此选项用于分析结果，并且是仅为测试目的而设计，因此只能用于开发或暂存环境。


### 利用目标数据 {#target-data}

存储在工作流临时工作表中的数据可用于个性化任务。 数据可用于[个性化字段](../../v8/send/personalization-fields.md)。

例如，您可以在投放中使用通过列表收集的数据。 为此，请使用以下语法：

```
%= targetData.FIELD %
```

**[!UICONTROL Target extension]** (targetData)类型个性化元素不可用于定位工作流。 必须在工作流中构建投放目标，并在投放的集客过渡中指定。

在下方的示例中，您将收集要用于个性化电子邮件中的客户信息列表。 应用以下步骤：

1. 创建工作流以收集信息，将其与数据库中已有的数据相协调，然后开始投放。

   ![](assets/wf-targetdata-sample-1.png)

1. 在我们的示例中，文件内容如下所示：

   ```
   Music,First name,Last name,Account,CD/DVD,Card
   Pop,David,BLAIR,4323,CD,0
   Rock,Daniel,ARCARI,3222,DVD,1
   Disco,Uma,ALTON,0488,DVD,0
   Jazz,Paul,BOLES,6475,CD,1
   Jazz,David,BOUKHARI,0841,DVD,1
   [...]
   ```

   要加载文件，请如下所示配置&#x200B;**[!UICONTROL Data loading (file)]**&#x200B;活动：

   ![](assets/wf-targetdata-sample-2.png)

1. 配置&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动以将收集的数据与Adobe Campaign数据库中已有的数据相协调。 在此，对帐密钥是帐号：

   ![](assets/wf-targetdata-sample-3.png)

1. 然后配置&#x200B;**[!UICONTROL Delivery]**：它是基于模板创建的，收件人由集客过渡指定。

   ![](assets/wf-targetdata-sample-4.png)

   >[!CAUTION]
   >
   >只能使用过渡中包含的数据来个性化投放。 **targetData**&#x200B;类型个性化字段仅可用于&#x200B;**[!UICONTROL Delivery]**&#x200B;活动的入站群体。

1. 在投放模板中，使用在工作流中收集的字段。

   为此，请插入&#x200B;**[!UICONTROL Target extension]**&#x200B;类型个性化字段。

   ![](assets/wf-targetdata-sample-5.png)

   在此，我们要插入客户最喜爱的音乐流派和媒体类型（CD或DVD），如工作流收集的文件中所述。

   此外，我们将为会员卡持有者（即“卡”值等于1的收件人）添加优惠券。

   ![](assets/wf-targetdata-sample-6.png)

   **[!UICONTROL Target extension]** (targetData)类型数据使用与所有个性化字段相同的特性插入投放。 它们还可以在主题、链接标签或链接本身中使用。


## 更新数据库 {#update-the-database}

所有收集的数据都可用于更新数据库或在投放中使用。 例如，您可以丰富消息内容个性化的可能性（包括消息中的合同数量，指定去年的平均购物车数等）或详细信息群体定位（向合同共同所有者发送消息，以在线服务的1,000个最佳订阅者为目标等）。 此数据还可以在列表中导出或存档。

### 更新列表  {#list-updates}

Adobe Campaign数据库和现有列表的数据可以使用两个专用活动进行更新：

* **[!UICONTROL List update]**&#x200B;活动允许您在数据列表中存储工作表。

  您可以选择现有列表或创建现有列表。 在这种情况下，将计算名称，并可能计算记录文件夹。

  ![](assets/s_user_create_list.png)

  请参阅[列表更新](list-update.md)。

* **[!UICONTROL Update data]**&#x200B;活动对数据库中的字段执行批量更新。

  有关详细信息，请参阅[更新数据](update-data.md)。

### 管理订阅 {#subscription-management}

要了解通过工作流订阅和取消订阅信息服务的收件人的相关信息，请参阅[订阅服务](subscription-services.md)。
