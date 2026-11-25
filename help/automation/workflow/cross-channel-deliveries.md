---
product: campaign
title: 跨渠道投放
description: 了解关于跨渠道投放的更多信息
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
TQID: 'https://experienceleague.adobe.com/hD15kwTxO1uHeIQjrozZmONmVWI5ZrMn40ORMwrGbf8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 2%
---
# 跨渠道投放{#cross-channel-deliveries}

跨渠道投放在[营销活动工作流](campaign-workflows.md)活动的&#x200B;**[!UICONTROL Deliveries]**&#x200B;选项卡中可用。

Select要作为投放基础并定义其内容的模板。

您可以使用不同的定向活动，在工作流上游指定投放目标。

在以下示例中，了解如何创建工作流来向推送通知订阅者发送电子邮件或短信，然后在一周后发送推送通知。 操作步骤：

1. 创建营销策划。
1. 在营销活动的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;选项卡中，添加&#x200B;**[!UICONTROL Query]**&#x200B;活动。
1. 配置查询：选择订阅了推送通知的收件人作为目标维度。

   >[!NOTE]
   >
   >对于推送通知，请使用&#x200B;**订阅者应用程序**&#x200B;目标维度。

   ![将订阅者应用程序架构选为要筛选的文档的查询活动。](assets/cross_channel_delivery_1.png)

1. 将筛选条件添加到查询。 在这种情况下，我们将选择具有手机号码或电子邮件地址的收件人。

   ![带有移动设备的查询筛选器不为空，电子邮件的Or条件不为空。](assets/cross_channel_delivery_2.png)

1. 将&#x200B;**[!UICONTROL Split]**&#x200B;活动添加到您的工作流中，以划分具有手机号码的收件人和具有电子邮件地址的收件人。
1. 在&#x200B;**[!UICONTROL Delivery]**&#x200B;选项卡中，为每个目标选择一个投放。

   通过双击工作流中的投放活动，使用与使用经典投放向导相同的方式创建投放。

   ![带有查询和拆分的营销活动工作流，可导致移动投放和电子邮件投放。](assets/cross_channel_delivery_3.png)

1. 添加并配置&#x200B;**[!UICONTROL Wait]**&#x200B;活动，以便收件人不会一次收到太多投放。
1. 添加&#x200B;**[!UICONTROL Split]**&#x200B;活动以划分iOS或Android移动应用程序的订阅者。

   Select针对每个操作系统的服务。

   ![将订阅者应用程序作为定向维度并选定Android移动应用程序的订阅者的“查询”对话框。](assets/cross_channel_delivery_4.png)

1. Select ，并为每个操作系统配置移动应用程序交付。

   ![包含加入等待活动的电子邮件和短信投放的工作流，然后拆分为推送iOS和推送Android投放。](assets/cross_channel_delivery_5.png)
