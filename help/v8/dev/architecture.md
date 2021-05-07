---
solution: Campaign
product: Adobe Campaign
title: 开始使用活动架构
description: 开始使用活动架构
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# 开始使用活动体系架构{#gs-ac-archi}

## 环境

活动以单个实例的形式提供，每个实例代表一个完整的活动环境。

可用于活动环境的三种类型：

* 生产环境:为业务从业者托管应用程序。

* 舞台环境:在将应用程序更改推送到生产环境之前，用于各种性能和质量测试。

* 开发环境:允许开发人员在与舞台和生产活动相同的运行时条件下实施环境。

可以将包从一个环境导出并导入到另一个包。

:arrow_upper_right:了解有关[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html?lang=en#about-data-packages)中包的更多信息

## 中间源部署{#mid-sourcing-deployment}

服务器和进程之间的通用通信按以下模式进行：

![](assets/architecture.png)

* 实例上禁用了执行和跳出管理模块。

* 应用程序配置为在使用SOAP调用（通过HTTP或HTTPS）驱动的远程“中间源”服务器上执行消息执行。

>[!NOTE]
>
> 活动 v8依赖于混合架构。 如果要从Campaign Classic v7转换，请注意，所有投放都通过中间源服务器。
> 因此，在活动 v8中，内部路由为&#x200B;**不可能**，并且外部帐户已相应地禁用。


## 消息中心架构{#transac-msg-archi}

事务消息（消息中心）是用于管理触发消息的活动模块。

：灯泡：了解如何在[此部分](../send/transactional.md)中发送事务性消息。

响应于客户在网站上的操作，通过REST API发送事件，并且消息模板填充通过API调用提供的信息或数据，并将事务性消息实时发送给客户。 这些消息可以单独发送，也可以通过电子邮件、短信或推送通知分批发送。

在此特定架构中，执行单元与控制实例分离，以确保高可用性和负载管理。

* 营销人员和IT团队使用&#x200B;**控制实例**（或营销实例）创建、配置和发布消息模板。 此实例还集中了事件监视和历史记录。

   :arrow_upper_right:了解如何在[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/message-templates/introduction.html?lang=en#transactional-messaging)中创建和发布消息模板

* **执行实例**&#x200B;会检索传入事件（例如，密码重置或来自网站的订单）并发送个性化消息。 可以通过负载平衡器处理消息并缩放要执行的执行实例数，以实现最大可用性。

>[!CAUTION]
>
>控制实例和执行实例必须安装在不同的计算机上。 他们不能共享同一活动实例。

![](assets/messagecenter_diagram.png)

:arrow_upper_right:[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging)中介绍了消息中心体系结构


### 身份验证

要使用这些功能，Adobe Campaign用户登录到控制实例以创建事务性消息模板，使用种子列表生成消息预览，显示报告并监视执行实例。

* 单一执行实例
当与Adobe托管的消息中心执行实例交互时，外部系统可以通过使用提供的帐户登录名和密码对会话登录方法进行api调用，首先检索会话令牌（默认在24小时后过期）。
然后，利用执行实例为响应上述调用而提供的sessionToken，外部应用程序可以进行SOAP api调用（rtEvents或batchEvents）来发送通信，而无需在每个SOAP调用中包含帐户登录名和口令。

* 多个执行实例
在负载平衡器后面具有多个执行实例的多单元执行架构中，外部应用程序调用的登录方法正在通过负载平衡器：因此，不能使用基于令牌的身份验证。 需要基于用户/密码的身份验证。

:arrow_upper_right:了解有关[Campaign Classic文档](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)中的事务消息事件的更多信息