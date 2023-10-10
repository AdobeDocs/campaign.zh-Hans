---
product: campaign
title: 查询
description: 了解有关查询工作流活动的更多信息
feature: Workflows, Targeting Activity, Query Editor
role: User, Data Engineer
exl-id: 717e4f7c-3a8e-4930-9a06-b7412d6e1675
source-git-commit: 28742db06b9ca78a4e952fcb0e066aa5ec344416
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 1%

---

# 查询{#query}



## 创建查询 {#creating-a-query}

通过查询，您可以根据条件选择目标。 您可以将区段代码关联到查询结果并在其中插入附加数据。
有关查询示例的详细信息，请参阅此 [本节](querying-recipient-table.md).

![](assets/query-activity.png)

有关使用和管理附加数据的更多信息，请参阅 [添加数据](#adding-data).

此 **[!UICONTROL Edit query...]** 利用链接，可通过以下方式定义群体的定位类型、限制和选择标准：

1. 选择定位和筛选维度。 默认情况下，目标是从收件人中选择的。限制过滤器的列表与用于投放定位的筛选器相同。

   定向维度与我们将处理的元素类型（例如，操作定向的群体）一致。

   通过筛选维度，可以收集这些元素，例如与目标人员相关的信息（合同、完全和最终结算等）。

   有关详细信息，请参见 [定位和筛选维度](targeting-workflows.md#targeting-and-filtering-dimensions).

   ![](assets/targeting-filtering-dimensions.png)

   查询可以基于集客过渡的数据，如有必要，可通过选择 **[!UICONTROL Temporary schema]** 选择定位和过滤维度时。

   ![](assets/query_temporary_table.png)

1. 使用向导定义群体。 要输入的字段可以因目标类型而异。 您可以使用以下工具预览符合您当前条件的目标群体 **[!UICONTROL Preview]** 选项卡。

   ![](assets/query-sample.png)

1. 如果您已选择 **[!UICONTROL Filtering conditions]** 在步骤1中或使用 **[!UICONTROL Filters]** > **[!UICONTROL Advanced filter...]** 选项，之后您将必须手动添加筛选条件。

   您还可以通过选中相应的框来添加数据分组条件。 要实现此目的，筛选维度必须与查询的定向维度不同。 有关分组的详细信息，请参阅此 [部分](query-grouping-management.md).

   您也可以使用表达式生成器并将其与逻辑选项AND、OR和EXCEPT组合来添加更多标准。

   如果您希望稍后重复使用过滤器，请保存该过滤器。

## 添加数据 {#adding-data}

通过附加列，可收集有关定向群体的其他信息，如合同编号、新闻稿订阅或来源。 此数据可以存储在Adobe Campaign数据库或外部数据库中。

此 **[!UICONTROL Add data...]** 链接允许您选择要收集的其他数据。

![](assets/wf_add_data_link.png)

首先，选择要添加的数据类型：

![](assets/wf_add_data_1st_option.png)

* 选择 **[!UICONTROL Data linked to the filtering dimension]** 以选择Adobe Campaign数据库中的数据。
* 选择 **[!UICONTROL External data]** 从外部数据库添加数据。 此选项仅在您购买了 **联合数据访问** 选项。 有关详细信息，请参见 [访问外部数据库（联合数据访问）](accessing-an-external-database--fda-.md).
* 选择 **[!UICONTROL An offer proposition]** 用于添加一组列的选项，这些列允许您存储优惠引擎生成的最佳建议。 此选项仅在您购买了 **互动** 模块。

如果平台上未安装可选模块，则不会显示此阶段。 你将被直接带往下一个阶段。

要从Adobe Campaign数据库添加数据，请执行以下操作：

1. 选择要添加的数据类型。 这可以是属于筛选维度的数据或存储在链接表中的数据。

   ![](assets/query_add_columns.png)

1. 如果数据属于查询的过滤维度，则只需在可用字段列表中选择该数据，即可在输出列中显示该数据。

   ![](assets/wf_add_data_field_selection.png)

   您可以添加：

   * 根据从目标群体或聚合（上个月内的待定购买次数、收据平均金额等）中获得的数据计算的字段。 例如，转到 [选择数据](targeting-workflows.md#selecting-data).
   * 使用创建的新字段 **[!UICONTROL Add]** 按钮显示在输出列列表的右侧。

     您还可以添加信息集合，例如合同列表、最近5次投放等。 收藏集与字段一致，这些字段可以为同一用户档案具有多个值（1-N关系）。 有关详细信息，请参见 [编辑其他数据](targeting-workflows.md#editing-additional-data).

要添加链接到目标群体的信息集合，请执行以下操作：

1. 在向导的第一步，选择 **[!UICONTROL Data linked to the filtering dimension]** 选项：
1. 选择包含要收集信息的表，然后单击 **[!UICONTROL Next]**.

   ![](assets/wf_add_data_linked_table.png)

1. 如有必要，通过选择集合中的值之一来指定要保留的集合元素数。 **[!UICONTROL Data collected]** 字段。 默认情况下，将恢复集合中的所有行，然后根据在以下步骤中指定的条件进行筛选。

   * 如果收藏集的单个元素与此收藏集的过滤条件一致，请选择 **[!UICONTROL Single row]** 在 **[!UICONTROL Data collected]** 字段。

     >[!IMPORTANT]
     >
     >此模式会优化由于集合元素上的直接连接而生成的SQL查询。
     >
     >如果不满足初始条件，则结果可能有缺陷（缺少线或线重叠）。

   * 如果选择恢复多行(**[!UICONTROL Limit the line count]**)您可以指定要收集的行数。
   * 如果收集的列包含聚合，例如声明的失败次数、网站的平均支出等等 您可以使用 **[!UICONTROL Aggregates]** 值。

   ![](assets/query_add_collection_param.png)

1. 指定集合的子选择。

   ![](assets/query_add_columns_collection_filter.png)

1. 如果您已选择 **[!UICONTROL Limit the line count]** 选项，定义所收集数据的过滤顺序。 一旦收集的行数超过您指定的要保留的行数，则筛选顺序允许您指定要保留的行。

## 示例：基于简单收件人属性定向 {#example--targeting-on-simple-recipient-attributes}

在以下示例中，查询试图识别居住在法国的18至30岁的男子。 例如，此查询将用于旨在使其成为排他选件的工作流中。

>[!NOTE]
>
>中提供了其他查询示例 [本节](querying-recipient-table.md).

1. 命名您的查询，然后选择 **[!UICONTROL Edit query...]** 链接。
1. 选择 **[!UICONTROL Filtering conditions]** 在可用的过滤器类型列表中。
1. 为建议的目标输入不同的标准。 此处使用AND选项组合标准。 要包含在选择中，收件人必须满足以下四个条件：

   * 标题为“先生”的收件人（也可以使用找到） **性别** 字段和选择 **男** 作为值)。
   * 年龄在30岁以下的收件人。
   * 18岁以上的收件人。
   * 居住在法国的收件人。

   ![](assets/query_example.png)

   您可以查看与您的条件组合匹配的SQL：

   ![](assets/query_example_sql.png)

1. 您可以通过预览在相关选项卡中与您的查询匹配的收件人，来检查您的标准是否正确：

   ![](assets/query_example_preview.png)

1. 保存您的过滤器，以便您以后可以通过单击 **[!UICONTROL Finish]** > **[!UICONTROL OK]**.
1. 通过向工作流中添加其他活动来继续编辑工作流。 启动查询并完成上一个查询步骤后，将显示找到的收件人数量。 您可以使用鼠标弹出菜单显示更多详细信息(右键单击过渡> **[!UICONTROL Display the target...]**)。

   ![](assets/query_example_result.png)

## 输出参数 {#output-parameters}

* 表名
* 架构
* recCount

这组三个值标识查询所定向的群体。 **[!UICONTROL tableName]** 是记录目标标识符的表的名称， **[!UICONTROL schema]** 是群体的模式（通常为nms：recipient）和 **[!UICONTROL recCount]** 是表中的元素数。

此值是工作表的模式。 此参数对于以下类型的所有过渡有效： **[!UICONTROL tableName]** 和 **[!UICONTROL schema]**.

## 优化查询 {#optimizing-queries}

以下部分提供了优化在Adobe Campaign上运行的查询的最佳实践，以限制数据库上的工作负载并改善用户体验。

### 联接和索引 {#joins-and-indexes}

* 高效的查询依赖于索引。
* 对所有连接使用索引。
* 在架构上定义链接将确定连接条件。 链接表的主键上应有一个唯一索引，并且联接应位于此字段上。
* 通过在数字字段而不是字符串字段上定义键来执行联接。
* 避免执行外连接。 只要有可能，请使用Zero ID记录实现外部连接功能。
* 对连接使用正确的数据类型。

  确保 `where` 子句与字段的类型相同。

  一个常见的错误是： `iBlacklist='3'` 位置 `iBlacklist` 是数值字段，并且 `3` 表示文本值。

  确保您知道查询的执行计划。 避免进行完整的表扫描，特别是对于每分钟运行的实时查询或近乎实时的查询。

### 函数 {#functions}

* 请注意以下功能 `Lower(...)`. 当使用Lower函数时，不使用Index。
* 仔细检查使用“like”指令或“upper”或“lower”指令的查询。 将“Upper”应用于用户输入，而不是数据库字段。

### 过滤维度 {#filtering-dimensions}

使用查询的筛选维度，而不是使用“存在方式”运算符。

![](assets/optimize-queries-filtering.png)

在查询中，过滤器中的“存在”条件无效。 它们等同于SQL中的子查询：

`select iRecipientId from nmsRecipient where iRecipientId IN (select iRecipientId from nmsBroadLog where (...))`

最佳实践是改用查询的筛选维度：

![](assets/optimize-queries-filtering2.png)

SQL中过滤维度的等效项是内部联接：

`select iRecipientId from nmsRecipient INNER JOIN nmsBroadLog ON (...)`

有关筛选维度的更多信息，请参阅 [本节](build-a-workflow.md#targeting-and-filtering-dimensions).

### 架构 {#architecture}

* 构建开发平台，其卷、参数和架构与生产平台相似。
* 对开发和生产环境使用相同的值。 请尽量使用相同的方式：

   * 操作系统,
   * 版本,
   * 数据,
   * 应用程序,
   * 卷。

  >[!NOTE]
  >
  >在开发环境中工作的功能可能无法在数据可能不同的生产环境中工作。 尝试识别主要差异以预测风险并准备解决方案。

* 进行与目标卷匹配的配置。 大型卷需要特定的配置。 适用于100,000个收件人的配置可能无法适用于10,000,000个收件人。

  考虑系统启用后的扩展方式。 不能因为某事物具有小规模运作而认为它适合大件作品。 应该使用与生产卷类似的卷进行测试。 您还应该评估在高峰时间、高峰日以及在整个项目周期内卷更改（调用的次数、数据库的大小）的影响。
