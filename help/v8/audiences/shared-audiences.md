---
title: 使用 Adobe Experience Cloud 解决方案共享受众
description: 了解如何使用 Adobe Experience Cloud 解决方案共享受众
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 81%

---

# 使用 Adobe Experience Cloud 解决方案共享受众{#shared-audiences}

选项 1：AEP 源和目标

选项 2：Adobe People/AAM

您可以将 **Adobe Campaign** 与 **People 核心服务** 或 Adobe Audience Manager 集成。 然后，您将能够：

* 从不同的 Adobe Experience Cloud 解决方案导入共享受众/区段到 Adobe Campaign 中。 可通过 Adobe Campaign 中的列表导入受众。

* 以 Adobe Experience Cloud 共享受众的形式导出列表。您可在所用的不同 Adobe Experience Cloud 解决方案中使用这些受众。在工作流中完成定位后，可使用专门的 **[!UICONTROL Update shared audience]** 活动导出受众。

此集成支持两种类型的 Adobe Experience Cloud ID：

* **访客ID**:此标识符可协调Adobe Experience Cloud访客与Adobe Campaign收件人。
* **声明的ID**:此标识符可将所有类型的数据与Adobe Campaign数据库中的元素进行协调。 它是Adobe Campaign中的预定义协调键值。

   >[!NOTE]
   >
   > 声明的ID数据源也可与People核心服务集成一起使用。
   >
   >如果您使用 People 核心服务集成，并想要添加 Audience Manager 集成，则需要 Adobe Audience Manager 顾问的帮助，以避免在 Adobe Audience Manager 环境中转换为使用此声明的 ID 数据源时收集的所有 ID 同步丢失。

请参阅：

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=zh_Hans](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=zh_Hans)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh_Hans](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh_Hans)