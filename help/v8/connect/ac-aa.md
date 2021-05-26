---
solution: Campaign v8
product: Adobe Campaign
title: 使用Campaign和Adobe Analytics
description: 了解如何使用Campaign和Adobe Analytics
feature: 概述
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 2%

---

# 使用Campaign和Adobe Analytics


## Adobe Analytics Connector

您可以配置Adobe Analytics连接器以集成Campaign和Analytics。

Adobe Analytics连接器允许Adobe Campaign和Adobe Analytics通过&#x200B;**Web Analytics连接器**&#x200B;附加组件进行交互。 此集成将Analytics中的数据作为与电子邮件后用户行为相关的区段共享到Campaign。 相反，它会将Adobe Campaign提供的电子邮件促销活动的指标和属性发送到Adobe Analytics - Data connector。

使用Adobe Analytics Connector，Adobe Campaign可以测量Internet受众(Web Analytics)。 借助这些集成，Adobe Campaign可以在营销活动后恢复一个或多个网站的访客行为数据，并（经过分析）运行再营销活动，以便将他们转化为购买者。 相反，Web分析工具使Adobe Campaign能够将指标和促销活动属性转发到其平台。

每个工具的操作字段如下所示：

* **Adobe Analytics**

   * 标记通过Adobe Campaign启动的电子邮件促销活动
   * 以区段形式保存收件人在点击促销活动电子邮件后浏览的网站上的行为。 区段与放弃的产品（已查看但未添加到购物车或已购买）、购买或购物车放弃相关。

* **Adobe Campaign**

   * 将指示器和营销活动属性发送到连接器，连接器又将它们转发到Web分析工具
   * 恢复和分析区段
   * 触发再营销活动

在[本页](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html)上了解有关Adobe Campaign和Adobe Analytics的更多信息

[!DNL :speech_balloon:]  作为受管Cloud Services用户， [请](../start/campaign-faq.md#support) 联系Adobe以将Adobe Analytics Data Connector与Campaign集成。


## Experience Cloud Triggers

您可以使用Experience Cloud触发器通过管道在Adobe Campaign和Adobe Analytics之间连接数据。 管道从您的网站中检索用户的操作或触发器。 放弃购买是触发器的一个示例。 在Adobe Campaign中处理触发器可近乎实时地发送电子邮件。

在[此页面](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en)上了解有关Adobe Campaign和Experience Cloud触发器的更多信息。

[!DNL :speech_balloon:]  作为受管Cloud Services用户，请 [联系](../start/campaign-faq.md#support) Adobe以通过Campaign实施Experience Cloud触发器。
