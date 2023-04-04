---
product: campaign
title: 入站电子邮件
description: 进一步了解入站电子邮件工作流活动
feature: Workflows, Channels Activity
exl-id: 6cc2c415-1886-4f31-8020-dbaf97a3cc43
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 1%

---

# 入站电子邮件{#inbound-emails}



的 **入站电子邮件** 活动，可让您从POP3邮件服务器下载和处理电子邮件。

![](assets/email_rec_edit_1.png)

的第一个选项卡 **入站电子邮件** 活动允许您输入POP3服务器的参数，并输入在收到每条消息时要执行的脚本。 第二个选项卡允许您为活动分配计划，第三个选项卡定义活动到期条件。

1. **[!UICONTROL Inbound Emails]**

   * **[!UICONTROL Use an external account]**

      激活此选项后，您可以选择外部POP3帐户，而不是输入连接参数。 的 **[!UICONTROL External account]** 字段指定用于连接到电子邮件服务的外部POP3帐户。 仅当启用“使用外部帐户”选项时，此字段才可见。

      如果未选择此选项，则必须指定以下参数：

      ![](assets/email_rec_edit_1b.png)

      * **[!UICONTROL POP3 server]**

         POP3服务器的名称。

      * **[!UICONTROL POP3 account]**

         用户的名称。

      * **[!UICONTROL Password]**

         用户帐户密码。

      * **[!UICONTROL Port]**

         POP3连接端口号。 默认端口为110。
   * **[!UICONTROL Stop as soon as email is processed]**

      此选项允许您逐个处理电子邮件。 活动仅激活其过渡一次，然后完成处理，在服务器上留下未处理的消息。


1. **[!UICONTROL Script]**

   利用脚本，可处理消息并执行依赖于消息内容的各种操作。 脚本针对每条消息执行，并且可以确定要对消息（离开或删除消息）和激活叫客过渡执行的操作。

   返回代码必须是以下值之一：

   * 1 — 从服务器删除消息并激活叫客过渡。
   * 2 — 将消息保留在服务器上并激活叫客过渡。
   * 3 — 从服务器删除消息。
   * 4 — 将消息保留在服务器上。

   可从全局访问消息的内容 **[!UICONTROL mailMessage]** 变量。

1. **[!UICONTROL Schedule]**

   要定义活动的计划，请单击 **[!UICONTROL Scheduling]** 选项卡和检查 **[!UICONTROL Plan execution]**. 单击 **[!UICONTROL Change]** 按钮以配置计划。

   计划配置与计划活动的计划配置相同。 请参阅 [调度程序](scheduler.md).

1. **[!UICONTROL Expiration]**

   您可以通过 **[!UICONTROL Expiration]** 选项卡。

   ![](assets/email_rec_edit_3.png)

   与计划活动的配置相同。 请参阅 [过期](define-approvals.md).
