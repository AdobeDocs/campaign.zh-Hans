---
title: 使用 Adobe Experience Cloud 解决方案共享受众
description: 了解如何使用 Adobe Experience Cloud 解决方案共享受众
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 75%
---
# 使用 Adobe Experience Cloud 解决方案共享受众{#shared-audiences}

选项 1：AEP 源和目标

选项 2：Adobe People/AAM

您可以将 **Adobe Campaign** 与 **People 核心服务** 或 Adobe Audience Manager 集成。 然后，您将能够：

* 从不同的 Adobe Experience Cloud 解决方案导入共享受众/区段到 Adobe Campaign 中。 可通过 Adobe Campaign 中的列表导入受众。

* 以 Adobe Experience Cloud 共享受众的形式导出列表。 您可在所用的不同 Adobe Experience Cloud 解决方案中使用这些受众。 在工作流中完成定位后，可使用专门的 **[!UICONTROL Update shared audience]** 活动导出受众。

此集成支持两种类型的 Adobe Experience Cloud ID：

* **访客 ID**：此标识符可使 Adobe Experience Cloud 访客与 Adobe Campaign 收件人相协调。
* **声明的 ID**：此标识符可使所有类型的数据与 Adobe Campaign 数据库中的元素相协调。 它是 Adobe Campaign 中的预定义合并关键项。

  >[!NOTE]
  >
  > “声明的 ID”数据源还可以与 People 核心服务集成一起使用。
  >
  >如果您使用People核心服务集成，并且想要添加Audience Manager集成，则需要Adobe Audience Manager顾问的帮助，以避免在Adobe Audience Manager上下文中转换为使用此声明的ID数据源时收集的所有ID同步丢失。

请参阅：

[Adobe Audience Manager知识库](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=zh-Hans){target="_blank"}。

[Adobe Experience Cloud中央界面组件指南](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh_Hans){target="_blank"}。
