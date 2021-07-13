---
product: Adobe Campaign
title: 通过Adobe Campaign发送直邮
description: Campaign中直邮入门
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 12%

---

# 创建直邮投放

通过直邮投放，可生成包含目标群体数据的提取文件。 然后，您可以与将向目标群体发送消息的提供商共享此文件。

生成文件的步骤如下：

1. 创建投放

   根据模板创建直邮投放。 您可以复制并配置&#x200B;**[!UICONTROL Deliver by direct mail (paper)]**&#x200B;内置模板。

   ↗️ 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html)以了解详情

1. 定义受众

   收件人用户档案必须至少包含其名称和邮政地址。

   邮政地址是计算字段。 默认情况下，地址最多可包含六行：第一行包含名字和姓氏，下一行包含邮政地址（门牌号码等），最后一行包含邮政编码和城镇或城市。

   如果名称、邮政编码字段和城镇/城市字段不为空，则地址被视为完整地址。

   ↗️ 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)以了解详情

1. 定义文件的内容

   使用提取向导可定义要导出到输出文件中的信息（列）。

   ↗️ 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html)以了解详情

1. 验证投放

   检查分析结果和输出文件的内容。

   ↗️ 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html)以了解详情

   在营销活动的上下文中，提取日期会创建提取文件。 您可以查看提取的文件内容、批准该文件，或更改格式并根据需要重新启动提取。 文件获得批准后，即可向路由器发送通知电子邮件。

   ↗️ 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html#approving-an-extraction-file)以了解详情

1. 开始投放

   验证提取文件后，单击&#x200B;**确认投放**&#x200B;确认消息，即可启动投放。

   确认会开始指定文件中的数据提取。

   在营销活动的上下文中，当所有批准都获得批准后，提取文件将通过特殊的工作流创建，在默认配置中，当直邮投放处于待提取状态时，该工作流将自动启动。

   ↗️ 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html#starting-an-offline-delivery)以了解详情