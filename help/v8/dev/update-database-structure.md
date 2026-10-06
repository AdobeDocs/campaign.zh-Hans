---
title: 更新数据库结构
description: 更新数据库结构
feature: Configuration
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
TQID: 'https://experienceleague.adobe.com/1UBvvvkN-05BqOe4aOMpYFtKEMp0Yf-q9ECtbtmHzb0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%
---
# 更新数据库结构 {#updating-the-database-structure}

要应用对架构所做的修改，请启动数据库更新向导。 可以通过&#x200B;**[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;访问此助手。 它检查数据库的物理结构是否与其逻辑描述匹配，并执行SQL更新脚本。

![](assets/schema_update.png)

数据库中的模块将自动填充和激活。

![](assets/schema_update_select2.png)

按照以下步骤操作并查看数据库更新SQL脚本：

![](assets/schema_update2.png)

>[!NOTE]
>
>此代码位于编辑字段中，可以修改以删除或添加SQL代码。

接下来，启动数据库更新：

![](assets/schema_update3.png)
