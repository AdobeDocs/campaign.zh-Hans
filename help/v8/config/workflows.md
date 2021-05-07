---
solution: Campaign
product: Adobe Campaign
title: 活动自动化入门
description: 活动自动化入门
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# 管理和自动化流程

配置活动以利用强大的营销活动自动化功能。

您可以设置：

* 工作流
* 循环活动
* 端到端验证周期
* 警报
* 自动发送报表
* 触发事件

## 设计和使用工作流{#gs-ac-wf}

使用Adobe Campaign工作流提高营销活动各个方面(从创建细分、准备消息到投放)的速度和规模。

通过以下部分进一步了解工作流:

* [工作流入门](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* 工作流活动
   * [定位活动](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html):查询、阅读列表、扩充、合并等
   * [流控制活动](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html):调度程序、叉、警报、外部信号等
   * [操作活动](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):跨渠道投放、Javascript代码、CRM活动、更新聚合等
   * [事件活动](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):文件传输、Web下载等
* [通过端到端使用案例学习](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [在营销受众工作流程中构建活动](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [内置的技术工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [监视工作流执行](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## 设置循环活动

每次执行时，设计循环并创建新的投放实例。 例如，如果您的工作流设计为每周运行一次，则一年后将产生52个投放。 这也意味着日志将由每个投放实例分隔。

:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)中创建循环活动。

## 配置端到端验证周期

为投放的每个步骤设置批准流程，并确保对营销活动的各种流程进行全面监控和控制：定位、内容、预算、提取和发送验证。

通知将发送给设置为审阅者的Adobe Campaign操作员，以通知他们批准请求。

:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html)中设置和管理批准过程。


## 发送警报

作为活动运算符，您可以在发生故障时接收警报。

您可以创建一个工作流，它允许您监视一组工作流的状态并向主管发送循环消息。

:arrow_upper_right:了解如何创建工作流来监视[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow)中其他工作流的状态。

您还可以在发生故障时收到警报

## 发送自动报告

:arrow_upper_right:了解如何自动向操作符[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list)的列表发送报告。


## 利用触发器事件

使用活动事务消息传递自动化从信息系统触发的事件生成的消息。 例如，这些事务性消息可以是发票、订单确认、发运确认、密码更改、产品不可用通知、帐户对帐单或网站帐户创建。 这些消息可以单独发送，也可以通过电子邮件、短信或推送通知批量发送。

:arrow_upper_right:了解有关[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging)中事务消息功能的更多信息。


连接Adobe Campaign和Adobe Analytics以检索用户操作并发送近乎实时的个性化信息。

:arrow_upper_right:了解如何在[活动文档](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud)中将Campaign Classic与Analytics触发器集成。

：灯泡：了解如何将活动与[本节](../start/connect.md)中的其他解决方案集成
