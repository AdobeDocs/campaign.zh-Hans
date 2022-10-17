---
title: 与Adobe Experience Cloud解决方案共享受众
description: 了解如何使用Adobe Experience Cloud解决方案共享受众
feature: Subscriptions
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ec46a6f41d640b11306a88d6a966f81f8c2e43e0
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 5%

---

# 与Adobe Experience Cloud解决方案共享受众{#shared-audiences}


选项1:AEP源和目标

选项2:Adobe人员/AAM

您可以集成 **Adobe Campaign** with **People核心服务** 或Adobe Audience Manager。 然后，您将能够：

* 将不同Adobe Experience Cloud解决方案中的共享受众/区段导入Adobe Campaign。 受众可通过Adobe Campaign中的列表导入。

* 以Adobe Experience Cloud共享受众的形式导出列表。 这些受众可在您使用的不同Adobe Experience Cloud解决方案中使用。 可在工作流中使用专用的 **[!UICONTROL Update shared audience]** 活动。

此集成支持两种类型的Adobe Experience Cloud ID:

* **访客ID**:此类标识符可协调Adobe Experience Cloud访客与Adobe Campaign收件人。
* **声明的ID**:此类型的标识符将所有类型的数据与Adobe Campaign数据库中的元素进行协调。 它在Adobe Campaign中表示为预定义的对帐密钥。

   >[!NOTE]
   >
   > Declared ID 数据源现在还可以与 People 核心服务集成一起使用。
   >
   >如果您使用“人员”核心服务集成并想要添加Audience Manager集成，则需要Adobe Audience Manager顾问的帮助，以避免在Adobe Audience Manager上下文中转换到使用此声明的ID数据源时收集的所有ID同步丢失。

参阅:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en)
