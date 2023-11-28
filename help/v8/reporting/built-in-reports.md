---
title: Adobe Campaign内置报告
description: 内置报告
feature: Reporting
role: User
level: Beginner
exl-id: b63e6905-3bd4-4de4-9e7e-7638e5fc1192
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '1115'
ht-degree: 2%

---

# Adobe Campaign内置报告 {#ootb-reports}

本页列出了Adobe Campaign内置的报告、其内容和上下文。 Adobe Campaign提供了一系列内置报表，这些报表可通过客户端控制台或Internet浏览器访问。

可以使用以下类型的报表：

* 在整个平台上报告。 [了解详情](global-reports.md)。
* 投放报告. [了解详情](delivery-reports.md)。

您可以从Campaign主页、专用报告仪表板或投放列表访问内置报告。 报表在UI中的显示方式取决于其上下文。

主页上有关键报告的列表，通过它，可快速访问投放数据。 此列表可以根据您的需求进行更改。 您还可以了解如何将自己的报告添加到 **[!UICONTROL Reports]** 选项卡。

有关这些自定义配置的更多信息，请参阅此 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/configuring-access-to-the-report.html).


## 访问内置报告 {#access-ootb-reports}

要访问Campaign内置报告，请执行以下操作：

1. 选择 **[!UICONTROL Reports]** Adobe Campaign选项卡。

   ![](assets/reporting-access-from-home.png)

1. 使用搜索字段筛选显示的报表。

1. 然后，单击要显示的报表。

   ![](assets/edit-a-report.png)

1. 单击 **[!UICONTROL Back]** 屏幕顶部的链接会将您转到报告列表。

   ![](assets/back-button.png)

特定于活动或投放的报告可通过其各自的仪表板访问。

![](assets/reporting-on-delivery.png)

对于列表、服务、选件等，此原则相同。 如下所示：

![](assets/reporting-on-offer.png)


## 投放报告 {#reports-on-deliveries}

下表显示了Adobe Campaign提供的内置报告。

有关这些报告内容的更多信息，请参阅 [本节](delivery-reports.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签和内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>架构</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 用户活动(recipientActivity)<br /> </td> 
   <td> 按时间段的打开、点击和交易细分。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放吞吐量（吞吐量）<br /> </td> 
   <td> 投放吞吐量图表，以消息/小时和Mbits/s为单位。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 失败和退回（错误）<br /> </td> 
   <td> 退回和无法投放（按原因和域）。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟踪指标(deliveryFeedback)<br /> </td> 
   <td> 用于跟踪收件人行为的关键指标摘要。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟踪指标(mobileAppDeliveryFeedback)<br /> </td> 
   <td> 跟踪投放到移动应用程序的指标。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 浏览器(browserStatistics)<br /> </td> 
   <td> 有关收件人点击消息后使用的浏览器的统计信息。<br /> </td> 
   <td> xtk：none<br /> </td> 
  </tr> 
  <tr> 
   <td> 共享到社交网络(deliveryForward)<br /> </td> 
   <td> 共享活动和邮件打开统计信息。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 热门点击（热门）<br /> </td> 
   <td> 显示消息和叠加的点击率。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 假设验证报表(deliveryHypothesis)<br /> </td> 
   <td> 显示投放假设验证的度量摘要。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放统计信息(statisticsPerDelivery)<br /> </td> 
   <td> 每个电子邮件域的统计数据（已处理消息、已投放消息、硬退回、软退回、点击次数、退订）。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 共享活动统计数据(forwardActivities)<br /> </td> 
   <td> 分析每个时段的共享活动、打开次数和订阅。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟踪统计数据(trackingStatistics)<br /> </td> 
   <td> 打开、单击和事务处理费率报表。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放摘要(deliverySending)<br /> </td> 
   <td> 投放指标摘要：目标、排除项和已发送消息。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放摘要(deliveryStatistics)<br /> </td> 
   <td> 所选投放的摘要表：目标、排除项和发送的消息。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 操作系统(osStatistics)<br /> </td> 
   <td> 点击消息的收件人使用的操作系统的统计信息。<br /> </td> 
   <td> xtk：none<br /> </td> 
  </tr> 
  <tr> 
   <td> 反应率(deliveryFeedbackSocial)<br /> </td> 
   <td> 投放反应率和反应细分。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> URL和点击吞吐量(topUrlDelivery)<br /> </td> 
   <td> 大多数反应URL和相关联的点击流。<br /> </td> 
   <td> nms：delivery<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 营销活动报表 {#reports-on-campaigns}

有关营销活动的报表涉及 **nms：operation** 表格。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签和内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 用户活动(operationRecipientActivity)<br /> </td> 
   <td> 按时段划分的打开、点击和交易，取决于Campaign。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放吞吐量（操作吞吐量）<br /> </td> 
   <td> 以邮件/小时和Mbits/s表示的投放吞吐量图表取决于Campaign。<br /> </td> 
  </tr> 
  <tr> 
   <td> 营销活动费用(budgetOperationExpenses)<br /> </td> 
   <td> 显示详细的促销活动行项目，具体取决于促销活动。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失败和退回(operationErrors)<br /> </td> 
   <td> 退回和无法投放项按原因和域分类，具体取决于Campaign。<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorerOperation)<br /> </td> 
   <td> 成本行的描述性分析，取决于MRM。<br /> </td> 
  </tr> 
  <tr> 
   <td> 跟踪指标(operationFeedback)<br /> </td> 
   <td> 关键跟踪指标概览：打开数、点击数和事务处理数取决于促销活动。<br /> </td> 
  </tr> 
  <tr> 
   <td> 共享到社交网络(operationForward)<br /> </td> 
   <td> 共享活动和邮件打开统计信息，具体取决于Campaign。<br /> </td> 
  </tr> 
  <tr> 
   <td> 假设验证报表(operationHypothesis)<br /> </td> 
   <td> 显示Campaign投放的假设验证测量摘要，具体取决于Campaign。<br /> </td> 
  </tr> 
  <tr> 
   <td> 共享活动统计数据(forwardActivityOpt)<br /> </td> 
   <td> 根据Campaign分析每个时段的共享活动、打开次数和订阅。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放摘要(operationStatistics)<br /> </td> 
   <td> 活动投放的摘要图表：目标、排除项和已发送消息。<br /> </td> 
  </tr> 
  <tr> 
   <td> URL和点击吞吐量(operationTopUrlDelivery)<br /> </td> 
   <td> 大多数被反应的URL和相关联的点击流取决于Campaign。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 服务报表 {#reports-on-services}

关于服务的报告涉及 **nms：service** 表格。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签和内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 粉丝收购(socialAcquisitionsByWebapp)<br /> </td> 
   <td> 哪些Web应用程序支持了潜在客户收购？ 依赖社交营销加载项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 订阅细分(mobileAppDistribution)<br /> </td> 
   <td> 每个移动应用程序的活动订阅的细分，取决于移动应用程序渠道加载项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 订阅跟踪(subscriptionsProgress)<br /> </td> 
   <td> 信息服务订购的发展<br /> </td> 
  </tr> 
  <tr> 
   <td> 反应率(socialReactionRate)<br /> </td> 
   <td> 最新投放的反应率是多少？ 依赖社交营销加载项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 反应率(mobileAppReactivityRate)<br /> </td> 
   <td> 最新投放的反应率取决于移动应用程序渠道加载项。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 预算报表 {#budget-reports}

下表显示了Adobe Campaign提供的内置报告。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签和内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>架构</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 与方案关联的成本(budgetProgramCost)<br /> </td> 
   <td> 方案费用细目。<br /> </td> 
   <td> nms：program<br /> </td> 
  </tr> 
  <tr> 
   <td> 预算演变(budgetEvolution)<br /> </td> 
   <td> 按承付款额分列的预算费用的变化。<br /> </td> 
   <td> nms：budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 预算的累积演变(budgetCumulativeEvolution)<br /> </td> 
   <td> 按承诺细分的累计预算成本的演变<br /> 时间级别。 </td> 
   <td> nms：budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorerBudget)<br /> </td> 
   <td> 成本行的描述性分析。<br /> </td> 
   <td> nms：budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 浏览成本行(budgetExplorer)<br /> </td> 
   <td> 成本行的描述性分析。<br /> </td> 
   <td> nms：costLine<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorerPlan)<br /> </td> 
   <td> 成本行的描述性分析。<br /> </td> 
   <td> nms：plan<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorerProgram)<br /> </td> 
   <td> 成本行的描述性分析。<br /> </td> 
   <td> nms：program<br /> </td> 
  </tr> 
  <tr> 
   <td> 预算摘要（预算）<br /> </td> 
   <td> 主要成本、费用类别和预算的快照。<br /> </td> 
   <td> nms：budget<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 模拟报表 {#reports-on-simulations}

模拟报表涉及 **nms：simulation** 表格。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签和内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 模拟排除的详细信息(dlvSimuLossDetail)<br /> </td> 
   <td> 所有排除原因的详细表格。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按排名划分优惠(offerSimulationRanking)<br /> </td> 
   <td> 模拟中按排名划分的优惠。<br /> </td> 
  </tr> 
  <tr> 
   <td> 模拟摘要(dlvSimuLossSummary)<br /> </td> 
   <td> 模拟数量和排除项摘要。<br /> </td> 
  </tr> 
  <tr> 
   <td> 重叠统计(dlvSimuOverling)<br /> </td> 
   <td> 投放目标重叠量。<br /> </td> 
  </tr> 
  <tr> 
   <td> 模拟排除项摘要(dlvSimuLossSimu)<br /> </td> 
   <td> 模拟导致的排除列表。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Web应用程序报表 {#reports-on-web-applications}

关于Web应用程序的报告涉及 **nms：WebApp** 表格。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签和内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 文档（调查词典）<br /> </td> 
   <td> 调查结构的描述，取决于Survey Manager加载项。<br /> </td> 
  </tr> 
  <tr> 
   <td> 主要(surveyProperties)<br /> </td> 
   <td> 调查属性<br /> </td> 
  </tr> 
  <tr> 
   <td> 回复的细目(surveyDistribution)<br /> </td> 
   <td> 对问题的回复的细分。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 其他ootb报告 {#other-ootb-reports}

内置提供了以下报告。 有关更多信息，请参阅有关其相关功能的文档。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签和内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
   <td> <strong>架构</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠分析(offerAnalysis)<br /> </td> 
   <td> 每个日期和渠道的优惠分析，取决于交互加载项。<br /> </td> 
   <td> nms：offer<br /> </td> 
  </tr> 
  <tr> 
   <td> 再营销效率(remarketingEffect)<br /> </td> 
   <td> 再营销效率的衡量<br /> </td> 
   <td> nms：webEvent<br /> </td> 
  </tr> 
  <tr> 
   <td> 社交潜在客户获取的历史(socialVisitorStatistics)<br /> </td> 
   <td> X(以前称为Twitter)和Facebook潜在客户收购的历史取决于Social营销附加产品。<br /> </td> 
   <td> nms：visitor<br /> </td> 
  </tr> 
  <tr> 
   <td> 最近建议跟踪(recentPropositions)<br /> </td> 
   <td> 实时建议跟踪<br /> </td> 
   <td> nms：propositionRcp<br /> </td> 
  </tr> 
 </tbody> 
</table>
