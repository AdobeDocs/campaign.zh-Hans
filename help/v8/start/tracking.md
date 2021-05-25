---
solution: Campaign v8
product: Adobe Campaign
title: 跟踪和监控功能入门
description: 跟踪和监控功能入门
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 95ed0369-7215-496b-8e11-fe264c436488,e7931de5-83ce-431d-ae81-83793d257550
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 2%

---

# 跟踪和监视消息{#gs-ac-reports}

## Campaign中的跟踪功能

促销活动跟踪功能可跟踪发送的消息并帮助您分析收件人的行为：打开、点击链接、订阅/退订等。 您可以访问专用日志、报告和量度、查询数据库以查看收集的数据等。

:arrow_upper_right: 有关更多信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#tracking-tab)。

投放仪表板是监控投放情况以及在发送消息过程中出现潜在问题的关键工具。

:arrow_upper_right:有关更多信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=en#sending-messages)。

Campaign中可用的关键跟踪功能列在下面。

### 消息跟踪{#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**跟踪的链接**

您可以跟踪消息的接收情况以及消息内容中插入的链接的激活情况，以便更好地了解收件人的行为。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=en#sending-messages)

**URL跟踪**

可以通过激活或取消激活跟踪的URL来配置跟踪选项。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html?lang=en#sending-messages)


**跟踪的链接个性化**

促销活动跟踪功能允许您在电子邮件中添加可进行个性化且支持跟踪的链接。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html?lang=en#sending-messages)

**跟踪日志**

在发送投放并激活跟踪后， **Tracking**&#x200B;技术工作流会检索跟踪数据。 此数据可在投放的跟踪选项卡中找到。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html?lang=en#sending-messages)

**测试跟踪**

在发送包含跟踪的消息之前，您可以在镜像页面、电子邮件日志和链接上测试跟踪。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html?lang=en#sending-messages)

### Web应用程序跟踪{#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**跟踪 Web 应用程序**

您还可以使用跟踪标记来跟踪和测量Web应用程序页面上的访问量。 此功能可用于所有Web应用程序类型，如表单和在线调查。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html?lang=en#designing-content)

**选择退出 Web 应用程序跟踪**

Web应用程序跟踪选择退出功能允许您停止跟踪选择退出行为跟踪的最终用户的Web行为。 您可以包括在Web应用程序或登陆页中显示横幅的功能，以允许用户选择退出。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html?lang=en#designing-content)

### 跟踪报表{#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**跟踪统计信息**

此报表提供打开数、点击数和交易统计信息，并允许您跟踪投放的营销影响。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html?lang=en#tracking-reports)

**URL 和点击流**

此报表显示投放后访问的页面列表。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#urls-and-click-streams)

**人员和收件人**

通过此示例，更好地了解Adobe Campaign中的人员和收件人之间的跟踪差异。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=en#reporting)

**跟踪指标**

此报表整合了用于在收到投放时跟踪收件人行为的关键指标，如打开率、点进率和点击流。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#reporting)

**指标计算**

不同的表格提供了不同报表中使用的指标列表及其计算公式，具体取决于投放类型。

:arrow_upper_right:[在Campaign Classicv7文档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/indicator-calculation.html?lang=en#reporting)

## 监控准则

Adobe Campaign提供了一组功能来监控您的流程和环境。

### 监控投放

监控投放发送后的投放是确保营销活动高效且能够与客户联系的关键步骤。

:arrow_upper_right:进一步了解在发送投放后可以监控的信息，了解如何在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)中管理投放失败和隔离

### 监控工作流

:arrow_upper_right:了解如何在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=en#automating-with-workflows)中监控工作流的执行

### 监控实例

:arrow_upper_right:[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html?lang=en#monitoring-campaign-classic)中提供了实例监控指南

使用审核跟踪自助服务界面监控实例中所做的更改。 审核跟踪可实时捕获在您的Adobe Campaign实例内发生的操作和事件的完整列表。 您可以访问数据历史，以帮助回答以下问题：工作流发生的事件、上次更新这些事件的人员或用户在实例中执行的操作。

:arrow_upper_right:在[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/audit-trail.html?lang=en#accessing-audit-trail)中了解有关审核跟踪的更多信息
