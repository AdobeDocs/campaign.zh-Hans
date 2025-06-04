---
product: campaign
title: 编辑架构
description: 了解有关编辑架构工作流活动的更多信息
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 3%

---

# 编辑架构{#edit-schema}



可以使用&#x200B;**[!UICONTROL Edit schema]**&#x200B;活动在工作流中转换、规范化和扩充数据（如有必要）。 它通常用于标准化数据结构：您可以重命名输出列或修改其内容，例如通过计算字段或聚合的平均值。

此活动不更改工作表中的数据，只更改其架构，即数据的逻辑视图。

![](assets/wf_manipulation_box.png)

您还可以通过&#x200B;**[!UICONTROL Links]**&#x200B;选项卡创建与其他工作表的联接。

![](assets/wf_manipulation_box_link_tab.png)

下面的部分允许您配置连接条件的列表，即用于协调来自两个表的数据的标准。
