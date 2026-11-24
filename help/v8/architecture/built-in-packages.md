---
title: 内置软件包
description: 了解Campaign v8中有哪些内置软件包，它们与自定义数据包有何不同，以及有哪些可用
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: a2ca220e4be9dfb4a90465b69dd08a3552040a07
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 15%
---
# 内置软件包 {#built-in-packages}

内置包（也称为标准包）包含Adobe Campaign的功能。 在Campaign v8中，Adobe会为您安装和管理这些软件包。 您无需安装它们。

## 内置包和自定义包 {#built-in-vs-custom}

Campaign使用两种类型的包。 确保与正确的团队合作。

| | 内置软件包 | 自定义包 |
|---|---|---|
| 用途 | 提供Campaign功能，例如渠道、集成和加载项。 | 导出并导入您自己的配置和数据，例如从暂存环境导入生产环境。 |
| 谁管理它们 | Adobe会安装和管理它们。 使用托管云服务，您无法修改已安装的内置软件包。 | 您可以创建、导出和导入它们。 |
| 在何处了解更多信息 | 此页面。 | [使用数据包](../dev/packages.md) |

## 检查已安装的包 {#check-installed-packages}

要检查实例上安装了哪些内置包，请浏览到&#x200B;**[!UICONTROL Administration > Configuration > Package management > Installed packages]**。 您还可以在控制面板的实例监控中查看它们。 请参阅[Campaign监视概述](../start/monitor.md#monitor-instance)以了解详情。

如果您需要未为您配置的包或加载项，请联系Adobe客户关怀团队或您的Adobe过渡经理。

## 内置软件包列表 {#list-of-built-in-packages}

下表列出了有关信息的内置软件包。 每个软件包的可用性取决于您的许可协议和部署模型。

| 包 | 说明 |
|---|---|
| 投放 | Adobe Campaign的强制性核心包。 它可让您发送投放。 [了解详情](../start/gs-message.md) |
| 营销活动（活动） | 定义、优化、执行和分析通信和营销活动。 [了解详情](../start/campaigns.md) |
| 营销资源 (MRM) | 在协作模式下控制营销活动，同时管理和跟踪任务、预算和营销资源。 [了解详情](../../automation/mrm/about-marketing-resource-management.md) |
| 优惠引擎（交互） | 在与联系人的交互期间，通过作出一个或多个自适应优惠实时响应。 [了解详情](../interaction/interaction.md) |
| 社交网络（社交媒体营销） | 将Adobe Campaign与X（以前称为Twitter）同步。 [了解详情](../connect/ac-tw.md) |
| 事务性消息控制和执行（消息中心） | 使用更高的可用性和更好的负载管理来管理从信息系统中的事件生成的触发消息。 [了解详情](../send/transactional.md) |
| LINE 渠道 | 通过LINE渠道发送投放。 [了解详情](../send/line/line.md) |
| 直邮渠道 | 通过直邮渠道发送投放。 [了解详情](../send/direct-mail.md) |
| 移动渠道（短信） | 通过移动渠道(SMS)发送投放，包括SMS连接器v2（自8.9.1起通常可用）。 [了解详情](../send/sms/sms.md) |
| 移动应用程序渠道 | 通过应用程序向iOS和Android设备发送个性化通知。 [了解详情](../send/push.md) |
| 内容管理器 | 创建定期新闻稿或网站，然后验证和发布消息。 [了解详情](../../automation/workflow/content-management.md) |
| 在线调查（调查管理器） | 创建和管理在线表单，以添加或修改用户档案信息、订阅、取消订阅或加入竞争对手。 [了解详情](../dev/surveys/about-surveys.md) |
| 营销分析 | 分析和测量数据，计算统计数据，并简化报告创建。 [了解详情](../reporting/gs-reporting.md) |
| 响应管理器 | 衡量所有渠道中的营销活动或优惠的成功性和盈利能力。 [了解详情](../../automation/response/about-response-manager.md) |
| 访问外部数据（联合数据访问） | 处理存储在外部数据库中的信息，而无需更改Adobe Campaign数据的结构。 [了解详情](../connect/fda.md) |
| 活动优化 | 控制、过滤和监控投放，以使消息符合客户需求和公司通信政策。 [了解详情](../../automation/campaign-opt/campaign-typologies.md) |
| 可投放性监控（电子邮件可投放性） | 测量您的邮件到达收件箱时是否不会退回或标记为垃圾邮件。 [了解详情](../send/monitoring-deliverability.md) |
| 优惠券管理 | 创建优惠券集以添加到营销优惠中。 [了解详情](../send/personalized-coupons.md) |
| 收件箱渲染 (IR) | 在可以接收消息的上下文中预览消息，并检查与主要桌面和Web电子邮件客户端的兼容性。 [了解详情](../send/inbox-rendering.md) |
| 集中式/本地营销（分布式营销） | 在中央实体（如总部）和本地实体（如销售点）之间实施合作活动。 [了解详情](../../automation/distributed-marketing/about-distributed-marketing.md) |
| CRM 连接器 | 将Adobe Campaign链接到第三方CRM系统。 [了解详情](../connect/crm.md) |
| 网站分析连接器 | 允许Adobe Campaign和Adobe Analytics进行交互。 [了解详情](../connect/ac-aa.md) |
| AEM 集成 | 在Adobe Experience Manager中管理电子邮件和表单内容。 [了解详情](../connect/ac-aem.md) |
| Adobe Experience Cloud 共享受众集成 | 与[!DNL Adobe CX Enterprise]（以前为Adobe Experience Cloud）解决方案和应用程序交换和共享受众。 [了解详情](../start/shared-audiences.md) |
| 与Adobe Experience Cloud集成 | 将受众从[!DNL Adobe CX Enterprise]（以前为Adobe Experience Cloud）解决方案导入和导出到Adobe Campaign中。 [了解详情](../connect/integration.md) |
| 隐私数据保护条例 | 添加了帮助遵守隐私规定的功能。 [了解详情](../start/privacy.md) |
| AMP 支持 | 使用交互式AMP发送动态电子邮件，用于电子邮件格式。 [了解详情](../send/defining-interactive-content.md) |


>[!NOTE]
>
>营销资源(MRM)、优惠券管理和在线调查包在Campaign的企业(FFDA)部署的上下文中不可用。 在[功能可用性](../architecture/enterprise-deployment.md#feature-availability)中了解详情。

## 相关主题 {#related-topics}

* [使用数据包](../dev/packages.md)：创建、导出和导入您自己的自定义数据包。
* [技术工作流](../../automation/workflow/technical-workflows.md)：内置的技术工作流以及安装每个技术工作流的包。
* [FFDA部署中的功能可用性](enterprise-deployment.md#feature-availability)：企业(FFDA)部署中不可用的功能。
* [不支持的功能](../start/v7-to-v8.md#gs-removed)： v8中不再支持的Campaign Classic v7功能。
* [全局原则](general-architecture.md)：在托管Cloud Services环境中可以和不能修改的内容。
* [开始使用Campaign v8](../start/get-started.md)：核心功能和加载项的概述。
