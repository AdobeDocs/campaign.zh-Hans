---
title: Campaign互动运算符
description: 创建选件管理运算符
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: c19ac91fe7b4b825f75ec096320efabc3e78328c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 2%

---

# 使用环境{#work-with-environments}

## 实时环境和设计环境{#live-design-environments}

交互可与两种类型的选件环境进行操作：

* **[!UICONTROL Design]** 包含正在编辑且可更改的选件的选件环境。 这些选件尚未通过批准周期，也未交付给联系人。
* **[!UICONTROL Live]** 在向联系人显示已批准选件时包含这些选件的选件环境。 此环境中的选件为只读选件。

![](assets/offer_environments_overview_001.png)

每个 **[!UICONTROL Design]** 环境已链接到 **[!UICONTROL Live]** 环境。 选件完成后，其内容和资格规则将受到批准周期的约束。 完成此周期后，相关选件会自动部署到 **[!UICONTROL Live]** 环境。 从此刻起，它将可供投放。

默认情况下，Campaign提供 **[!UICONTROL Design]** 环境和 **[!UICONTROL Live]** 链接到该环境。 这两个环境都已预配置为定位 [内置收件人表](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>要定位收件人表，您需要使用目标映射助手创建环境。 [了解详情](#creating-an-offer-environment)。

![](assets/offer_environments_overview_002.png)

投放管理器只能查看 **[!UICONTROL Live]** 并利用优惠来提供它们。 选件管理器可以查看和使用 **[!UICONTROL Design]** 环境，并查看 **[!UICONTROL Live]** 环境。 [了解详情](interaction-operators.md)

## 为匿名交互创建环境{#create-an-offer-environment}

默认情况下，Campaign附带一个内置环境，用于定位收件人表（已识别的选件）。 要定位其他表（如访问网站进行集客交互的匿名用户档案），您需要更新配置。

按照下面的步骤进行操作：

1. 浏览到 **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**，右键单击要使用的目标映射并选择 **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. 单击 **[!UICONTROL Next]**，选择 **[!UICONTROL Generate a storage schema for propositions]** 选项并单击 **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >如果选项已选中，请取消选中它，然后重新选中它。

1. Adobe Campaign创建两个环境 —  **[!UICONTROL Design]** 和 **[!UICONTROL Live]**  — 包含先前启用的目标映射中的目标信息。 环境已预配置了定位信息。

如果已激活 **[!UICONTROL Visitor]** 映射， **[!UICONTROL Environment dedicated to incoming anonymous interactions]** 框中，此复选框将被自动选中 **[!UICONTROL General]** 选项卡。

利用此选项，可激活特定于匿名交互的函数，尤其是在配置环境选件空间时。 您还可以配置选项，以便从“已识别”环境切换到“匿名”环境。

例如，您可以将收件人环境选件空间（已识别的联系人）与与访客环境（未识别的联系人）匹配的选件空间链接起来。 这样，联系人就可以获得不同的选件，具体取决于此联系人是否被识别。 有关更多信息，请参阅 [创建优惠空间](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>有关入站渠道上匿名交互的更多信息，请参阅 [匿名互动](anonymous-interactions.md).
