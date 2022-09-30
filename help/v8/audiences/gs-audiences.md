---
title: Campaign中的用户档案和受众快速入门
description: 了解如何在Campaign中创建和管理用户档案和受众
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 20%

---

# Campaign中的用户档案和受众快速入门{#gs-profiles-and-audiences}

用户档案是存储在Campaign数据库中的联系人，例如客户、服务订阅者或潜在客户。 有许多可能的机制可获取用户档案并创建此数据库：通过 Web 窗体在线收集、手动或自动导入文本文件、复制公司数据库或其他信息系统的内容。借助Adobe Campaign，您可以整合营销历史、购买信息、偏好、CRM数据以及整合视图中任何相关的PI数据，以便进行分析并采取行动。 用户档案包含定位、鉴别和跟踪个人所需的所有信息。

用户档案是 **nmsRecipient** 表或外部表，用于存储所有配置文件属性，如名字、姓氏、电子邮件地址、Cookie ID、客户ID、移动标识符或与特定渠道相关的其他信息。 链接到收件人表的其他表包含与用户档案相关的数据，例如投放日志表，其中包含发送给收件人的所有投放记录。 了解有关 [此部分](../dev/datamodel.md#ootb-profiles).

在Adobe Campaign, **收件人** 是发送投放（电子邮件、短信等）的默认定向用户档案。 通过数据库中存储的收件人数据，您可以筛选将接收任何给定投放的目标，并在投放内容中添加个性化数据。 数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。


要使用用户档案数据填充Adobe Campaign，您可以：

* [导入数据文件](../start/import.md) 从外部数据源（如CRM系统）
* [创建web窗体](../dev/webapps.md) 允许客户输入自己的信息并创建自己的用户档案
* [映射到外部数据库](../connect/fda.md) 存储用户档案的位置
* 在Client Console中手动输入用户档案，如下所示：

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as “external” deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->
