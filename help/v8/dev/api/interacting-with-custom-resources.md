---
title: 与自定义资源交互
description: 了解有关使用API进行自定义资源管理的更多信息/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
TQID: https://experienceleague.adobe.com/w8FCKOzUXzquVrDL2R6BJkkKWN-S1BaXZ4-sKl93iRI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 0%

---

# 与自定义资源交互 {#interacting-with-custom-resources}

**/customResources**&#x200B;端点允许您在REST中公开Campaign自定义资源。 基于此API，可在自定义实体和外部端点之间实现集成。

/customResources端点的行为与/profileAndServices端点完全相同。

此API中公开的自定义资源包括：

* 所有未在/profileAndServicesExt下公开的实体
* 所有与个人资料无关的实体，对于这些实体，还包括其子代和孙代。
* 默认情况下，所有未链接到任何内容的实体及其子项和孙项。

>[!NOTE]
>/profileAndServicesExt下可用的自定义资源不会在/customResources API中公开。


以下是从自定义资源检索元数据的示例：

```
GET /customResources/resourceType/<customResourceName>
```

要执行创建、更新或删除，请使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```
