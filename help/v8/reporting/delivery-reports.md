---
title: Adobe Campaign内置投放报告
description: Adobe Campaign内置投放报告
feature: Reporting
source-git-commit: 60db4c2e8cd280845ddd0176bd10dc1b7edbb767
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 2%

---


# 投放报告 {#delivery-reports}

您可以通过从投放概述访问的各种报表来跟踪投放的执行情况。

要访问报表，请执行以下步骤：

1. 浏览到 **[!UICONTROL Campaigns]** ，然后单击 **[!UICONTROL Delivery]** 链接以显示投放列表。
1. 单击要访问的报表的投放名称。
1. 选择 **[!UICONTROL Summary]** ，然后单击 **[!UICONTROL Reports]** 链接以访问特定于投放的报表。

   ![](assets/detailed-report-2.png)

   默认情况下，可使用以下报表：

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

此报表整合了用于跟踪收件人在收到投放时的行为的关键指标。 它提供了对投放和接收统计信息、打开和点进率、生成的点击流、Web跟踪以及将活动共享到社交网络的访问权限。

>[!NOTE]
>
>根据消息打开次数计算的值始终是预估值，因为链接到文本格式电子邮件的误差范围。 的 **[!UICONTROL Distinct opens/Sum of opens for the population reached]** 指标考虑此误差范围。 [了解详情](metrics-calculation.md#tracking-opens-)。

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]** :投放分析后要投放的邮件总数。
* **[!UICONTROL Success]** : 成功处理的消息数.

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>相关百分比是根据成功转发的消息数量计算的。

* **[!UICONTROL Distinct opens for the population reached]** :至少一次打开消息的目标收件人数目的估计。 由于必须打开电子邮件才能单击链接，因此会考虑对跟踪URL的点击。
* **[!UICONTROL Sum of opens for the population reached]** :目标收件人的打开总数估计。
* **[!UICONTROL Clicks on opt-out link]** :退订链接的点击次数。
* **[!UICONTROL Clicks on the mirror page link]** :点击指向镜像页面的链接的次数。 要考虑这一点，必须在投放向导（跟踪的URL）中将链接定义为相同的链接。 <!--Refer to this [page](../../delivery/using/about-delivery-monitoring.md).-->
* **[!UICONTROL Estimation of forwards]** :目标收件人转发的电子邮件数量的估计。 此值的计算方式是减去在电子邮件中点击的不同人员数量和不同收件人的数量。

   >[!NOTE]
   >
   >有关不同人员和目标收件人之间差异的更多信息，请参阅 [目标人员/收件人](metrics-calculation.md#targeted-persons---recipients).

**[!UICONTROL 3. Open and click-through rate]**

此值表显示每个Internet域的投放、打开、点击和原始反应性的细分。 使用以下指标：

* **[!UICONTROL Sent]** :在此域上发送的消息总数。
* **[!UICONTROL Complaints]** :收件人报告为不希望的此域的消息数。 速率是根据在此域上发送的消息总数计算的。
* **[!UICONTROL Opens]** :此域中至少打开过一次消息的不同目标收件人的数量。 速率是根据在此域上发送的消息总数计算的。
* **[!UICONTROL Clicks]** :在同一投放中至少点击一次的不同目标收件人的数量。 速率根据在此域上发送的消息总数计算
* **[!UICONTROL Raw reactivity]** :点击了投放至少一次的收件人数量与打开了投放至少一次的收件人数量的百分比。

>[!NOTE]
>
>此报表中显示的域名在多维数据集级别使用的明细列表中定义。 要更改、添加或删除默认域，请编辑 **[!UICONTROL Domains]** 列出列表并修改值和别名。 的 **[!UICONTROL Others]** 类别包括不属于项目列表任何值的域名。
>
>了解如何在 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/managing-enumerations.html){target=&quot;_blank&quot;}。


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>相关百分比是根据成功转发的消息数量计算的。

* **[!UICONTROL Distinct clicks for the population reached]** :在投放中至少点击一次的独特访客数。
* **[!UICONTROL Cumulated clicks]** :目标收件人的总点击次数，不包括退订链接和镜像页面。
* **[!UICONTROL Recipient clicks]** :在同一投放中至少点击一次的不同目标收件人的数量。
* **[!UICONTROL Estimated recipient reactivity]** :在投放中点击了至少一次的收件人数目与至少打开一次投放的预计收件人数目的比率。 选择禁用和镜像页面链接的点击次数未被考虑在内。
<!--
**[!UICONTROL 5. Web tracking]**

* **[!UICONTROL Visited pages]** : Number of web pages visited following message reception.
* **[!UICONTROL Transactions]** : Number of purchases following message reception.
* **[!UICONTROL Total amount]** : Total amount of purchases following message reception. 
* **[!UICONTROL Average transaction amount]** : Average purchase made by distinct delivery recipients. 
* **[!UICONTROL Articles]** : Number of articles purchased by the delivery recipients. 
* **[!UICONTROL Average count of articles per transaction]** : Average number of items per purchase made by distinct recipients.
* **[!UICONTROL Average amount per message]** : Average amount of purchases generated per message.

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

* **[!UICONTROL Reactivity]** : Ratio of the number of targeted recipients having clicked in a delivery, in relation to the estimated number of targeted recipients having opened a delivery. Clicks on the opt-out link and on the mirror page are not taken into account.

  >[!NOTE]
  >
  >For more information on tracking opens, refer to [this section](metrics-calculation.md#tracking-opens-).

* **[!UICONTROL Distinct clicks]** : Number of distinct people having clicked at least once (excluding unsubscription link and mirror page) in a delivery. The rate displayed is calculated based on the number of messages delivered successfully. 
* **[!UICONTROL Cumulated clicks]** : Total number of clicks by targeted recipients (excluding unsubscription link and mirror page). The rate displayed is calculated based on the number of messages forwarded successfully.

**[!UICONTROL Platform average]** : This average rate, displayed under each rate (reactivity, distinct clicks, and cumulated clicks), is calculated for deliveries sent over the previous six months. Only deliveries with the same typology and on the same channel are taken into account. Proofs are excluded.

The central table provides the following information:

* **[!UICONTROL Clicks]** : Number of cumulated clicks, per link. 
* **[!UICONTROL Clicks (in %)]** : Breakdown of the number of clicks per link, in relation to the total number of cumulated clicks.

**[!UICONTROL Breakdown of clicks in time]**

This chart shows the breakdown of cumulated clicks per day.
-->

## 投放摘要 {#delivery-summary}

此报表提供了有关投放的所有主要信息。

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

本节包含两个指标：

* **[!UICONTROL Initial population]** :投放所定向的收件人总数。
* **[!UICONTROL Messages rejected by the rule]** :应用分类规则时，分析期间忽略的地址数：地址丢失、已隔离、阻止列表已挂起等。 <!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

中图显示了在分析期间被拒绝消息的每个规则的划分。

**[!UICONTROL Delivery statistics]**

本节包括以下指标：

* **[!UICONTROL Messages to be delivered]** :投放分析后要投放的邮件总数。
* **[!UICONTROL Success]** :成功处理的消息数。 关联率是要投放消息数量的比率。
* **[!UICONTROL Errors]** :在投放和自动回弹处理过程中累积的错误总数。 关联率是要投放消息数量的比率。
* **[!UICONTROL New quarantines]** :投放失败后隔离的地址数（用户未知，域无效）。 关联率是要投放消息数量的比率。

## 热门点击 {#hot-clicks}

此报表可显示每个链接上的消息内容(HTML和/或文本)，以及链接的点击百分比。 个性化块退订链接、镜像页面链接和选件链接在累计的点击总数中会得到考虑，但不会显示在报表中。

>[!NOTE]
>
>如果您的投放包含选件（交互），则报表上方会显示一个框，显示选件的点击百分比。


## 跟踪统计信息 {#tracking-statistics}

此报表提供有关打开数、点击数和交易的统计资料。

它允许您跟踪投放的营销影响。 您可以通过更改时间刻度（1小时、3小时或24小时视图等）来配置值的显示方式。 单击 **[!UICONTROL Refresh]** 以确认您的选择。

此报表提供了值表和帕累托图，其中显示了达到最高效率所需的交付时间。 使用以下指标：

* **[!UICONTROL Opens]** :达到消息总打开数的百分比所需时间的估计。 未考虑文本格式的电子邮件。 [了解详情](metrics-calculation.md#tracking-opens-)。
* **[!UICONTROL Clicks]** :达到记录的点击总数百分比所需时间的估计。 选择退出链接和镜像页面的单击次数未被考虑在内。
<!--
* **[!UICONTROL Transactions]** : Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->


## 累积报告 {#cumulated-reports}

您可以显示投放的累积报告。 为此，请选择要比较的投放，以获取这些投放的报告列表。

要从列表中选择非相邻投放，请在进行选择时按住CTRL键。

要选择保存在其他文件夹中的投放，请单击 **[!UICONTROL Display sub-levels]** 图标（可在工具栏中访问）。 然后，它们将显示在同一列表中。


