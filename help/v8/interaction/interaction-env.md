---
title: 使用Campaign交互环境
description: 了解如何为Campaign交互创建环境
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# 使用环境{#work-with-environments}

## 实时和设计环境{#live-design-environments}

交互操作有两种类型的选件环境：

* **[!UICONTROL Design]** 优惠环境，其中包含正在编辑且可以更改的优惠。 这些选件尚未经过批准周期，不会发送给联系人。
* **[!UICONTROL Live]** 优惠环境，其中包含向联系人展示的已批准优惠。 此环境中的选件处于只读状态。

![](assets/offer_environments_overview_001.png)

每个 **[!UICONTROL Design]** 环境已链接到 **[!UICONTROL Live]** 环境。 选件完成后，其内容和资格规则需要经过批准周期。 完成此周期后，相关选件将自动部署到 **[!UICONTROL Live]** 环境。 从现在开始，它将可供交付。

默认情况下，Campaign提供 **[!UICONTROL Design]** 环境和 **[!UICONTROL Live]** 链接到它的环境。 这两个环境都已预配置为定位 [内置收件人表](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>要定位收件人表，您需要使用目标映射助手创建环境。 [了解详情](#creating-an-offer-environment)。

![](assets/offer_environments_overview_002.png)

投放经理只能查看 **[!UICONTROL Live]** 环境和利用优惠进行交付。 优惠经理可以查看和使用 **[!UICONTROL Design]** 环境，并查看 **[!UICONTROL Live]** 环境。 [了解详情](interaction-operators.md)

## 为匿名交互创建环境{#create-an-offer-environment}

默认情况下，Campaign附带内置环境以定向收件人表（已识别的选件）。 要定位其他表（例如访问您网站进行入站交互的匿名用户档案），您需要更新配置。

按照下面的步骤进行操作：

1. 浏览至 **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**，右键单击要使用的目标映射，然后选择 **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. 单击 **[!UICONTROL Next]**，选择 **[!UICONTROL Generate a storage schema for propositions]** 选项并单击 **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >如果选项已选中，请取消选中该选项，然后重新选中。

1. Adobe Campaign创建两个环境 —  **[!UICONTROL Design]** 和 **[!UICONTROL Live]**  — 包含之前启用的目标映射中的定位信息。 环境已预先配置了定位信息。

如果您已激活 **[!UICONTROL Visitor]** 映射， **[!UICONTROL Environment dedicated to incoming anonymous interactions]** 框会在环境的 **[!UICONTROL General]** 选项卡。

此选项允许您激活特定于匿名交互的功能，尤其是在配置环境优惠空间时。 您还可以配置相应的选项，以便从“已识别”环境切换到“匿名”环境。

例如，您可以将收件人环境选件空间（已识别的联系人）链接到与访客环境（未识别的联系人）匹配的选件空间。 这样，根据此联系人是否识别，将向联系人提供不同的选件。 有关详细信息，请参见 [创建优惠空间](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>有关入站渠道匿名交互的详细信息，请参阅 [匿名互动](anonymous-interactions.md).
