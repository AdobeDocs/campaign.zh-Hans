---
solution: Campaign Classic
product: campaign
title: 活动外部帐户
description: 活动外部帐户
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 13%

---

# 配置外部帐户

Adobe Campaign 提供了一组预定义的外部帐户。要设置与外部系统的连接，您可以创建新外部帐户。

技术工作流或营销策划工作流等技术流程，会使用外部帐户。例如，在工作流中设置文件传输或与任何其他应用程序(Adobe Target、Experience Manager等)进行数据交换时，您需要选择外部帐户。

:arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts.html)中创建和配置外部帐户

特定外部帐户管理活动本地数据库与云数据库([!DNL Snowflake])之间的连接。

:speech_balloon:作为托管Cloud Services用户，[!DNL Snowflake]外部帐户是按Adobe为您的实例配置的。

您可以访问此外部帐户来检查设置和执行复制工作流。 要执行此操作，请执行以下步骤：

1. 在活动&#x200B;**[!UICONTROL Explorer]**&#x200B;中，单击&#x200B;**[!UICONTROL Administration > Platform > External Accounts]**。

1. 选择&#x200B;**[!UICONTROL Full FDA]**&#x200B;外部帐户。

![](assets/snowflake-ext-account.png)

全局设置显示在&#x200B;**[!UICONTROL General tab]**&#x200B;中。

使用&#x200B;**[!UICONTROL Parameters]**&#x200B;选项卡，然后使用&#x200B;**[!UICONTROL Deploy functions]**&#x200B;按钮创建函数。

![](assets/snowflake-parameters.png)

**在此添加参数**

使用&#x200B;**[!UICONTROL Full FDA]**&#x200B;选项卡强制执行复制工作流。

![](assets/snowflake-full-fda.png)

**在此添加详细信息**

