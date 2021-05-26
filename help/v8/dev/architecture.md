---
solution: Campaign v8
product: Adobe Campaign
title: Campaign架构快速入门
description: Campaign架构快速入门
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 0%

---

# Campaign架构入门{#gs-ac-archi}

## 环境

Campaign可作为单个实例使用，每个实例代表一个完整的Campaign环境。

Campaign可用的三种环境Cloud Service:

* **生产环境**:为业务从业者托管应用程序。

* **暂存环境**:在将对应用程序所做的更改推送到生产环境之前，用于各种性能和质量测试。

* **开发环境**:允许开发人员在与暂存环境和生产环境相同的运行时条件下实施Campaign。

您可以将资源包从一个环境导出并导入到另一个环境。

:[!DNL :arrow_upper_right:]:了解有关[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)中软件包的更多信息

## 中间源部署{#mid-sourcing-deployment}

服务器和进程之间的一般通信按照以下模式进行：

![](assets/architecture.png)

* 实例上禁用了执行和退回管理模块。

* 该应用程序配置为在使用SOAP调用（通过HTTP或HTTPS）驱动的远程“中间源”服务器上执行消息执行。

>[!NOTE]
>
> Campaign v8依赖于混合架构。 如果您从Campaign Classicv7进行过渡，请注意，所有投放都经过中间源服务器。
> 因此，在Campaign v8中，内部路由方式为&#x200B;**不可能**，并且外部帐户已相应禁用。

## 消息中心架构{#transac-msg-archi}

事务型消息传递（消息中心）是用于管理触发器消息的Campaign模块。

[!DNL :bulb:] 在此部分中了解如何发送事务 [型消息](../send/transactional.md)。

为响应客户在网站上的操作，通过REST API发送Campaign事件，并填充通过API调用提供的信息或数据，并向客户实时发送事务型消息。 这些消息可以单独发送，也可以通过电子邮件、短信或推送通知批量发送。

在此特定架构中，执行单元与控制实例分开，以确保高可用性和负载管理。

* 营销人员和IT团队使用&#x200B;**控制实例**（或营销实例）来创建、配置和发布消息模板。 此实例还将事件监控和历史记录集中在一起。

   [!DNL :bulb:] 在此部分中了解如何创建和发布消 [息模板](../send/transactional.md)。

* **执行实例**&#x200B;会检索传入事件（例如，密码重置或网站的订单）并发送个性化消息。 可以有多个执行实例通过负载平衡器处理消息，并扩展要进行的事件数以实现最大可用性。

>[!CAUTION]
>
>控制实例和执行实例必须安装在不同的计算机上。 他们无法共享同一Campaign实例。

![](assets/messagecenter_diagram.png)

:[!DNL :arrow_upper_right:]:[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging)中介绍了消息中心架构

### 身份验证

要使用这些功能，Adobe Campaign用户登录到控制实例以创建事务型消息模板、使用种子列表生成消息预览、显示报告并监视执行实例。

* 单个执行实例
当与Adobe托管的消息中心执行实例交互时，外部系统可以首先通过使用提供的帐户登录和密码对会话登录方法进行api调用来检索会话令牌（默认在24小时后过期）。
然后，通过执行实例为响应上述调用而提供的sessionToken，外部应用程序可以调用SOAP API（rtEvents或batchEvents）来发送通信，而无需在每个SOAP调用中包含帐户登录和密码。

* 多个执行实例
在负载平衡器后面具有多个执行实例的多单元执行架构中，外部应用程序调用的登录方法将通过负载平衡器：因此，无法使用基于令牌的身份验证。 需要基于用户/密码的身份验证。

:[!DNL :arrow_upper_right:]:在[Campaign Classicv7文档](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)中了解有关事务性消息传递事件的更多信息