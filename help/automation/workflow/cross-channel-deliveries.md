---
product: campaign
title: 跨渠道投放
description: 了解有关跨渠道投放的更多信息
feature: Workflows, Channels Activity
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# 跨渠道投放{#cross-channel-deliveries}

在 **[!UICONTROL Deliveries]** 选项卡 [活动工作流](campaign-workflows.md) 活动。

选择要作为投放基础的模板并定义其内容。

您可以使用不同的定位活动为工作流上游的投放指定定位。

在以下示例中，了解如何创建工作流，以在一周后为推送通知订阅者发送电子邮件或短信，然后发送推送通知。 操作步骤：

1. 创建营销策划.
1. 在 **[!UICONTROL Targeting and workflows]** 的 **[!UICONTROL Query]** 活动。
1. 配置查询：选择订阅推送通知的收件人作为目标维度。

   >[!NOTE]
   >
   >对于推送通知，请使用 **订户应用程序** 目标维度。

   ![](assets/cross_channel_delivery_1.png)

1. 将筛选条件添加到查询。 在这种情况下，我们将选择具有手机号码或电子邮件地址的收件人。

   ![](assets/cross_channel_delivery_2.png)

1. 添加 **[!UICONTROL Split]** 活动，以划分具有移动号码的收件人和具有电子邮件地址的收件人。
1. 在 **[!UICONTROL Delivery]** 选项卡，为每个目标选择投放。

   通过双击工作流中的投放活动，以与经典投放向导相同的方式创建投放。

   ![](assets/cross_channel_delivery_3.png)

1. 添加和配置 **[!UICONTROL Wait]** 活动，以便收件人一次不会收到过多投放。
1. 添加 **[!UICONTROL Split]** 活动来划分iOS或Android移动设备应用程序的订阅者。

   为每个操作系统选择一项服务。

   ![](assets/cross_channel_delivery_4.png)

1. 为每个操作系统选择和配置移动应用程序交付。

   ![](assets/cross_channel_delivery_5.png)
