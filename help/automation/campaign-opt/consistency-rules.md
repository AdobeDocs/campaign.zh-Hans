---
product: campaign
title: 一致性规则
description: 一致性规则
feature: Typology Rules
version: Campaign v8, Campaign Classic v7
exl-id: dcb4ffcf-71e5-48a2-b0f7-42915a599652
TQID: 'https://experienceleague.adobe.com/KaybpQFNgtTiMgQOWX0-bNqPEMeWGWR8vb6qjZzr63k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: e5fb657f-3c0a-4fcc-9980-3589a23ab4de
    internal-label: Typology rules
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%
---
# 一致性规则{#consistency-rules}

Adobe Campaign通过营销活动类型中包含的一组规则，确保通信的连续性。 其目的是控制发送给收件人的投放，如数量、性质、相关性等。

例如，**容量**&#x200B;规则可以避免消息投放所关注的平台过载。 例如，包含下载链接的特殊优惠不得同时发送给太多人，以免服务器饱和；电话营销活动不得超出呼叫中心的处理能力等。

## 控制能力 {#control-capacity}

在投放消息之前，您需要确保您的组织具有处理投放的能力（物理基础架构）、投放可能生成的响应（入站消息）以及要联系订阅者的呼叫次数（呼叫中心处理能力），例如。

为此，请创建&#x200B;**[!UICONTROL Capacity]**&#x200B;分类规则。

在以下示例中，我们通过电话为忠诚度营销活动创建分类规则。 我们将消息数量限制为每天20条，即呼叫中心的每日处理能力。 将规则应用于两个投放后，我们可以通过日志监控使用情况。

要设计新容量规则，请执行以下步骤：

1. 在&#x200B;**[!UICONTROL Administration > Campaign management > Typology management > Typology rules]**&#x200B;文件夹下，单击&#x200B;**[!UICONTROL New]**。
1. Select **[!UICONTROL Capacity]**&#x200B;规则类型。

   ![类型规则创建屏幕，在“规则类型”下拉列表中选择“容量”选项。](assets/campaign_opt_create_capacity_01.png)

1. 在&#x200B;**[!UICONTROL Capacity]**&#x200B;选项卡中，创建可用性行：在我们的示例中，这些是可进行调用的时间段。 Select提供24小时的期限，并在初始数量中输入150，这意味着呼叫中心每天可以处理150次呼叫。

   ![带有“编辑可用性行”对话框的“容量”选项卡，用于输入开始、结束和初始数量。](assets/campaign_opt_create_capacity_02.png)

   >[!NOTE]
   >
   >可用性行仅供参考。 如果达到容量限制时需要排除邮件，请参阅[达到容量限制时排除邮件](#exclude-messages-when-capacity-limit-reached)。

1. 将此规则与分类关联，然后将该分类引用到您的投放以应用此容量规则。 有关详细信息，请参阅[将分类应用于投放](apply-rules.md#apply-a-typology-to-a-delivery)。
1. 您可以从规则&#x200B;**[!UICONTROL Consumptions]**&#x200B;和&#x200B;**[!UICONTROL Capacity]**&#x200B;选项卡中监视消耗。

   在投放中使用规则时，**[!UICONTROL Consumed]**&#x200B;和&#x200B;**[!UICONTROL Remaining]**&#x200B;列提供有关加载的信息，如下所示：

   ![容量选项卡，显示具有150个初始数量、200个已冲减量和–50个剩余量的可用性行。](assets/campaign_opt_create_capacity_03.png)

   如需详细信息，请参阅[此小节](#monitor-consumption)。

## 定义最大负载 {#define-the-maximum-load}

要定义最大负荷，您需要定义可用性行。 为此，有两个可用选项：您可以手动[创建一个或多个可用性行](#add-availability-lines-one-by-one)或创建可用性范围。 可以自动设置这些时间段的频率。 [了解详情](#add-a-set-of-availability-lines)。

### 逐一添加可用性行 {#add-availability-lines-one-by-one}

要创建可用性行，请单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮并选择&#x200B;**[!UICONTROL Add an availability line]**。 输入可用性期间和可用负荷。

![从“添加”按钮打开了“编辑可用性行”对话框，其中包含“开始”、“结束”和“初始数量”字段。](assets/campaign_opt_create_capacity_02.png)

根据需要添加任意数量的行以适合您的处理能力。

### 添加一组可用性行 {#add-a-set-of-availability-lines}

要定义给定时间的可用时段，请单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮并选择&#x200B;**[!UICONTROL Add a set of availability lines]**&#x200B;选项。 指示每个时段的持续时间以及要创建的期间数。

要自动设置页面创建频率，请单击&#x200B;**[!UICONTROL Change]**&#x200B;按钮并定义时间段计划。

![使用“添加一组选定的可用性行”和“更改计划”按钮编辑可用性行对话框。](assets/campaign_opt_create_capacity_07.png)

例如，我们定义一个时间表，为所有工作日创建可用性时段，在上午9点到下午5点之间，每小时接听10次呼叫。 要执行此操作，请应用以下步骤：

1. Select的周期类型以及有效日期和时间：

   ![计划编辑向导“有效期”页，其中包含从日历中选择的有效开始日期和有效结束日期。](assets/campaign_opt_create_capacity_08.png)

1. 指示有效日期：

   ![计划编辑向导“有效期”页，其中从日历中挑选了结束有效日期。](assets/campaign_opt_create_capacity_09.png)

1. 在批准计划之前检查计划：

   ![计划编辑向导“摘要”页面，其中包含计划说明和完成前的启动时间列表。](assets/campaign_opt_create_capacity_10.png)

**[!UICONTROL Forecasting]**&#x200B;工作流会自动创建所有匹配的行。

呼叫中心规则的![容量选项卡，其中列出了计划自动创建的可用性行。](assets/campaign_opt_create_capacity_12.png)

>[!NOTE]
>
>我们建议通过文件导入创建可用性行。 通过此选项卡，可以查看和检查消耗行。

## 达到容量限制时排除消息 {#exclude-messages-when-capacity-limit-reached}

可用性行仅供参考。 要排除超出的消息，请选中&#x200B;**[!UICONTROL Exclude from the target messages in excess of capacity]**&#x200B;选项。 这样可防止超出容量。 对于与上例相同的人口，冲减和剩余能力不能超过初始数量：

![容量选项卡，从超过所选容量的目标邮件中排除：已使用100，剩余50。](assets/campaign_opt_create_capacity_04.png)

可处理的最大消息数在定义的可用性范围内平均细分。 这尤其与呼叫中心相关，因为它们每天的最大呼叫数是有限的。 对于电子邮件投放，**[!UICONTROL Do not limit instantaneous delivery capacity]**&#x200B;选项允许您忽略此可用性范围，同时发送电子邮件。

![已选择“不限制即时投放容量”的“容量”选项卡，显示150个已用容量和0个剩余容量。](assets/campaign_opt_create_capacity_05.png)

>[!NOTE]
>
>在过载的情况下，将根据投放属性中定义的公式选择已保存的消息。

![具有容量设置的“传递属性”的“类型”选项卡：呼叫中心渠道容量和重要性公式。](assets/campaign_opt_create_capacity_06.png)

## 监测消耗 {#monitoring-consumption}

默认情况下，容量规则仅用于指示用途。 Select的&#x200B;**[!UICONTROL Exclude messages in excess of capacity from the target]**&#x200B;选项可防止超出定义的负载。 在这种情况下，使用此分类规则将自动从投放中排除多余的消息。

要监视使用，请查看类型规则中&#x200B;**[!UICONTROL Capacity]**&#x200B;选项卡的&#x200B;**[!UICONTROL Consumed]**&#x200B;列中显示的值。

![已选择排除选项的“容量”选项卡，显示150个初始数量中的100个已用和50个剩余数量。](assets/campaign_opt_create_capacity_04.png)

要查看消耗行，请单击规则中的&#x200B;**[!UICONTROL Consumptions]**&#x200B;选项卡。
