---
title: Campaign交互选件预定义过滤器
description: 了解如何创建预定义过滤器
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 092262c7-768c-4e86-9b2b-c52516f6a030
TQID: 'https://experienceleague.adobe.com/XWkWbgrMASz-9FfrXC23tTwiw54oQH5U4iWM9fa2FDQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%
---
# 创建预定义过滤器{#creating-pre-defined-filters}

创建预定义过滤器，定义可在选件创建期间轻松重复使用的目标群体的资格规则。 它们特定于每个环境，并将选件参数考虑在内。

>[!NOTE]
>
>Adobe Campaign Web UI为您提供了一个用户友好的界面，可轻松管理和自定义预定义过滤器以满足您的特定需求。 创建一次并保存，以供将来使用。 要了解有关Web UI预定义过滤器的更多信息，请参阅[Adobe Campaign Web UI文档](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/predefined-filters){target=_blank}。


要创建预定义过滤器，请应用以下流程：

1. 浏览到&#x200B;**[!UICONTROL Administration]**&#x200B;文件夹并选择&#x200B;**[!UICONTROL Pre-defined offer filters]**。

   ![选件 — 在“管理”下选择了“预定义选件过滤器”节点的设计树](assets/offer_filter_create_005.png)

1. 单击 **[!UICONTROL New]**。

   ![预定义的选件筛选器列表，其中突出显示“新建”按钮，并列出“年龄”筛选器](assets/offer_filter_create_001.png)

1. 更改标签以便以后能够识别过滤器。

   ![应用程序筛选器对话框，其“标签”字段设置为“电子邮件渠道”](assets/offer_filter_create_002.png)

1. 选择筛选条件将关注的字段。

   ![使用从收件人字段中选择的Email字段Select表达式对话框](assets/offer_filter_create_003.png)

1. 根据需要选择运算符和值，然后保存查询。

   运算符设置为的电子邮件表达式的![筛选条件不为空](assets/offer_filter_create_004.png)

1. 单击&#x200B;**[!UICONTROL Preview]**&#x200B;查看筛选结果。

   电子邮件渠道筛选器的“预览”选项卡，其中列出了与筛选器匹配的收件人![&#128279;](assets/offer_filter_create_006.png)
