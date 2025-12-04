---
title: Adobe Campaign内置投放报告
description: Adobe Campaign内置投放报告
feature: Reporting
exl-id: e9031d65-6e0e-49da-9990-7687d2a77591
source-git-commit: 3453820bb0eca7847ec55d7e6ea15766a57ab94e
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 10%

---

# 投放报告 {#delivery-reports}

您可以通过可从投放概述访问的各种报告来跟踪投放的执行情况。

要访问报表，请执行以下步骤：

1. 浏览到&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡并单击&#x200B;**[!UICONTROL Delivery]**&#x200B;链接以显示投放列表。
1. 单击要访问报告的投放名称。
1. 选择&#x200B;**[!UICONTROL Summary]**&#x200B;选项卡并单击&#x200B;**[!UICONTROL Reports]**&#x200B;链接以访问特定于投放的报告。

   ![](assets/detailed-report-2.png)

   默认情况下，可以使用以下报表：

   * **[!UICONTROL Delivery throughput]**
   * **[!UICONTROL Sharing to social networks]**
   * **[!UICONTROL Statistics on sharing activities]**
   * **[!UICONTROL Hot clicks]**
   * **[!UICONTROL Tracking statistics]**
   * **[!UICONTROL URLs and click streams]**
   * **[!UICONTROL Tracking indicators]**
   * **[!UICONTROL Non-deliverables and bounces]**
   * **[!UICONTROL User activities]**
   * **[!UICONTROL Delivery summary]**
   * **[!UICONTROL Subscription tracking]**
   * **[!UICONTROL Delivery statistics]**
   * **[!UICONTROL Breakdown of opens]**

## 跟踪指标 {#tracking-indicators}

此报表将用于在接收投放时跟踪收件人行为的关键指标组合在一起。 它提供投放和接收统计信息、打开率和点进率、生成的点击流，以及分享活动到社交网络。

>[!NOTE]
>
>根据消息打开次数计算的值始终为估计值，这是因为文本格式中链接至电子邮件的错误边距。 **[!UICONTROL Distinct opens/Sum of opens for the population reached]**&#x200B;指标考虑此错误边距。 [了解详情](metrics-calculation.md#tracking-opens-)。

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]**：传递分析后要传递的邮件总数。
* **[!UICONTROL Success]**：已成功处理的邮件数。

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>相关百分比是根据成功转发的邮件数来计算的。

* **[!UICONTROL Distinct opens for the population reached]**：估计至少已打开邮件一次的目标收件人的数量。 由于必须打开电子邮件才能单击链接，因此会考虑对跟踪URL的点击量。
* **[!UICONTROL Sum of opens for the population reached]**：目标收件人打开总数的估计值。
* **[!UICONTROL Clicks on opt-out link]**：取消订阅链接的点击次数。
* **[!UICONTROL Clicks on the mirror page link]**：指向[镜像页面](../send/mirror-page.md)的链接的点击次数。 要将其考虑在内，必须在投放向导（跟踪的URL）中定义链接。
* **[!UICONTROL Estimation of forwards]**：目标收件人转发的电子邮件数量的估计。 此值计算方式为减去点击电子邮件的不同人员的数量和不同收件人的数量。

  >[!NOTE]
  >
  >有关不同人员和目标收件人之间差异的更多信息，请参阅[目标人员/收件人](metrics-calculation.md#targeted-persons---recipients)。

**[!UICONTROL 3. Open and click-through rate]**

此值表显示每个Internet域的投放、打开次数、点击次数和原始反应性的细分。 使用以下指示器：

* **[!UICONTROL Sent]**：在此域上发送的邮件总数。
* **[!UICONTROL Complaints]**：此域被收件人报告为不受欢迎的邮件数。 根据此域上发送的消息总数来计算速率。
* **[!UICONTROL Opens]**：此域中至少打开过一次邮件的不同目标收件人的数量。 根据此域上发送的消息总数来计算速率。
* **[!UICONTROL Clicks]**：在同一个投放中至少点击过一次的不同目标收件人的数量。 根据此域上发送的消息总数来计算速率
* **[!UICONTROL Raw reactivity]**：与至少打开一次投放的收件人人数相比，至少点击一次投放的收件人人数的百分比。

>[!NOTE]
>
>此报告中显示的域名在多维数据集级别使用的明细列表中定义。 要更改、添加或删除默认域，请编辑&#x200B;**[!UICONTROL Domains]**&#x200B;明细列表并修改值和别名。 **[!UICONTROL Others]**&#x200B;类别包括不属于明细列表任何值的域名。
>
>在[此页面](../config/enumerations.md)中了解如何访问和配置枚举。


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>相关百分比是根据成功转发的邮件数来计算的。

* **[!UICONTROL Distinct clicks for the population reached]**：在投放中至少单击一次的不同人员的数量。
* **[!UICONTROL Cumulated clicks]**：目标收件人的总点击次数，不包括退订链接和镜像页面。
* **[!UICONTROL Recipient clicks]**：在同一个投放中至少点击过一次的不同目标收件人的数量。
* **[!UICONTROL Estimated recipient reactivity]**：在投放中至少点击一次的收件人数量与至少打开投放一次的预计收件人数量的比率。 选择退出和镜像页面链接的点击次数不包含在内。
<!--
**[!UICONTROL 5. Web tracking]**

* **[!UICONTROL Visited pages]**: Number of web pages visited following message reception.
* **[!UICONTROL Transactions]**: Number of purchases following message reception.
* **[!UICONTROL Total amount]**: Total amount of purchases following message reception. 
* **[!UICONTROL Average transaction amount]**: Average purchase made by distinct delivery recipients. 
* **[!UICONTROL Articles]**: Number of articles purchased by the delivery recipients. 
* **[!UICONTROL Average count of articles per transaction]**: Average number of items per purchase made by distinct recipients.
* **[!UICONTROL Average amount per message]**: Average amount of purchases generated per message.

  >[!NOTE]
  >
  >In order for a visited page, transaction, amount or article to be taken into account, a webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).

**[!UICONTROL 6. Sharing activities to email and social networks]**

This section shows the number of messages shared on each social network. For more on this, refer to [Sharing to social networks](../../reporting/using/global-reports.md#sharing-to-social-networks).

## URLs and click streams {#urls-and-click-streams}

This report shows the list of pages visited following a delivery. 

![](assets/s_ncs_user_url_report.png)

You can configure the contents of this report by selecting: the score chart to be displayed, the time filter (since the action launch, over the first 6 hours following launch, etc.) and the data display mode (by label, by URL, by category. Click **[!UICONTROL Refresh]** to confirm your selection.

The following rates are displayed in the upper section of the report:

* **[!UICONTROL Reactivity]**: Ratio of the number of targeted recipients having clicked in a delivery, in relation to the estimated number of targeted recipients having opened a delivery. Clicks on the opt-out link and on the mirror page are not taken into account.

  >[!NOTE]
  >
  >For more information on tracking opens, refer to [this section](metrics-calculation.md#tracking-opens-).

* **[!UICONTROL Distinct clicks]**: Number of distinct people having clicked at least once (excluding unsubscription link and mirror page) in a delivery. The rate displayed is calculated based on the number of messages delivered successfully. 
* **[!UICONTROL Cumulated clicks]**: Total number of clicks by targeted recipients (excluding unsubscription link and mirror page). The rate displayed is calculated based on the number of messages forwarded successfully.

**[!UICONTROL Platform average]**: This average rate, displayed under each rate (reactivity, distinct clicks, and cumulated clicks), is calculated for deliveries sent over the previous six months. Only deliveries with the same typology and on the same channel are taken into account. Proofs are excluded.

The central table provides the following information:

* **[!UICONTROL Clicks]**: Number of cumulated clicks, per link. 
* **[!UICONTROL Clicks (in %)]**: Breakdown of the number of clicks per link, in relation to the total number of cumulated clicks.

**[!UICONTROL Breakdown of clicks in time]**

This chart shows the breakdown of cumulated clicks per day.
-->

## 投放摘要 {#delivery-summary}

此报表提供有关投放的所有主要信息。

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

此部分包含两个指标：

* **[!UICONTROL Initial population]**：投放所定向的收件人总数。
* **[!UICONTROL Messages rejected by the rule]**：应用分类规则时在分析期间忽略的地址数：地址缺失、隔离、列入阻止列表等。<!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

中间图表显示分析期间拒绝的消息按规则细分。

**[!UICONTROL Delivery statistics]**

本节包括以下指标：

* **[!UICONTROL Messages to be delivered]**：传递分析后要传递的邮件总数。
* **[!UICONTROL Success]**：已成功处理的邮件数。 关联比率是与要投放的消息数量的比率。
* **[!UICONTROL Errors]**：投放和自动回弹处理期间累计的错误总数。 关联比率是与要投放的消息数量的比率。
* **[!UICONTROL New quarantines]**：投放失败（用户未知，域无效）后隔离的地址数。 关联比率是与要投放的消息数量的比率。

## 热门点击 {#hot-clicks}

此报告显示邮件内容（HTML 和/或文本）以及每个链接的点击百分比。个性化块退订链接、镜像页面链接和产品建议链接将计入总累计点击次数，但不会显示在报告中。

>[!NOTE]
>
>如果您的投放包含选件（交互），则报表上方部分会显示一个框，其中显示了对选件点击的百分比。


## 跟踪统计数据 {#tracking-statistics}

此报表提供有关打开、点击和交易的统计数据。

通过它，您可以跟踪投放的营销影响。 您可以通过更改时间刻度（1小时、3小时或24小时视图等）来配置值的显示方式。 单击&#x200B;**[!UICONTROL Refresh]**&#x200B;确认您的选择。

此报告提供了一个值表和一个排列图，其中显示投放达到最大效率所需的时间。 使用以下指示器：

* **[!UICONTROL Opens]**：估计达到打开邮件总数百分比所需的时间。 不考虑文本格式的电子邮件。 [了解详情](metrics-calculation.md#tracking-opens-)。
* **[!UICONTROL Clicks]**：估计达到所记录点击总数百分比所需的时间。 选择退出链接和镜像页面的点击次数不会考虑在内。
<!--
* **[!UICONTROL Transactions]**: Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->


## 累积报告 {#cumulated-reports}

您可以显示投放的累积报告。 要实现此目的，请选择要比较的投放，以获取这些投放的报告列表。

要从列表中选择不相邻的投放，请在进行选择时按住CTRL键。

要选择保存在其他文件夹中的投放，请单击工具栏中的&#x200B;**[!UICONTROL Display sub-levels]**&#x200B;图标。 然后，它们将显示在同一列表中。
