---
product: campaign
title: 投放控制
description: 了解有关投放控制工作流活动的更多信息
feature: Workflows
role: User
exl-id: 09fe638d-5e1c-49d1-9196-6300c1e56703
source-git-commit: e0dbeb7402a46f76a26c28dd226bc069d52f2609
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 5%

---

# 投放控制{#delivery-control}

**投放控制**&#x200B;类型的操作允许您启动、暂停或停止投放。

这可以是过渡中指定的投放、显式选择的投放或由脚本计算的投放。 有关详情，请参阅[投放](delivery.md)。

![](assets/edit_diffusion_act.png)

如果选择&#x200B;**[!UICONTROL Start]**，活动将执行启动投放所需的所有步骤（目标计算、内容准备、投放）。 如果上一工作流活动已经执行了其中的某些步骤，则将不再执行它们。 例如，如果目标估计已由&#x200B;**[!UICONTROL Delivery]**&#x200B;类型活动（请参阅[投放](delivery.md)）执行，**[!UICONTROL Act on the delivery]**&#x200B;活动将启动剩余步骤（内容准备和投放）。

可以使用以下选项：

* **[!UICONTROL Generate an outbound transition]**

  创建将在执行结束时激活的叫客过渡。 您可以选择是否检索出站投放的目标。

* **[!UICONTROL Processing errors]**

  请参阅[处理错误](monitor-workflow-execution.md#processing-errors)。

## 输入参数 {#input-parameters}

* deliveryId

  投放标识符（如果所选操作为&#x200B;**[!UICONTROL Specified in the transition]**）。
