---
solution: Campaign
product: Adobe Campaign
title: 使用活动和Adobe Analytics
description: 了解如何使用活动和Adobe Analytics
feature: 概述
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 3%

---

# 使用活动和Adobe Analytics

## Experience Cloud Triggers

您可以使用Experience Cloud触发器来使用管道在Adobe Campaign和Adobe Analytics之间连接数据。 管道从您的网站中检索用户的操作或触发器。 放弃购物车是触发器的一个示例。 触发器会以Adobe Campaign处理，以近乎实时地发送电子邮件。

:speech_balloon:作为“托管Cloud Services”用户，[与Adobe](../start/support.md#support)联系以使用活动实现Experience Cloud触发器。

## Adobe Analytics 数据连接器

使用新集成进行更新

您还可以配置Adobe Analytics Data Connectors以集成活动和分析。

Data Connector(以前称为Adobe Genesis)允许Adobe Campaign和Adobe Analytics通过&#x200B;**Web Analytics connectors**&#x200B;包进行交互。 此集成将Analytics与活动的数据共享为与电子邮件后用户行为相关的细分。 相反，它会通过Adobe Campaign将电子邮件活动的指示符和属性发送到Adobe Analytics — 数据连接器。

借助这些集成，Adobe Campaign可以恢复营销活动后一个或多个站点的访客行为数据，并(分析后)与视图一起运行再营销活动以将其转化为购买者。 相反，Web分析工具使Adobe Campaign能够将指标和活动属性转发到其平台。

每个工具的操作字段如下：

* Adobe Analytics:

   * 标记使用Adobe Campaign启动的电子邮件活动
   * 以区段的形式保存收件人行为，保存在单击活动电子邮件后浏览的站点上。 区段与放弃的产品（已查看但未添加到购物车或购买的产品）、购买或购物车放弃相关。

* Adobe Campaign:

   * 将指示符和活动属性发送到连接器，连接器将指示符和数据属性转发到Web分析工具
   * 恢复和分析细分
   * 触发再营销活动

请参阅https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes

:speech_balloon:作为“托管Cloud Services”用户，[与Adobe](../start/support.md#support)联系，将Adobe Analytics Data Connector与活动集成。

