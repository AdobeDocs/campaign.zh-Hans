---
solution: Campaign
product: Adobe Campaign
title: 活动 Interaction运算符
description: 创建优惠管理运营商
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# 实时和设计环境{#live-design-environments}

交互操作有两种类型的优惠环境:

* **[!UICONTROL Design]** 优惠环境，包括正在编辑且可以更改的优惠。这些优惠尚未通过审批周期，也未送达联系人。
* **[!UICONTROL Live]** 优惠环境，在向联系人显示批准的优惠时，包括这些。此环境中的优惠为只读。

![](assets/offer_environments_overview_001.png)

每个&#x200B;**[!UICONTROL Design]**&#x200B;环境都链接到&#x200B;**[!UICONTROL Live]**&#x200B;环境。 优惠完成后，其内容和合格规则将受到批准周期的约束。 完成此周期后，相关优惠将自动部署到&#x200B;**[!UICONTROL Live]**&#x200B;环境。 从现在开始，它将可用于投放。

默认情况下，活动附带一个&#x200B;**[!UICONTROL Design]**&#x200B;环境和一个链接到它的&#x200B;**[!UICONTROL Live]**&#x200B;环境。 这两个环境都预配置为目标[内置收件人表](../dev/datamodel.md#ootb-profiles)。

>[!NOTE]
>
>要目标收件人表，您需要使用目标映射助手创建环境。 [了解详情](#creating-an-offer-environment)。

![](assets/offer_environments_overview_002.png)

投放管理者只能视图&#x200B;**[!UICONTROL Live]**&#x200B;环境并利用优惠来提供。 优惠管理器可以视图和使用&#x200B;**[!UICONTROL Design]**&#x200B;环境，并视图&#x200B;**[!UICONTROL Live]**&#x200B;环境。 [了解详情](interaction-operators.md)。

## 创建优惠环境{#creating-an-offer-environment}

默认情况下，活动附带一个内置环境，用于目标收件人表(已标识优惠)。 要目标其他表，请执行以下步骤：

1. 浏览到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Delivery mappings]** ，右键单击要使用的投放映射并选择&#x200B;**[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**。

   ![](assets/offer_env_anonymous_001.png)

1. 单击&#x200B;**[!UICONTROL Next]**，选择&#x200B;**[!UICONTROL Generate a storage schema for propositions]**&#x200B;选项，然后单击&#x200B;**[!UICONTROL Save]**。

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >如果选中了该选项，请取消选中它，然后重新选中它。

1. Adobe Campaign创建了两个环境- **[!UICONTROL Design]**&#x200B;和&#x200B;**[!UICONTROL Live]** — 其中包含先前启用的目标映射中的定位信息。 环境预配置了定位信息。
