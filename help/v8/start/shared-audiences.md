---
title: 使用 Adobe Experience Cloud 解决方案共享受众
description: 了解如何使用 Adobe Experience Cloud 解决方案共享受众
feature: Audiences
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 74%

---

# 使用 Adobe Experience Cloud 解决方案共享受众{#shared-audiences}


选项 1：AEP 源和目标

选项 2：Adobe People/AAM

您可以将 **Adobe Campaign** 与 **People 核心服务** 或 Adobe Audience Manager 集成。 然后，您将能够：

* 从不同的 Adobe Experience Cloud 解决方案导入共享受众/区段到 Adobe Campaign 中。 可通过 Adobe Campaign 中的列表导入受众。

* 以 Adobe Experience Cloud 共享受众的形式导出列表。您可在所用的不同 Adobe Experience Cloud 解决方案中使用这些受众。在工作流中完成定位后，可使用专门的 **[!UICONTROL Update shared audience]** 活动导出受众。

此集成支持两种类型的 Adobe Experience Cloud ID：

* **访客 ID**：此类标识符可协调 Adobe Experience Cloud 访客与 Adobe Campaign 收件人。
* **声明的 ID**：此类型的标识符会使所有类型的数据与 Adobe Campaign 数据库中的元素相协调。它在 Adobe Campaign 中表示为预定义的合并关键项。

  >[!NOTE]
  >
  > 声明的 ID 数据源现在还可以与 People 核心服务集成一起使用。
  >
  >如果您使用People核心服务集成，并想要添加Audience Manager集成，则需要Adobe Audience Manager顾问的帮助，以避免在Adobe Audience Manager上下文中转换为使用此声明的ID数据源时收集的所有ID同步丢失。

请参阅：

[Adobe Audience Manager文档](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=zh-Hans){target="_blank"}

[《Adobe Experience Cloud中央界面组件指南》](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh_Hans){target="_blank"}
