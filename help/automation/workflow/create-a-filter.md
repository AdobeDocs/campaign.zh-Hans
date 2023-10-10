---
product: campaign
title: 创建筛选
description: 了解如何在执行查询时创建过滤器
feature: Query Editor, Workflows
role: User
exl-id: 8e6fd9b4-77c4-4af8-921b-c3fe104fa5bc
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# 创建筛选 {#creating-a-filter}

Adobe Campaign中可用的过滤器是通过使用与查询相同的操作模式创建的过滤条件来定义的。

此 **[!UICONTROL Administration > Configuration > Predefined filters]** 节点包含列表和概述中使用的所有筛选器。

例如，可以按以下方式筛选运算符列表 **[!UICONTROL Active accounts]**：

![](assets/query_editor_filter_sample_1.png)

匹配筛选器包含对以下项的查询： **[!UICONTROL Account disabled]** 的值 **[!UICONTROL Operators]** 架构：

![](assets/query_editor_filter_sample_2.png)

对于同一列表， **[!UICONTROL By login or label]** 过滤器允许您根据在过滤器字段中输入的值过滤列表上的数据：

![](assets/query_editor_filter_sample_3.png)

其构建方式如下：

![](assets/query_editor_filter_sample_4.png)

要匹配筛选条件，操作员帐户必须检查以下条件之一：

* 其标签包含输入字段中输入的字符，
* 操作员名称包含输入字段中输入的字符，
* 描述区域的内容包含在输入字段中输入的字符。

>[!NOTE]
>
>此 **[!UICONTROL Upper]** 函数中，您可以停用区分大小写的函数。

此 **[!UICONTROL Taken into account if]** 列允许您定义这些过滤条件的应用条件。 在此， **$(/tmp/@text)** 字符表示链接到过滤器的输入字段的内容：

![](assets/query_editor_filter_sample_5.png)

此处， **$(/tmp/@text)=&#39;代理&#39;**

此 **$(/tmp/@text)！=&quot;** 表达式在输入字段不为空时应用每个条件。
