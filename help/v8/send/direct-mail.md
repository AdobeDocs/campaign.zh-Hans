---
title: 使用Adobe Campaign发送直邮
description: Campaign中的直邮入门
feature: Direct Mail
role: Data Engineer
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 12%

---

# 创建直邮投放

通过直邮投放，可生成包含目标群体数据的提取文件。 然后，您可以与将消息交付给目标群体的提供商共享此文件。

生成文件的步骤如下：

1. 创建投放

   根据模板创建直邮投放。 您可以复制并配置 **[!UICONTROL Deliver by direct mail (paper)]** 内置模板。

   ![](../assets/do-not-localize/book.png) 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html)以了解详情{target="_blank"}

1. 定义受众

   收件人用户档案必须至少包含其姓名和邮政地址。

   邮政地址是计算字段。 默认情况下，地址最多可包含六行：第一行包含名字和姓氏，下一行包含邮政地址（门牌号码等），最后一行包含邮政编码和城镇或城市。

   如果名称、邮政编码字段和城镇/城市字段不为空，则认为地址完整。

   ![](../assets/do-not-localize/book.png) 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)以了解详情{target="_blank"}

1. 定义文件的内容

   使用提取向导定义要导出到输出文件中的信息（列）。

   ![](../assets/do-not-localize/book.png) 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html)以了解详情{target="_blank"}

1. 验证投放

   检查分析结果和输出文件的内容。

   ![](../assets/do-not-localize/book.png) 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html)以了解详情{target="_blank"}

   在营销活动上下文中，在提取日期创建提取文件。 您可以查看提取文件的内容、批准它或更改格式并根据需要重新启动提取。 文件获得批准后，即可向路由器发送通知电子邮件。 请参阅[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html)以了解详情

1. 开始投放

   验证提取文件后，单击 **确认投放** 确认消息可让您启动投放。

   确认操作将开始提取指定文件中的数据。

   在营销活动上下文中，当所有批准都获得授权后，将通过特殊工作流创建提取文件，在默认配置中，当直邮投放挂起提取时，将自动启动该工作流。 了解详情，请参阅 [本节](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=zh-Hans)
