---
title: 使用Adobe Campaign发送直邮
description: Campaign中的直邮入门
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 13%

---

# 创建直邮投放

直邮投放允许您生成包含目标群体数据的提取文件。 然后，您可以与将向其定向群体投放消息的提供商共享此文件。

生成文件的步骤如下：

1. 创建投放

   根据模板创建直邮投放。 您可以复制和配置&#x200B;**[!UICONTROL Deliver by direct mail (paper)]**&#x200B;内置模板。

   请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html){target="_blank"}以了解详情

1. 定义受众

   收件人用户档案必须至少包含其姓名和邮政地址。

   邮政地址是计算字段。 默认情况下，地址最多可包含六行：第一行包含名字和姓氏，下一行包含邮政地址（门牌号码等），最后一行包含邮政编码和城镇或城市。 可以在nms：recipient模式中查看默认计算的postalAddress字段的定义。

   如果名称、邮政编码字段和城镇/城市字段不为空，则认为地址完整。 将从直邮投放中排除任何地址不完整的收件人。

   请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}以了解详情

1. 定义文件的内容

   使用提取向导定义要导出到输出文件中的信息（列）。

   请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html){target="_blank"}以了解详情

1. 验证投放

   检查分析结果和输出文件的内容。

   请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html){target="_blank"}以了解详情

   在营销活动上下文中，在提取日期创建提取文件。 您可以查看提取文件的内容、批准该文件或更改格式并根据需要重新启动提取。 文件获得批准后，即可向路由器发送通知电子邮件。 请参阅[此页面](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=zh-Hans)以了解详情

1. 开始投放

   验证提取文件后，单击&#x200B;**确认投放**&#x200B;确认消息可让您启动投放。

   确认会启动指定文件中的数据提取。

   在营销活动上下文中，当所有批准都获得后，将通过一个特殊工作流创建提取文件，在默认配置中，当直邮投放挂起提取时，将自动启动该工作流。 可在[此部分](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=zh-Hans){target="_blank"}中了解详情。
