---
product: Adobe Campaign
title: Campaign互动运算符
description: 创建选件管理运算符
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# 实时环境和设计环境{#live-design-environments}

交互可与两种类型的选件环境进行操作：

* **[!UICONTROL Design]** 包含正在编辑且可更改的选件的选件环境。这些选件尚未通过批准周期，也未交付给联系人。
* **[!UICONTROL Live]** 在向联系人显示已批准选件时包含这些选件的选件环境。此环境中的选件为只读选件。

![](assets/offer_environments_overview_001.png)

每个&#x200B;**[!UICONTROL Design]**&#x200B;环境均链接到&#x200B;**[!UICONTROL Live]**&#x200B;环境。 选件完成后，其内容和资格规则将受到批准周期的约束。 完成此周期后，相关选件会自动部署到&#x200B;**[!UICONTROL Live]**&#x200B;环境。 从此刻起，它将可供投放。

默认情况下，Campaign附带一个&#x200B;**[!UICONTROL Design]**&#x200B;环境和一个与之关联的&#x200B;**[!UICONTROL Live]**&#x200B;环境。 这两个环境都已预配置为定向[内置收件人表](../dev/datamodel.md#ootb-profiles)。

>[!NOTE]
>
>要定位收件人表，您需要使用目标映射助手创建环境。 [了解详情](#creating-an-offer-environment)。

![](assets/offer_environments_overview_002.png)

投放管理器只能查看&#x200B;**[!UICONTROL Live]**&#x200B;环境并利用选件进行投放。 选件管理器可以查看和使用&#x200B;**[!UICONTROL Design]**&#x200B;环境，并查看&#x200B;**[!UICONTROL Live]**&#x200B;环境。 [了解详情](interaction-operators.md)

## 创建选件环境{#creating-an-offer-environment}

默认情况下，Campaign附带一个内置环境，用于定位收件人表（已识别的选件）。 要定位另一个表，请执行以下步骤：

1. 浏览到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**，右键单击要使用的目标映射，然后选择&#x200B;**[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**。

   ![](assets/offer_env_anonymous_001.png)

1. 单击&#x200B;**[!UICONTROL Next]**，选择&#x200B;**[!UICONTROL Generate a storage schema for propositions]**&#x200B;选项，然后单击&#x200B;**[!UICONTROL Save]**。

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >如果选项已选中，请取消选中它，然后重新选中它。

1. Adobe Campaign创建两个环境 — **[!UICONTROL Design]**&#x200B;和&#x200B;**[!UICONTROL Live]** — 其中包含先前启用的目标映射中的定位信息。 环境已预配置了定位信息。
