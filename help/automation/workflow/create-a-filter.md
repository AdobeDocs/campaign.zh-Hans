---
product: campaign
title: 创建筛选
description: 了解如何在执行查询时创建过滤器
feature: Query Editor, Workflows
exl-id: 8e6fd9b4-77c4-4af8-921b-c3fe104fa5bc
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# 创建筛选 {#creating-a-filter}

Adobe Campaign中可用的过滤器是通过使用与查询相同的操作模式创建的筛选条件来定义的。

此 **[!UICONTROL Administration > Configuration > Predefined filters]** 节点包含列表和概述中使用的所有筛选器。

例如，可通过以下方式筛选运算符列表 **[!UICONTROL Active accounts]**：

![](assets/query_editor_filter_sample_1.png)

匹配筛选器包含对 **[!UICONTROL Account disabled]** 的值 **[!UICONTROL Operators]** 架构：

![](assets/query_editor_filter_sample_2.png)

对于同一列表， **[!UICONTROL By login or label]** 筛选条件允许您根据在筛选条件字段中输入的值筛选列表上的数据：

![](assets/query_editor_filter_sample_3.png)

其构建方式如下：

![](assets/query_editor_filter_sample_4.png)

要匹配筛选条件，操作员帐户必须选中以下条件之一：

* 其标签包含输入字段中输入的字符，
* 操作员名称包含输入字段中输入的字符，
* 描述区域的内容包含在输入字段中输入的字符。

>[!NOTE]
>
>此 **[!UICONTROL Upper]** 函数可让您取消激活区分大小写的函数。

此 **[!UICONTROL Taken into account if]** 列允许您定义这些过滤条件的应用条件。 在此， **$(/tmp/@text)** 字符表示链接到筛选器的输入字段的内容：

![](assets/query_editor_filter_sample_5.png)

此处， **$(/tmp/@text)=&#39;代理&#39;**

此 **$(/tmp/@text)！=”** 表达式在输入字段不为空时应用每个条件。
