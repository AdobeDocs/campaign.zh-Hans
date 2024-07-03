---
title: 使用Adobe Campaign配置电子邮件
description: 了解如何在Adobe Campaign中配置电子邮件。
feature: Email
role: User
level: Beginner
exl-id: 36033255-1e75-41c1-9816-126777f7330a
source-git-commit: 2e9c9f8e677233b2906f6ebb8f42dd86afe4e111
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 8%

---

# 配置和发送投放 {#configure-delivery}

访问投放参数以配置更多设置并定义消息发送方式。 您可以定义投放 [优先级](#delivery-priority)，设置 [批次](#sending-using-multiple-waves)，并测试您的投放发送。 完成此配置后，您可以按照中的说明确认发送 [本节](#confirm-delivery). 然后，将立即发送消息或根据投放发送消息 [计划](#schedule-delivery-sending).

## 设置其他参数 {#delivery-additional-parameters}

在发送投放之前，您可以在投放属性中定义发送参数，方法是 **[!UICONTROL Delivery]** 选项卡。

![](assets/delivery-properties-delivery.png)

### 投放优先级 {#delivery-priority}

使用 **[!UICONTROL Delivery priority]** 选项可通过以下方式设置投放的优先级，以更改投放的发送顺序： **[!UICONTROL Very low]** 到 **[!UICONTROL Very high]** (默认值为 **[!UICONTROL Normal]**)。

### 批次数量 {#delivery-batch-quantity}

使用  **[!UICONTROL Message batch quantity]** 用于定义在同一个XML投放包中分组的消息数的选项。 如果参数设置为0，则消息将自动分组。 程序包大小由计算定义 `<delivery size>/1024`，则每个包最少8条消息，最多256条消息。

>[!IMPORTANT]
>
>通过复制现有投放创建投放时，此参数会重置。

### 测试投放发送

使用  **[!UICONTROL Test SMTP delivery]** 用于测试通过SMTP发送的选项。 处理投放直至连接到 SMTP 服务器，但不发送：对于投放的每个收件人，Campaign 连接到 SMTP 提供商服务器，执行 SMTP RCPT TO 命令，并在执行 SMTP DATA 命令之前关闭连接。

>[!NOTE]
>
>* 不得在中间源中设置此选项。
>
>* 在中了解有关SMTP服务器配置的更多信息 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/configure-delivery-settings.html#smtp-relay){target="_blank"}.

## 使用多批次发送 {#sending-using-multiple-waves}

要平衡负荷，您可以将投放分为多个批。 配置批次数量及其相对于整个投放的比例。

### 启用批次 {#enable-waves}

要定义波段，请执行以下步骤：

1. 打开投放属性并浏览到 **[!UICONTROL Delivery]** 选项卡。
1. 启用 **[!UICONTROL Send using multiple waves]** 选项，然后单击 **[!UICONTROL Define waves...]** 链接。

   ![](assets/delivery-define-waves.png)

### 配置批次 {#config-waves}

>[!NOTE]
>
>您只能定义两个连续波形之间的大小和延迟。 无法配置每个波次的收件人选择标准。

您可以定义每个批次的大小，或将其添加到日历中。

* **定义每个波次的大小**. 例如，如果您输入 **[!UICONTROL 30%]** 在相应的字段中，每个波次将代表投放中所包含报文的30%，但最后一条代表10%的报文。

  在 **[!UICONTROL Period]** 字段，指定两个连续批次开始之间的延迟。 例如，如果您输入 **[!UICONTROL 2d]**，第一波立即开始，第二波在两天内开始，第三波在四天内开始，以此类推。

  ![](assets/delivery-waves-size.png)

* **定义发送每个波次的日历**.  例如，第一波表示投放中包含的消息总数的25%，将立即开始。 接下来的两个批次将完成投放，并设置为以六小时间隔开始。

  在 **[!UICONTROL Start]** 列，指定两个连续批次开始之间的延迟。 在 **[!UICONTROL Size]** 列中，输入固定数字或百分比。

  ![](assets/delivery-waves-calendar.png)

### 波动计划检查 {#check-waves}

特定的分类规则， **[!UICONTROL Wave scheduling check]**，确保最后一个波次的计划时间早于投放有效期限。 营销活动类型及其规则，配置于 **[!UICONTROL Typology]** 的选项卡中显示 [本节](../../automation/campaign-opt/campaign-typologies.md#typology-rules)<!--ref TBC-->.

>[!IMPORTANT]
>
>确保最后批次不超过投放截止日期，投放截止日期在中定义 **[!UICONTROL Validity]** 选项卡。 否则，某些消息可能不会发送。 在中了解有关投放有效期的更多信息 [本节](delivery-failures.md#valid-period).
>
>在配置最后批次时，还必须为重试设置足够的时间。 了解有关重试的详细信息 [本节](delivery-failures.md#retries).

### 监测批次 {#monitor-waves}

要监控您的发送，请浏览到投放日志。 请参阅 [此页面](send.md)

您可以看到已在已处理批次中发送的投放(**[!UICONTROL Sent]** 状态)和要在剩余批次中发送的投放(**[!UICONTROL Pending]** 状态)。


### 批次样本 {#samples-waves}

以下两个示例是使用多个批次的最常见用例。

* **启动过程中**

  使用新平台发送电子邮件时，Internet服务提供商(ISP)会怀疑无法识别的IP地址。 如果突然发送大量电子邮件，ISP通常会将其标记为垃圾邮件。

  要避免被标记为垃圾邮件，您可以逐步增加使用批次发送的数量。 这应该可以确保启动阶段的顺利发展，并帮助您降低地址无效的总比率。

  要执行此操作，请使用 **[!UICONTROL Schedule waves according to a calendar]** 选项。 例如，将第一个波次设置为10%，将第二个波次设置为15%，以此类推。

  ![](assets/delivery-waves-ex-ramp-up.png)

* **具有呼叫中心的营销活动**

  通过电话管理忠诚度促销活动时，贵组织处理致电订阅者的能力有限。

  使用批次，您可以将消息数量限制为每天20条，例如，考虑呼叫中心的每日处理能力。

  要执行此操作，请选择 **[!UICONTROL Schedule multiple waves of the same size]** 选项。 输入 **[!UICONTROL 20]** 因为波浪的大小和 **[!UICONTROL 1d]** 在 **[!UICONTROL Period]** 字段。

  ![](assets/delivery-waves-ex-call-center.png)

## 确认投放 {#confirm-delivery}

当投放已配置并准备好发送时，请确保在确认发送之前已运行投放分析。

为此，请执行以下步骤。

1. 单击 **[!UICONTROL Send]**&#x200B;中，选择所需的操作。

   * 要立即发送投放，请选择 [**尽快投放**].
   * 要安排在以后的日期发送，请选择 **[!UICONTROL Postpone the delivery]**. [了解详情](#schedule-delivery-sending)

1. 单击 **[!UICONTROL Analyze]**。有关更多信息，请参阅[此小节](delivery-analysis.md)。

   ![](assets/delivery-send-analyze.png)

1. 完成后，单击 **[!UICONTROL Confirm delivery]** 以启动消息的投放。

   ![](assets/delivery-send-confirm.png)

1. 您可以关闭投放向导，并从以下位置跟踪投放的执行情况 **[!UICONTROL Delivery]** 选项卡，可通过此投放的详细信息或投放列表访问。

   有关更多信息，请参阅以下部分：

   * [监测投放](send.md)
   * [了解投放失败](delivery-failures.md)

<!--About message tracking-->

## 安排发送投放 {#schedule-delivery-sending}

您可以推迟邮件的投放，以便计划内容的投放或管理销售压力并避免过度营销。

1. 单击 **[!UICONTROL Send]** 按钮并选择 **[!UICONTROL Postpone delivery]** 选项。

1. 在中指定开始日期 **[!UICONTROL Contact date]** 字段。

   ![](assets/delivery-send-postpone.png)

1. 开始投放分析并确认投放发送。 但是，直到中给定的日期才会开始投放发送 **[!UICONTROL Contact date]** 字段。

   >[!IMPORTANT]
   >
   >开始分析后，您定义的联系日期即是固定的。 如果修改此日期，则必须重新启动分析，以便考虑所做的修改。

   ![](assets/delivery-send-scheduled.png)

在投放列表中，投放将与 **[!UICONTROL Pending]** 状态。

您还可以通过在上游配置计划 **[!UICONTROL Scheduling]** 投放的按钮。

![](assets/delivery-scheduling-button.png)

这样，您可以将投放推迟到以后的日期，或将投放保存在临时日程表中。

* 此 **[!UICONTROL Schedule delivery (no automatic execution)]** 选项允许您计划投放的临时分析。

  保存此配置后，投放将更改为 **[!UICONTROL Targeting pending]** 状态。 分析将在指定的日期启动。

* 此 **[!UICONTROL Schedule delivery (automatic execution on planned date)]** 选项可让您指定提交日期。

  单击 **[!UICONTROL Send]** 并选择 **[!UICONTROL Postpone delivery]** 然后启动分析并确认投放。 分析完成后，投放目标已准备就绪，并在指定日期自动发送消息。

日期和时间以当前运算符的时区表示。 此 **[!UICONTROL Time zone]** 通过位于联系日期输入字段下方的下拉列表，您可以将输入的日期和时间自动转换为所选时区。

例如，如果您安排在伦敦时间8点自动执行投放，则该时间将自动转换为所选时区：

![](assets/delivery-schedule-time-zone.png)

<!--
## Adjust delivery failure management {#delivery-failure-management}

### Configure retries {#configure-retries}

Temporarily undelivered messages due to a **Soft** or **Ignored** error are subject to an automatic retry. The delivery failure types and reasons are presented in this [section](../../delivery/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

>[!IMPORTANT]
>
>For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the retry settings in the delivery are no longer used by Campaign. Soft bounce retries and the length of time between them are determined by the Enhanced MTA based on the type and severity of the bounce responses coming back from the message's email domain.

For on-premise installations and hosted/hybrid installations using the legacy Campaign MTA, the central section of the **[!UICONTROL Delivery]** tab for delivery parameters indicates how many retries should be performed the day after the delivery and the minimum delay between retries.

![](assets/s_ncs_user_wizard_retry_param.png)

By default, five retries are scheduled for the first day of the delivery with a minimum interval of one hour spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Validity]** tab (see [Defining validity period](#defining-validity-period)).

### Define the validity period {#define-validity-period}

When the delivery has been launched, the messages (and any retries) can be sent until the delivery deadline. This is indicated in the delivery properties, via the **[!UICONTROL Validity]** tab.

![](assets/s_ncs_user_email_del_valid_period.png)

* The **[!UICONTROL Delivery duration]** field lets you enter the limit for global delivery retries. This means that Adobe Campaign sends the messages beginning on the start date, and then, for messages returning an error only, regular, configurable retries are performed until the validity limit is reached.

  You can also choose to specify dates. To do this, select **[!UICONTROL Explicitly set validity dates]**. In this case, the delivery and validity limit dates also let you specify the time. The current time is used by default, but you can modify this directly in the input field.

  >[!IMPORTANT]
  >
  >For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the **[!UICONTROL Delivery duration]** setting in your Campaign email deliveries will be used only if set to **3.5 days or less**. If you define a value higher than 3.5 days, it will not be taken into account.

* **Validity limit of resources**: The **[!UICONTROL Validity limit]** field is used for uploaded resources, mainly for the mirror page and images. The resources on this page are valid for a limited time (to save disk space).

  The values in this field can be expressed in the units listed in [this section](../../platform/using/adobe-campaign-workspace.md#default-units).
-->
