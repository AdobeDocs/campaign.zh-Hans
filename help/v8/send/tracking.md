---
title: 消息跟踪入门
description: 详细了解Adobe Campaign中的跟踪功能
feature: Monitoring, Email
role: User
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: 90ed82673b893b62a185227dd8cdfe80cc8f1455
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 3%

---

# 消息跟踪入门 {#get-started-tracking}

借助跟踪功能，Adobe Campaign使您能够跟踪发送的消息并检查收件人的行为：打开、单击链接、退订等。

此信息在投放的每个收件人用户档案的&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡中检索。 此选项卡显示从列表中选择的收件人跟踪和点击的所有URL链接。 这是投放中跟踪的仍存在于投放屏幕中的所有URL的累积。 该列表可以配置，通常包含：点击的URL、点击的日期和时间以及在其中找到URL的文档。

**投放仪表板**&#x200B;也是用于监视投放和发送消息期间潜在问题的关键工具。

下图显示了用户与各种服务器之间的对话阶段。

<img src="assets/tracking-diagram.png" width="70%">

>[!NOTE]
>
>跟踪配置由Adobe针对托管云服务部署执行。

## 消息跟踪 {#message-tracking}

**跟踪的链接**

您可以跟踪邮件是否收到，以及邮件内容中插入的链接是否被点击，以便更好地了解收件人的行为。

[了解有关跟踪链接的更多信息](tracked-links.md)

**URL跟踪**

可通过激活或停用跟踪的URL来配置跟踪选项。

[了解有关URL跟踪选项的更多信息](url-tracking.md)

**跟踪的链接个性化**

利用Campaign跟踪功能，可在电子邮件中添加可个性化并支持跟踪的链接。

[详细了解个性化链接跟踪](personalized-links.md)

**跟踪日志**

发送投放并激活跟踪后，**跟踪**&#x200B;技术工作流会检索跟踪数据。 此数据可在投放的“跟踪”选项卡中找到。

[了解有关跟踪日志的更多信息](tracking-logs.md)

**测试跟踪**

在将消息与跟踪一起发送之前，您可以在镜像页面、电子邮件日志和链接上测试跟踪。

[了解有关测试跟踪的更多信息](testing-tracking.md)

## 跟踪报表 {#tracking-reports}

**跟踪统计数据**

此报表提供了有关打开、点击和交易的统计数据，并允许您跟踪投放对营销的影响。

[了解有关跟踪报表的更多信息](../reporting/delivery-reports.md#tracking-indicators)

**URL 和点击流**

此报表显示投放后访问的页面列表。

[了解有关URL和点击流的更多信息](../reporting/delivery-reports.md#urls-and-click-streams)

**人员和收件人**

通过此示例，更好地了解Adobe Campaign中个人/人员与收件人之间的跟踪差异。

请参阅[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html#reporting){target="_blank"}以了解有关人员和收件人的更多信息

**跟踪指标**

此报表将组合关键指标，用于跟踪接收投放时的收件人行为，例如打开次数、点进率和点击流。

[了解有关跟踪指标的更多信息](../reporting/delivery-reports.md#tracking-indicators)

**指标计算**

不同的表格会根据投放类型为您提供不同报告中使用的指标列表及其计算公式。

[了解有关指标计算的更多信息](../reporting/metrics-calculation.md)


