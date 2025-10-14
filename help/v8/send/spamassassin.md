---
product: campaign
title: SpamAssassin
description: 了解如何使用SpamAssassin设置电子邮件垃圾邮件检测
feature: Email, Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8be6836d-f7dc-4199-b2b2-b6a9cac9d162
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 1%

---

# SpamAssassin{#spamassassin}

可以将Adobe Campaign配置为与用于电子邮件垃圾邮件过滤的第三方服务[SpamAssassin](https://spamassassin.apache.org){target="_blank"}一起使用。 这允许您对电子邮件进行评分，以确定邮件在接收时是否会被反垃圾邮件工具视为垃圾邮件。

SpamAssassin利用多种垃圾邮件检测技术，包括：

* 基于DNS和基于模糊校验和的垃圾邮件检测
* 贝叶斯滤波
* 外部程序
* 阻止列表
* 在线数据库

>[!NOTE]
>
>必须在Adobe Campaign应用程序服务器上安装和配置SpamAssassin。 有关更多信息，请联系您的Adobe代表。
>
>控制元素是否为垃圾邮件的规则通过SpamAssassin进行管理，并且可由具有权限的管理员编辑。

## 在营销活动中使用SpamAssassin {#using-spamassassin}

创建电子邮件投放并定义其内容后，请按照以下步骤评估风险。

有关创建和设计投放的更多信息，请参阅此[页面](defining-the-email-content.md)。


1. 转到&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡。
1. 选择一个收件人以预览您的投放。

   ![](assets/s_tn_del_preview_spamassassin_recipient.png)

   >[!NOTE]
   >
   >如果不选择收件人，则无法执行反垃圾邮件检查。

1. 出现警告消息，给出测试结果。 如果检测到高风险，将显示以下警告消息：

   ![](assets/s_tn_del_preview_spamassassin_ko.png)

1. 单击警告旁边的&#x200B;**[!UICONTROL More...]**&#x200B;链接。
1. 选择 **[!UICONTROL Anti-spam checking]** 选项卡。
1. 转到&#x200B;**[!UICONTROL Points / Rule / Description]**&#x200B;部分查看此风险的原因。

   ![](assets/s_tn_del_msg_spamassassin_ko.png)

>[!NOTE]
>
>每次单击&#x200B;**[!UICONTROL Anti-spam checking]**&#x200B;时，都会调用SpamAssassin服务，并再次分析邮件以进行反垃圾邮件检测。 在再次运行反垃圾邮件分析之前，请确保已更改您的内容。
