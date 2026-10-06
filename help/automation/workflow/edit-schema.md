---
product: campaign
title: 编辑架构
description: 了解有关编辑架构工作流活动的更多信息
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
TQID: 'https://experienceleague.adobe.com/uHsIfXEPlhLjwbGdRaUagbAhFhZb5JFxGurpSH4c0fI'
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
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
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
