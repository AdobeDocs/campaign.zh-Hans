---
title: Campaign v8 常见问题解答
description: 获取有关设置、配置、消息传递、工作流等的常见Adobe Campaign v8问题的答案
feature: Overview
role: User
level: Beginner
keywords: 常见问题解答， Campaign v8，问题，回答，帮助，支持，故障排除
version: Campaign v8
hide: true
hidefromtoc: true
source-git-commit: 825421f9b25830daad6bdf5c8a58a1c58b272835
workflow-type: tm+mt
source-wordcount: '12510'
ht-degree: 9%

---

# 常见问题解答 {#faq}

快速获取有关Adobe Campaign v8的最常见问题的答案。 无论您是刚刚入门还是正在寻找高级配置帮助，您都可以找到以下按主题排列的答案。

**是营销活动的新用户？**&#x200B;以[一般问题](#general)和[关键概念](#key-concepts)开始。\
**需要技术帮助？**&#x200B;检查[开发人员](#developers)和[促销活动设置](#settings)。\
**找不到您的答案？**&#x200B;访问我们的[社区论坛](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}或[联系支持人员](#get-help)。

**提示：**&#x200B;使用Ctrl+F(在Mac上按Cmd+F)搜索此页面上的特定关键字。 单击任意问题以展开答案。


## 一般问题 {#general}

获取有关Adobe Campaign v8的最常见问题的答案，包括如何连接、升级和获取支持。

+++ 如何连接到 Campaign v8？

您需要下载并安装 Campaign 客户端控制台才能连接到 Adobe Campaign。

[单击此处以了解详情](connect.md)。

从Campaign v8.6版本开始，您可以访问&#x200B;**Campaign Web用户界面**，该界面可通过集中式Adobe Experience Cloud环境使用。 Experience Cloud是Adobe的集成式数字营销应用程序、产品和服务系列。

在本页[中了解如何连接到Adobe Experience Cloud并访问Adobe Campaign Web界面](campaign-ui.md#ac-web-ui)。 请参阅 [Adobe Campaign Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}以了解详情。


**相关主题：**

[安装客户端控制台](connect.md) | [Campaign用户界面](campaign-ui.md) | [用户权限](gs-permissions.md)

+++

+++ Campaign v8是否可以安装在内部部署或混合环境中？

没有。Campaign v8作为&#x200B;**托管Cloud Service**&#x200B;独家提供，完全由Adobe托管。

**托管云服务的主要优势：**

* 卓越的性能和可扩展性
* 自动升级 — 始终为最新版本
* 通过持续监控增强的安全性
* 无基础架构管理或IT开销
* 内置的高可用性和灾难恢复

了解有关[Campaign v8架构](../architecture/architecture.md)以及Campaign v8与Classic v7[之间](../start/v7-to-v8.md)差异的更多信息。

+++

+++ 如何将 Campaign 升级到最新版本？

Adobe Campaign 会定期更新。每年都会发布包含新功能、改进和修复的次要版本。此外，我们还定期发布仅包含累积修复的内部版本。

这种定期更新旨在让您掌握最新、最充分的信息，保持环境的安全，并改进您对我们产品的体验。这就是为什么我们认为运行最新版本的 Adobe Campaign 至关重要的原因。

**注意：**&#x200B;作为Managed Cloud Services用户，您的实例已由Adobe升级为新版本。

了解有关[Campaign版本和升级的详细信息](upgrades.md)。

+++

+++ 如何改进电子邮件可投放性？

电子邮件可投放性是每个发件人的营销计划取得成功的重要因素，其特点是不断变化的标准和规则。想要在这个数字化的世界中取得成果，就必须定期调整电子邮件策略，并考虑关键可投放性趋势，以便最好地吸引受众。

请参阅本指南以了解[可投放性最佳实践](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}

要了解如何在 Campaign 中实施可投放性，请参阅[本指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=zh-Hans){target="_blank"}

**相关主题：**

[关于可投放性](../send/about-deliverability.md) | [控制邮件内容](../send/control-message-content.md) | [监视投放能力](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ 如何确认我的投放已成功发送，并且未出现错误？

请按照以下步骤操作以确保成功交付：

发送前&#x200B;**：**

* 运行投放分析以检测错误（缺少个性化、收件人无效、内容问题）
* 发送测试验证以验证渲染和个性化
* 在准备期间查看警告
* 验证目标群体计数

**发送期间和发送之后：**

* 监测投放仪表板的实时统计数据（已发送、已投放、退回、错误）
* 检查投放日志以了解消息级别状态
* 跟踪成功率、跳出率和错误消息
* 查看隔离的地址

**最佳实践：**

* 设置错误阈值的警报
* 对大型卷使用批次（批量发送）
* 先进行小容量测试
* 定期清理收件人数据库
* 监测发件人信誉

了解有关[监视投放](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans){target="_blank"}和[投放最佳实践](delivery-best-practices.md)的更多信息。

+++

+++ 是否能监测工作流的执行？

是的。 Campaign提供了多种用于监视工作流执行的工具：

* **[工作流仪表板](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}** — 查看每个工作流活动的实时状态、进度和错误
* **[工作流日志](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** — 访问详细的执行日志以解决问题
* **[热图](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** — 可视化工作流活动并识别性能瓶颈
* **[审核跟踪](../reporting/audit-trail.md)** — 跟踪对工作流所做的所有修改
* **[警报](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** — 为工作流失败或延迟设置通知

要监视工作流，请打开该工作流并单击&#x200B;**日志**&#x200B;选项卡。 失败的活动会以红色突出显示，您可以通过单击这些活动来查看错误详细信息。

了解有关[监视工作流执行](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}和[工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}的更多信息。

+++

+++ 哪些系统和组件与 Campaign v8 兼容？

在 [Adobe Campaign 兼容性矩阵](compatibility-matrix.md)中，您可以获得支持 Campaign 最新版本的所有系统和组件的列表。

+++

+++ 如何下载Campaign？

可以从 Adobe 下载中心获取安装程序和客户端控制台。

作为管理员用户，请访问Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/zh-hans/campaign.html){target="_blank"}下载Adobe Campaign。

在此页面[上了解有关分发中心](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hans){target="_blank"}的更多信息。

+++

+++ 域委派的程序是怎样的？

子域是域的一个分支，可用于隔离您的品牌或各种类型的流量（事务性消息、营销信息等）。

>[!NOTE]
>
>作为托管云服务用户，请联系 Adobe 以将子域委派给 Adobe。

+++

+++ 作为Campaign Classic v7用户，我是否可以迁移到Campaign v8？

从现有 Campaign Classic v7 环境进行自动迁移的功能尚不可用。

Campaign v8 **仅**&#x200B;作为托管式云服务提供，不能部署在内部部署或混合环境中。

有关迁移流程的更多信息，请联系您的 Adobe 代表。

+++


+++ 如何记录问题？

通过创建案例，您可以就您在使用 Adobe 产品的过程中遇到的任何问题联系 Adobe 客户支持团队。为帮助您解决问题或排除疑难，Adobe Admin Console 将支持您与 Adobe 客户支持团队聊天。

如需在新系统中登记问题或开始聊天会话，请连接到 [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}。

此系统要求每个用户都有个人帐户，并具有正确的权限。如果您发现无法使用 Adobe ID 登录，请通过 Experience League 提出访问请求，客户关怀团队将尽快为您进行设置。[了解详情](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

加入 Campaign 社区：在现有问题中搜索答案或询问专家。[加入对话](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

+++


## 重要概念 {#key-concepts}

了解Campaign的基本概念，包括身份验证、用户界面、工作流和核心功能，以便有效入门。

+++ 我可以使用Adobe ID连接到Campaign v8吗？

是！ 通过与IMS (Adobe Identity Management System)集成，用户可使用其Adobe ID连接到Adobe Campaign控制台。 该集成具有以下优势︰

* 所有 Experience Cloud 解决方案都可以使用相同的 ID。
* 使用具有不同集成的 Adobe Campaign 时，可以记住该连接。
* 密码管理策略更安全。
* 使用联合 ID 帐户（外部 ID 提供商）。

[了解更多](connect.md)如何使用Adobe ID访问Campaign v8。

+++

+++ 我的 Campaign 是什么版本？

可通过 Campaign 客户端控制台的 **Help > About...** 菜单查看您的[版本号和构建号](upgrades.md#version)。

+++

+++ Campaign Classic v7与Campaign v8之间有何区别？

Campaign v8是Campaign的下一代版本，专为托管云服务而设计。 它在基础架构、安全性、可投放性和监控方面带来了显着改进。

Adobe Campaign v8作为&#x200B;**托管Cloud Service**&#x200B;独家提供，不能部署在内部部署或混合环境中。

[了解有关从Campaign Classic v7过渡到v8](v7-to-v8.md)的更多信息。

+++

+++ 如何设置用户权限?

作为 Campaign 管理员，您可以为组织的用户设置权限。

这些权限是一组权利或限制，可授权或拒绝用户执行以下操作：

* 访问特定功能
* 访问特定数据
* 创建、修改和/或删除数据

[了解有关Campaign v8用户权限的更多信息](../start/gs-permissions.md)。

**相关主题：**

[开始使用权限](gs-permissions.md) | [管理用户权限](manage-permissions.md) | [添加文件夹权限](folder-permissions.md)

+++

+++ 我应该了解哪些 Campaign 用户界面概念?

请参阅[此部分](campaign-ui.md)，了解有关Adobe Campaign用户界面基础知识的更多信息。

从Campaign v8.6版本开始，您还可以访问新的&#x200B;**Campaign Web用户界面**，该界面可通过集中式Adobe Experience Cloud环境使用。

[请参阅Adobe Campaign Web用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}以了解详情。

+++

+++ 如何选择消息的受众？

凭借 Adobe Campaign，您可以使用不同策略来创建受众，并选择目标收件人。

[了解更多](../audiences/gs-audiences.md)如何在Campaign v8中定义受众。

+++

+++ 什么是工作流？

Adobe Campaign 包括在不同的应用程序服务器模块之间编排所有流程和任务的工作流。您可以利用这个全面的图形环境设计各式流程，包括部分划分、活动执行、文件处理、人员参与等。工作流引擎会执行并跟踪这些流程。

例如，您可以使用某个工作流从服务器下载文件、解压缩，然后将其中包含的记录导入 Adobe Campaign 数据库。

此外，一个工作流也可能涉及到要通知一个或多个操作员，或者是可以作出决策和批准流程的相关人员。这样就可以创建一次投放行动，将内容相关任务指派给一位或多位操作员，指定目标并在开始投放前审批校样。

[了解工作流详细信息](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}。 您也可以阅读[工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}。

**相关主题：**

[工作流入门](../config/workflows.md) | [构建您的第一个工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"} | [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [监视工作流执行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

+++ 如何创建并发送第一封电子邮件？

在Campaign v8中创建第一封电子邮件涉及几个关键步骤：

1. **创建投放** — 首先从模板或从头开始创建新电子邮件投放
1. **定义受众** — 使用查询、列表或工作流选择目标收件人
1. **设计内容** — 使用电子邮件设计器创建个性化消息
1. **使用验证进行测试** — 发送测试电子邮件以验证内容和个性化
1. **分析和发送** — 运行投放分析以检查错误，然后发送电子邮件

Campaign v8提供两种用于创建电子邮件的界面：

* **客户端控制台** — 具有高级功能的全功能桌面应用程序
* **Campaign Web UI** — 新式、直观的Web界面，可加快电子邮件的创建

[在Campaign v8中了解有关电子邮件设计和验证的更多信息](../send/email.md)。

**相关主题：**

[创建您的第一个投放](create-message.md) | [使用投放模板](../send/create-templates.md) | [投放最佳实践](delivery-best-practices.md) | [定义电子邮件内容](../send/defining-the-email-content.md) | [预览和验证](../send/preview-and-proof.md) | [配置并发送](../send/configure-and-send.md) | [个性化内容](../send/personalize.md)

+++

+++ 如何发送 SMS 消息？

使用Campaign v8发送短信消息需要初始配置，然后遵循简单的投放流程：

**初始设置（一次性配置）：**

1. **配置短信渠道** — 设置短信投放设置和外部帐户
1. **配置SMPP连接** — 通过SMPP协议连接到您的SMS服务提供商
1. **测试连接** — 验证与短信提供商的连接
1. **设置路由** — 定义通过提供商路由短信消息的方式

**创建和发送短信：**

1. **创建短信投放** — 从模板开始新的短信投放
1. **定义收件人** — 使用电话号码字段选择您的移动受众
1. **编写SMS内容** — 创建消息（标准为160个字符或更长，包含串联）
1. **添加个性化** — 包含特定于每个收件人的动态字段
1. **发送校样** — 测试SMS投放以验证内容和投放
1. **分析和发送** — 运行分析并发送给您的受众

**关键短信功能：**

* **多个SMPP连接器** — 支持各种短信提供商和协议
* **投放报告** — 跟踪已发送、已投放和失败的邮件
* **字符编码** — 支持GSM7、Unicode和特殊字符
* **长短信支持** — 长短信的自动消息连接
* **双向SMS** — 使用工作流处理入站SMS响应

[在Campaign v8中了解有关短信配置和发送的更多信息](../send/sms/sms.md)。

**相关主题：**

[开始使用短信](../send/sms/sms.md) | [短信投放设置](../send/sms/sms-delivery-settings.md) | [SMPP外部帐户设置](../send/sms/smpp-external-account.md) | [创建短信投放](../send/sms/create-sms.md) | [短信内容](../send/sms/sms-content.md) | [发送短信验证](../send/sms/sms-proofs.md) | [监控SMS](../send/sms/sms-monitor.md)

+++

+++ 如何发送推送通知？

使用Campaign v8发送推送通知涉及配置移动应用程序集成和创建吸引人的通知：

**初始设置（一次性配置）：**

1. **配置推送渠道** — 在Campaign中设置推送通知渠道设置
1. **集成Campaign SDK** — 将Adobe Campaign SDK添加到您的移动应用程序（或使用数据收集）
1. **配置移动应用程序** — 在Campaign中注册iOS和Android应用程序
1. **设置证书** — 配置APNs证书(iOS)和FCM密钥(Android)
1. **测试注册** — 验证设备是否可以注册和接收令牌

**创建和发送推送通知：**

1. **创建推送投放** — 从模板启动新的推送通知
1. **选择平台** — 选择iOS和/或Android
1. **定义受众** — 使用移动应用订阅数据定位应用订阅者
1. **设计通知** — 创建标题、消息和富媒体内容
1. **配置行为** — 设置点击操作、深层链接和自定义数据
1. **发送测试通知** — 在发送之前在实际设备上验证
1. **分析和发送** — 查看定位并发送给您的移动受众

**推送通知功能：**

* **富推送通知** — 包含图像、视频和交互式按钮(iOS和Android)
* **Personalization** — 基于用户配置文件和行为的动态内容
* **深层链接** — 将用户引导至特定的应用程序屏幕或内容
* **计划** — 基于用户时区在最佳时间发送
* **A/B测试** — 测试不同的消息并优化参与度
* **跟踪** — 监视器打开次数、点击次数和转化次数

**平台特定功能：**

* **iOS** — 静默通知、通知类别、声音自定义
* **Android** — 富推送模板、通知渠道、自定义布局

[了解有关Campaign v8中推送通知配置的更多信息](../send/push-settings.md)。

**相关主题：**

[创建并发送推送通知](../send/push.md) | [配置推送通知渠道](../send/push-settings.md) | [设计Android富推送](../send/rich-push-android.md) | [设计iOS富推送](../send/rich-push-ios.md) | [使用数据收集进行配置](../send/push-data-collection.md) | [跟踪和监视](tracking.md)

+++

+++ 如何创建登陆页？

您可以使用Adobe Campaign数字内容编辑器来设计登陆页并定义与数据库字段的映射。

[请参阅Campaign v8文档以了解详情](../dev/landing-pages.md)。

您还可以使用Campaign Web用户界面创建和发布登陆页面 — [了解更多](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}。

+++

+++ 如何跟踪投放内容？

在Campaign v8中您可通过专用的[投放报告](../reporting/delivery-reports.md)跟踪发送的投放，然后监视您的投放。

在此页面[中了解有关促销活动](../start/tracking.md)中跟踪管理的更多信息。

**相关主题：**

[跟踪和监视邮件](tracking.md) | [传递报告](../reporting/delivery-reports.md) | [了解投放失败](../send/delivery-failures.md) | [配置跟踪的链接](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ 如何翻译错误消息？

错误消息是用外文显示的？[此页面](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hans){target="_blank"}中列出了所有错误消息及其译文。

+++

+++ 我能在 Campaign 中创建 Web 窗体并收集回答吗？

是的。 使用&#x200B;**Campaign Web Applications和Forms**（客户端控制台）创建Web表单，以便完全控制表单逻辑和验证；或者使用&#x200B;**Campaign登陆页面**(Web UI)，为订阅和商机开发提供现代化的拖放界面。 两者都会将数据直接收集到Campaign中，并集成到工作流中以自动执行操作。

[了解有关Web应用程序和表单的更多信息](../dev/webapps.md) | [Campaign Web UI登陆页面](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8与先前版本 {#v7-differences}

了解Campaign v8与先前版本（Classic v7和Standard）之间的主要差异，包括架构、部署、迁移路径和功能更改。 无论您是来自Campaign Classic v7还是Campaign Standard，都可以了解新增功能以及如何平稳过渡。

+++ Campaign v8与先前版本之间有何主要区别？

Campaign v8是Adobe Campaign的完全再造，专为现代云原生架构而设计，与Campaign Classic v7和Campaign Standard相比有显着改进：

**部署模型：**

* **v8：**&#x200B;仅限Managed Cloud Services — 由Adobe完全托管和管理
* **v7/Standard：**&#x200B;内部部署、混合或托管选项可用
* **优点：**&#x200B;零基础架构管理、自动扩展、企业级安全性、主动监控

**架构和性能：**

* 使用PostgreSQL数据库的&#x200B;**v8：**&#x200B;增强型完全FDA (FFDA)架构
* **v8：**&#x200B;批处理吞吐量达到每小时&#x200B;**200万次操作**
* **v8：**&#x200B;事务性消息吞吐量为每小时&#x200B;**1百万**
* **v8：**&#x200B;实时数据探索和快速构建受众（分钟与小时）
* **好处：**&#x200B;大型操作和复杂营销活动的性能更高

**用户界面：**

* **v8：**&#x200B;新的&#x200B;**Campaign Web用户界面**&#x200B;以及客户端控制台 — 直观、可访问，非常适合营销人员
* **v8：**&#x200B;具有拖放功能的现代响应式设计
* **v8：**&#x200B;简化的营销活动创建和管理工作流
* **v8：**&#x200B;与Campaign Standard界面有许多相似之处
* **优势：**&#x200B;入门更快，活动执行更轻松，可访问性更好，学习曲线最短

**新关键功能：**

* **富推送通知**，其中包含图像、视频、交互式按钮、轮播和计时器
* 用于生成内容（电子邮件、短信、推送）的&#x200B;**AI助手**，具有品牌一致性评分
* **已升级SMS基础结构(SMS v2.0)**，可靠性和兼容性得到改进
* **Adobe Experience Manager as a Cloud Service集成**&#x200B;以实现无缝内容管理
* **增强的报告**，包括Campaign Standard用户的动态报告

**升级和维护：**

* **v8：**&#x200B;由Adobe管理的自动升级 — 始终为具有连续交付模型的最新稳定版本
* **v7/Standard：**&#x200B;需要手动升级规划和执行
* **优点：**&#x200B;减少了维护负担，可立即访问新功能，无需停机

**API和集成：**

* **v8：**&#x200B;具有增强的性能和可靠性的现代REST API
* **v8：**&#x200B;与Adobe Experience Cloud和Adobe Experience Platform无缝集成
* **优势：**&#x200B;更简单的集成、更好的互操作性、现代开发实践

[了解关于Campaign v8关键功能的更多信息](whats-new.md)

**相关主题：**

[从Campaign Classic v7到v8](v7-to-v8.md) | [v7到v8过渡指南](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"} | [从Campaign Standard到v8](acs-to-v8.md) | [Campaign Standard过渡](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Campaign v8采用指南](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/acs-to-ac/home){target="_blank"} | [Campaign v8功能矩阵](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Campaign v8 架构](../architecture/architecture.md)
* [护栏和限制](ac-guardrails.md)

+++

+++ 我应该从Campaign Classic v7还是Campaign Standard迁移到v8？

**Campaign v8非常适合于需要：**&#x200B;的组织

* **大量营销活动** — 发送数百万条消息，其性能和可靠性都得到了改进（每小时2000万条操作）
* **企业可扩展性** — 无性能顾虑地扩展数据库和营销活动
* **新式Web用户界面** — 直观、响应式的Campaign Web UI，可加快活动创建并改善用户体验
* **云原生优势** — 利用自动更新、托管的基础架构、弹性扩展和主动监控
* **长期支持** - Campaign v8是Adobe的具有扩展支持的战略平台，而以前的版本将在未来几年内停止支持
* **减少IT开销** — 消除基础架构管理和升级计划
* **高级功能** - AI助手、富推送、增强型短信、Adobe Experience Platform集成

对于Campaign Standard用户：**&#x200B;**

Campaign Standard用户现在有资格过渡到Campaign v8托管云服务。 主要优势包括：

* **熟悉的界面** - Campaign Web UI与Campaign Standard有许多相似之处，可最大限度地减少学习过程
* **功能等同性** — 关键Campaign Standard功能已添加到v8（动态报告、集中品牌策略、REST API、登陆页面、可视化片段）
* **增强的支持** — 提供卓越的帮助，可实现平稳过渡和持续平台监控
* **数据迁移** — 从Campaign Standard导入所有数据时中断最少
* **一致的用户体验** — 继续使用熟悉的工作流程和界面

对于Campaign Classic v7用户&#x200B;**：**

Campaign v8在保持核心Campaign功能的同时，实现了重大改进：

* **双界面** — 访问功能强大的客户端控制台和现代化的Campaign Web UI
* **更好的性能** — 查询性能和数据处理得到了显着改进
* **Cloud优势** — 由Adobe管理的自动升级、安全修补程序、备份/恢复
* **新式架构** — 增强的FFDA架构与PostgreSQL配合使用以获得更好的可扩展性

**何时考虑迁移：**

* 您的当前Campaign实例处理大量数据（数百万个配置文件）
* 您遇到复杂工作流或定位的性能问题
* 您希望降低基础架构管理和维护成本
* 您需要与Adobe Experience Cloud或Adobe Experience Platform无缝集成
* 您仍然在计划重大升级或基础架构更新
* **您希望使用面向未来的技术** — 对以前版本的支持即将终止
* **您的团队需要新式界面** - Campaign Web UI为营销人员提供了更好的辅助功能

**迁移注意事项：**

* Adobe提供迁移支持、指导和工具
* v8仅限于Managed Cloud Service（无内部部署或混合部署）
* 某些技术实施可能不同 — 请查看[功能矩阵](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* 数据迁移和测试需要规划和资源
* **对于Campaign Standard用户** — 过渡旨在保持平稳，工作流中断最小

**后续步骤：**

请联系您的Adobe代表：

* 评估您的迁移准备情况和时间表
* 了解用例的特定优势
* 规划迁移策略和资源分配
* 访问迁移工具和支持

**相关主题：**

**对于Campaign Classic v7用户：** [从Campaign Classic v7到v8](v7-to-v8.md) | [v7到v8详细指南](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**对于Campaign Standard用户：** [Campaign Standard过渡到v8](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Campaign v8采用指南](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/acs-to-ac/home){target="_blank"} | [从Campaign Standard到v8概述](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/overview){target="_blank"} | [营销人员快速入门](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/marketers){target="_blank"} | [管理员/开发人员快速入门](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**常规资源：** [Campaign v8功能矩阵](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [兼容性矩阵](compatibility-matrix.md)

+++

+++ Campaign v8中的主要术语和功能区别是什么？

Campaign v8增强了大多数Campaign Classic v7和Campaign Standard功能，但某些功能会因云原生架构而发生更改，并且某些术语在版本之间有所不同。

**术语差异(Campaign Standard到v8)：**

* **自定义资源**&#x200B;现在是&#x200B;**架构**
* **消息**&#x200B;称为&#x200B;**投放**
* **产品用户**&#x200B;现在是&#x200B;**操作员**
* **角色**&#x200B;配置有&#x200B;**命名权限**
* **安全组**&#x200B;现在是&#x200B;**操作员组**
* **组织单位**&#x200B;通过&#x200B;**文件夹权限**&#x200B;进行管理

**Campaign Web UI术语更新：**

Campaign Web UI中已更新以下术语（客户端控制台使用传统术语）：

* **收件人**&#x200B;现在是&#x200B;**用户档案**
* **种子地址**&#x200B;现在是&#x200B;**测试配置文件**
* **传递分析**&#x200B;现在是&#x200B;**传递准备**（单击&#x200B;**准备**&#x200B;按钮）
* **电子邮件预览**&#x200B;可通过&#x200B;**模拟内容**&#x200B;按钮使用
* **列表**&#x200B;现在是&#x200B;**受众**

**在v8中不可用：**

* **内部部署和混合部署** - v8仅为托管式云服务
* **直接数据库访问** — 改用提供的API和工具
* **客户管理的基础结构** - Adobe管理所有的基础结构
* **手动内部版本升级** — 现在为自动(Adobe托管)

**v8中的不同实施：**

* **技术工作流** — 某些已针对云架构进行了优化，可能会工作方式不同
* **数据库结构** — 增强的FFDA架构可能需要架构调整
* **自定义集成** — 可能需要更新基于云的架构
* **低级自定义项** — 有些自定义项在托管环境中需要不同的方法

在v8中增强或替换了&#x200B;**：**

* **内部版本升级** — 使用连续交付模型自动而不是手动
* **性能优化** — 由Adobe基础架构优化处理
* **安全修补程序** — 由Adobe自动应用
* **备份和恢复** — 作为服务的一部分由Adobe管理
* **用户界面** — 客户端控制台旁新增了Campaign Web UI

为Campaign Standard用户添加了过渡到v8的&#x200B;**功能：**

* **动态报告** — 包含人口统计分析的可自定义实时报告
* **集中式品牌** — 定义品牌视觉和技术准则
* **REST API** — 创建集成并构建生态系统
* **登陆页面改进** — 增强与Campaign Standard的功能对等性
* **可视片段** — 可重用的电子邮件和内容模板可视组件

**重要信息：**&#x200B;大多数营销和运营功能在v8中可用并得到了改进。 Adobe在云环境中管理技术和基础架构级别的功能。

**相关主题：**

[功能矩阵](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [兼容性矩阵](compatibility-matrix.md) | [护栏和限制](ac-guardrails.md) | [v7到v8过渡指南](v7-to-v8.md)
* [Campaign Standard到v8的过渡](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++

## 轮廓和受众 {#audiences}

查找有关管理营销策划的用户档案、创建受众、导入数据和定向收件人等问题的答案。

+++ 如何创建收件人？

在客户端控制台中为各个用户档案手动创建收件人，从文件(CSV/TXT)导入以进行批量添加，使用Web表单进行自助注册，或通过外部系统的API进行集成。 使用导入工作流进行定期数据加载。

[手动创建配置文件](../audiences/create-profiles.md) | [从文件导入用户档案](../audiences/import-profiles.md) | [使用Web窗体收集配置文件](../audiences/collect-profiles.md)

+++

+++ 如何导入用户档案？

Campaign提供了多种导入方法：使用导入向导导入简单的文件；基于工作流的导入以进行复杂转换；通过SFTP中的计划工作流重复导入；导入API以进行程序集成。

对于文件导入，请准备数据文件（CSV/TXT、UTF-8编码），使用导入向导或工作流，将列映射到Campaign字段，定义更新/插入规则，并首先使用小示例进行测试。 使用工作流进行定期导入并应用重复数据删除规则。

[导入数据指南](../start/import.md) | [循环导入工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [数据加载活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}

+++

+++ 如何定义营销活动的目标群体？

Campaign提供了多种定位方法：使用可视条件构建查询、定位现有列表或区段、从外部文件(CSV、TXT)导入收件人或应用预定义过滤器。 您可以将标准与AND/OR逻辑相结合，排除特定群体，使用控制组，以及拆分以进行A/B测试。 始终在发送前预览目标群体大小。

[定义营销活动目标](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"} | [查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [创建受众](../audiences/create-audiences.md)

+++

+++ 如何创建用户档案列表？

列表是一组静态的收件人，您可以在投放中定位并在营销活动中重复使用。

**三种创建方法：**

* **手动创建：**&#x200B;导航到&#x200B;**[!UICONTROL Profiles and Targets > Lists]**&#x200B;并单击&#x200B;**[!UICONTROL Create]**。 通过查询、单个选择或文件夹添加收件人。

* **工作流自动化：**&#x200B;使用&#x200B;**[!UICONTROL List update]**&#x200B;活动从查询结果或导入的数据中自动创建和维护列表。

* **导入期间：**&#x200B;在导入用户档案时创建一个列表以将其另存为可重复使用的组。

**提示：**&#x200B;使用工作流处理需要定期更新的列表，以及手动创建的一次性分段。

[创建受众](../audiences/create-audiences.md) | [列出更新活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ 如何在发送邮件前删除重复的群体？

在投放之前使用工作流中的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活动删除重复的收件人。 将其放在您的&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Delivery]**&#x200B;活动之间，然后选择您的重复数据删除条件（通常是电子邮件地址或收件人ID）以及要保留的记录。

**提示：**&#x200B;发送前始终删除重复项，以确保每个人只收到一次您的消息。

[重复数据删除活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}

+++

+++ 如何识别和定位新闻稿的订阅者？

Campaign通过信息服务自动跟踪新闻稿订阅。 要定位订阅者，请执行以下操作：

* 使用&#x200B;**[!UICONTROL Query]**&#x200B;活动并筛选&#x200B;**[!UICONTROL Subscriptions]** >选择新闻稿服务
* 通过选择&#x200B;**[!UICONTROL To > Subscribers of an information service]**&#x200B;直接从投放中定位订阅者
* 使用&#x200B;**[!UICONTROL Subscription Services]**&#x200B;工作流活动生成订阅者列表

Campaign跟踪订阅/退订历史记录，并自动管理选择加入/选择退出。

[管理订阅](../start/subscriptions.md) | [查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ 从目标群体中排除用户档案的最佳实践是什么？

在工作流中使用&#x200B;**[!UICONTROL Exclusion]**&#x200B;活动从目标中删除不需要的用户档案。 将其放在定向活动之后，并定义要排除的群体。

[排除活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ 我能否在不在Campaign中导入外部用户档案的情况下使用外部用户档案？

是的，通过Campaign v8，您可以使用存储在外部数据库中的外部用户档案，而无需将其加载到Adobe Campaign中。 [了解详情](../audiences/external-profiles.md)。

+++

+++ 如何为投放创建测试用户档案？

测试用户档案是用于发送验证和验证投放而不影响生产数据库的特殊收件人。 在&#x200B;**[!UICONTROL Profiles and Targets > Test profiles]**&#x200B;中创建测试收件人，或使用&#x200B;**[!UICONTROL Seed addresses]**&#x200B;功能自动将测试收件人添加到您的投放以进行质量保证和收件箱监控。

[测试轮廓](../audiences/test-profiles.md)

+++

## 消息设计 {#design}

了解如何在Campaign v8中设计有效的营销消息，包括电子邮件模板、个性化技术和多语言内容。 在客户端控制台中设计消息，或在Campaign Web UI中使用现代的&#x200B;**Email Designer**，以增强可视化编辑体验。

+++ 在Campaign中设计电子邮件的最佳实践是什么？

关键准则：确保实现移动响应式设计，将HTML 4.0/XHTML兼容代码与内联CSS一起使用，使用替换文本优化图像（小于100 KB），使用个性化合并字段，在发送之前跨电子邮件客户端进行测试，并包含纯文本版本。 将电子邮件总大小控制在500 KB以下以实现最佳可投放性。

[电子邮件设计指南](../send/email.md) | [投放最佳实践](delivery-best-practices.md)

+++

+++ 什么是投放模板？

投放模板是预配置的投放，可保存所有设置和参数以供在多个营销活动中重复使用。 模板包括目标规则、内容设计、个性化、技术设置（发件人、回复）和类型规则。 创建一次并重复使用，以保持一致性并加快活动创建。

[创建投放模板](../send/create-templates.md)

+++

+++ 在 Campaign 中能轻松导入现有的 HTML 以制作电子邮件吗?

是的。 通过直接复制/粘贴将HTML内容导入内容编辑器、从计算机上传文件或从URL加载。 确保您的HTML使用具有内联CSS的电子邮件兼容代码(HTML 4.0/XHTML)，并将图像托管在公共服务器上。 Campaign会自动将个性化和跟踪添加到导入的HTML。

**提示：**&#x200B;要获得最佳的电子邮件设计体验，请在Campaign Web UI中使用&#x200B;**电子邮件Designer**，它提供现代拖放功能和内置响应模板，而不是导入原始HTML。

[导入HTML内容](../send/defining-the-email-content.md)

+++

+++ 如何在 Campaign 中创建基于订阅的新闻稿？

是的。 使用Campaign的信息服务管理新闻稿订阅。 关键功能包括自动选择加入/选择退出处理、订阅跟踪、合规性管理(GDPR、CAN-SPAM)、多新闻稿支持、注册表单的Web集成以及面向订阅者的目标交付。

[管理订阅](../start/subscriptions.md)

+++

+++ 如何个性化各种消息？

Campaign提供个性化功能，根据收件人数据、行为和偏好创建相关的定向消息。

**Personalization选项：**

* **个性化字段** — 插入收件人数据（例如，`"Hello {{firstName}}")`）
* **个性化块** — 使用预定义或自定义的内容块
* **条件内容** — 根据收件人条件显示不同的内容
* **行为数据** — 利用浏览历史记录、购买模式或参与量度

在发送之前测试个性化，以验证合并字段和条件逻辑是否正常工作。

[Personalization指南](../send/personalize.md) | [个性化字段](../send/personalization-fields.md) | [条件内容](../send/conditions.md)

+++

+++ 我能发送多语言邮件吗？

是的。 Campaign v8提供多语言功能，其中&#x200B;**Campaign Web UI**&#x200B;提供了最简单的方法。 Web UI通过语言变体提供本机多语言交付 — 将语言变体添加到交付中，并且Campaign会根据收件人的首选语言自动发送相应的版本。 可用于电子邮件、推送通知、短信和事务型消息。

主要功能：自动内容复制、基于语言的自动发送、默认语言回退和轻松的变量管理。

客户端控制台还支持使用条件内容和工作流的多语言内容，但需要更多手动配置。

[多语言投放(Web UI)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [条件内容（客户端控制台）](../send/conditions.md)

+++

+++ 我可以将Web窗体本地化吗？

是的。 Campaign Web应用程序支持多语言本地化。 为所有表单元素（标签、按钮、消息、错误文本）定义翻译，并根据收件人配置文件或浏览器设置自动进行语言检测。 单个Web应用程序支持多种语言版本，并在需要时回退到默认语言。

[Web应用程序本地化](../dev/webapps.md)

+++

+++ 我可以在电子邮件中使用AI支持的内容吗？

是，但&#x200B;**只能通过Campaign Web UI**。 由Microsoft Azure OpenAI和Adobe Firefly提供支持的AI助手有助于跨电子邮件、短信和推送通知创建专业且品牌一致的内容。

**关键功能：**

* 生成文本（电子邮件副本、主题行、短信/推送内容）和品牌对齐的图像
* 创建针对不同受众优化的内容变体
* 优化内容（精细、摘要、改写、简化）
* 上传品牌资产并获得品牌一致性评分
* 使用现有内容作为引用和上传样式引用图像

**注意：** AI助手仅在Campaign Web UI中可用，当前仅支持英语。 用户需要适当的权限，并且必须同意用户协议。

[AI助手概述](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI助手用例](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [品牌一致性](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## 测试和发送消息 {#send}

了解测试、验证、发送和跟踪营销消息的最佳实践，以确保成功交付营销活动。

+++ 什么是投放分析？

投放分析是Campaign在发送之前运行的验证阶段。 它计算目标群体、验证内容、检查错误、应用分类规则并估计投放量。

Campaign生成显示警告和错误的日志。 错误会阻止投放，必须修复；警告是建议性的。 发送前请务必查看分析日志。

[投放分析指南](../send/delivery-analysis.md)

+++

+++ 为何要创建验证？

校样是在发送给主受众之前验证投放的测试消息。 使用校样验证个性化、测试跨电子邮件客户端的内容渲染、确认链接和跟踪工作、检查图像和附件，以及验证移动响应性。

验证有助于在错误到达成千上万的收件人之前捕获错误、支持利益相关者批准和测试收件箱放置。 将验证发送到多个电子邮件客户端和设备，并始终在生产发送之前获得批准。

[验证和预览指南](../send/preview-and-proof.md)

+++

+++ 如何在 Adobe Campaign 中使用种子地址？

种子地址是特殊收件人，会自动添加到每次投放以进行测试、质量保证和监控，这与您的目标条件不匹配。 对于持续监控、收件箱放置测试、直邮验证和利益相关者可见性非常有用。

**与校对的主要差异：**

* **种子地址** — 已自动添加到生产投放，计入发送数量
* **验证** — 测试在生产之前发送，不计入卷，用于验证

在&#x200B;**[!UICONTROL Resources > Campaign management > Seed addresses]**&#x200B;中管理种子地址。 保持较小的列表以避免影响投放量度。

[种子地址指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ 如何设置发送邮件前的批准流程？

Campaign提供审批工作流程，以确保报文在发送前符合质量标准。 在营销活动或投放级别为内容、目标、提取（直邮）和预算配置批准。

**设置：**

在&#x200B;**[!UICONTROL Administration > Access management > Operator groups]**&#x200B;中创建操作员组，然后在营销活动或投放属性中分配审批组。 Campaign会向批准、拒绝或请求更改的审阅人发送通知电子邮件。

**对于独立投放（不在营销活动中）：**

使用&#x200B;**验证作为您的审批流程**。 将验证发送到您的审批组进行验证，并始终在做出更改后发送新验证，以确保利益相关者查看最新版本。

[投放验证](../send/preview-and-proof.md) | [营销活动审批](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=zh-Hans){target="_blank"}

+++

+++ 什么是类型规则？

类型规则是在投放分析期间应用的自动业务逻辑，用于验证和优化消息发送。 它们确保遵守营销政策，保护可投放性，并防止客户疲劳。

**主规则类型：**

* 列入阻止列表 **筛选规则** — 排除收件人（已、已取消订阅、已隔离）
* **压力规则** — 控制消息频率以避免收件人过多
* **容量规则** — 限制用于处理容量或ISP限制的邮件量
* **控制规则** — 检查邮件有效性（主题行、取消订阅链接、发件人格式）

规则将分组为类型，并在投放分析期间应用。 Campaign可以根据规则排除收件人、阻止投放或生成警告。

[类型规则指南](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何分批次发送电子邮件？

是的。 波次发送将按计划间隔将投放拆分为多个批次。 这对于大型营销活动至关重要，这些活动可以平衡服务器负载、防止ISP带宽限制、通过新IP建立发件人信誉以及管理批次之间的选择退出/退回。

**配置：**

在投放属性中，启用波次发送并定义波次数（或批次大小）、波次间隔和波次分布（线性或自定义百分比）。 Campaign会自动划分目标群体，并按计划发送每个波次。

将批次用于大型营销活动，在继续之前监视首轮效果，并在批次之间留出足够的时间处理退回和选择退出。

[配置波次发送](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ 在 Campaign 中创建电子邮件有哪些重要步骤？

在Campaign v8中创建电子邮件涉及以下关键步骤：创建投放、定义目标受众、设计内容、添加个性化、配置设置（发件人、主题、回复）、运行投放分析、发送验证以进行测试，最后发送或计划。

**关键步骤：**

1. **创建投放** — 选择电子邮件作为渠道，并选择性地选择投放模板
1. **定义目标** — 使用查询、列表或导入的文件选择您的收件人受众
1. **设计内容** — 使用电子邮件编辑器(Web UI电子邮件Designer或客户端控制台编辑器)创建消息
1. **添加个性化** — 插入动态字段、个性化块和条件内容
1. **配置设置** — 设置发件人地址、主题行、回复和传递参数
1. **运行投放分析** - Campaign验证内容、计算目标并检查错误
1. **发送校样** — 使用审批组测试您的电子邮件以验证渲染和内容
1. **发送或计划** — 立即发送到主目标或计划在以后的日期发送

**两个接口选项：**

* **Campaign Web UI** — 现代界面，具有增强的电子邮件Designer、AI助手和多语言功能
* **客户端控制台** — 具有高级定位和工作流程功能的传统界面

**提示：**&#x200B;使用Campaign Web UI通过现代设计工具创建更快速、更直观的电子邮件。 可使用客户端控制台执行复杂的定位或基于工作流的高级营销活动。

[创建您的第一封电子邮件](create-message.md) | [电子邮件设计指南](../send/email.md)

+++

+++ 如何计划一次投放？

利用Campaign，可计划投放以备将来发送，从而优化发送时间并协调活动。

**计划选项：**

* **投放属性** — 立即发送、计划特定日期/时间，或延迟小时/天
* **营销活动级别** — 协调营销活动中的所有投放
* **工作流调度程序活动** — 对于定期投放、复杂模式和事件触发的营销活动

Campaign还支持联系日期优化（每个收件人的最佳发送时间）和时区适应（所有收件人的相同本地时间）。

[计划投放发送](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ 我可以将附件添加到电子邮件吗？

是的。 Campaign支持静态附件（所有收件人的同一文件）和个性化附件（根据用户档案数据，每个收件人的文件不同）。 在投放属性的&#x200B;**[!UICONTROL Attachments]**&#x200B;部分中添加附件。

**重要注意事项：**

* 将附件保持在1MB以下以实现最佳可投放性
* 附件可能会触发垃圾邮件过滤器；请在发送之前进行全面测试
* 避免电子邮件客户端通常会阻止的文件类型(.exe、.zip、.js)
* 对于大型文件，请考虑改用跟踪的下载链接

在生产发送之前，使用安全文件格式(PDF、JPEG、PNG、DOCX)并使用种子地址进行测试。

[电子邮件附件指南](../send/email.md#attachments)

+++

+++ 如何在电子邮件投放中设置跟踪链接？

Campaign会自动将电子邮件中的所有URL转换为跟踪链接以监测收件人参与。 访问投放中的&#x200B;**[!UICONTROL Tracking]**&#x200B;部分，为每个链接配置跟踪设置。

**配置选项：**

* **启用/禁用跟踪** — 每个链接的控制跟踪
* **链接标签** — 为报表添加描述性名称(例如，“立即购买CTA”)
* **链接类别** — 按类型对链接进行分组以进行聚合分析
* **跟踪类型** — 跟踪点击次数、打开次数或两者

Campaign跟踪内容链接、镜像页面链接、取消订阅链接，并且可以包含用于电子邮件打开次数的可选跟踪像素。 使用有意义的标签和类别来简化报表并快速识别高性能内容。

[链接跟踪指南](../start/tracking.md) | [跟踪最佳实践](../send/send.md)

+++

+++ 我在哪里可以访问投放内容和跟踪日志？

直接从每个投放仪表板访问投放和跟踪日志。 在客户端控制台中，单击底部的&#x200B;**[!UICONTROL Delivery]**&#x200B;选项卡。 在Campaign Web UI中，导航到&#x200B;**[!UICONTROL Logs]**&#x200B;部分。

**可用日志：**

* **投放日志** — 已发送包含收件人详细信息和状态（已发送、挂起、失败）的邮件
* **跟踪日志** — 包含时间戳的收件人交互（打开、点击）
* **排除日志** — 已排除的收件人及其原因（隔离、类型规则、重复）
* **广播日志** — 完成发送历史记录，包括重试和错误

使用这些日志对投放问题进行故障诊断、分析参与和维护列表卫生。

[投放监视](../send/send.md) | [跟踪指南](../start/tracking.md)

+++

+++ 从何处获得投放报告？

Campaign提供全面的内置报告，用于分析投放性能、收件人参与和活动有效性。 从任何投放的&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡、营销活动仪表板或跨营销活动分析的全局&#x200B;**[!UICONTROL Reports]**&#x200B;菜单访问报告。

**关键报告包括：**

* **投放摘要** — 发送统计数据、打开次数、点击次数、退信次数和取消订阅次数
* **热门点击** — 链接性能的可视热图
* **跟踪指标** — 点进率和参与量度
* **无法投放** — 包含失败原因的退回分析

通过现代可视化图表，可在客户端控制台和Campaign Web UI中获取报表。

[内置传递报告](../reporting/delivery-reports.md) | [Campaign报告](../reporting/gs-reporting.md)

+++

+++ Adobe Campaign如何确定和管理隔离地址？

Campaign会自动管理隔离列表，以保护您的发件人信誉并提高可投放性。 隔离的地址会自动从将来的投放中排除，直到验证它们或从隔离中删除它们为止。

**隔离地址的原因：**

* **硬退回** — 永久传递失败（电子邮件地址无效、域不存在、邮箱已删除）
* **软退回阈值** — 重复的临时故障（邮箱已满，服务器暂时不可用）超过错误阈值
* **垃圾邮件投诉** — 将您的电子邮件标记为垃圾邮件的收件人
* **地址无效** — 地址有语法错误或验证失败
* **已列入阻止列表** — 选择退出或请求排除的收件人

**隔离的工作方式：**

Campaign跟踪每个地址的投放错误。 当某个地址达到配置的错误阈值时，将在分析期间自动将其隔离并从所有未来的投放中排除。 硬退回（永久失败）会立即隔离，而软退回在隔离之前需要多次失败。

**管理隔离的地址：**

在&#x200B;**[!UICONTROL Administration > Campaign Management > Non deliverables Management]**&#x200B;中访问隔离管理。 您可以查看隔离的地址、从隔离中手动删除已验证的地址，或配置自动清理规则。

**提示：**&#x200B;定期监视隔离列表。 提高隔离率通常意味着数据质量问题需要引起注意，然后才能影响发件人的声誉。

[隔离管理指南](../send/quarantines.md) | [退回管理](../send/delivery-failures.md)

+++

## 工作流 {#workflows}

了解如何在Adobe Campaign中使用工作流实现流程自动化、管理数据和编排复杂的营销活动。

+++ 创建工作流的主要步骤是什么？

创建工作流以在Campaign中自动执行营销流程：

1. **创建新工作流** — 导航到&#x200B;**[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]**&#x200B;或&#x200B;**[!UICONTROL Administration > Production > Technical workflows]**&#x200B;并单击&#x200B;**[!UICONTROL Create]**
1. **添加活动** — 从面板中拖放活动（定位、流量控制、操作活动）
1. **配置活动** — 双击每个活动以设置参数和定义逻辑
1. **连接活动** — 将活动与过渡链接以定义执行流
1. **测试和验证** — 使用工作流图检查逻辑，然后使用小型数据集进行测试
1. **执行** — 手动启动工作流或安排工作流自动执行

常见的工作流模式：数据导入、受众分段、投放发送、数据扩充和跨渠道编排。

**相关主题：**

[生成工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"} | [工作流活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ 如何在 Campaign 中导入数据？

根据您的需求，可使用多种方法将数据导入Campaign：

**简单文件导入：**

* 使用引导式界面进行一次性CSV/TXT导入向导
* 非常适合手动上传和快速数据加载

**基于工作流的导入：**

* 为复杂导入创建具有&#x200B;**[!UICONTROL Data loading (file)]**&#x200B;活动的工作流
* 添加数据转换、扩充和重复数据删除
* 计划从SFTP、本地目录或云存储定期导入

**API集成：**

* 使用REST API以编程方式从外部系统导入数据
* 非常适合于与CRM、电子商务或其他平台的实时同步

**最佳实践：**&#x200B;始终使用小样本进行测试，使用UTF-8编码，正确映射字段，应用重复数据删除规则，并安排在非高峰时间执行大量导入。

**相关主题：**

[导入最佳实践](../start/import.md) | [数据加载活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [循环导入工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ Campaign中常见的工作流用例有哪些？

活动工作流几乎可以自动化任何营销过程。 以下是最常见的用例：

**数据管理：**

* **导入和加载数据** — 从SFTP、API或云存储自动导入文件
* **数据清理** — 删除重复的配置文件，标准化格式，删除无效记录
* **数据扩充** — 使用外部数据或计算字段增强用户档案
* **列表管理** — 根据行为或条件自动更新区段

**营销活动自动化：**

* **欢迎系列** — 为新订阅者触发自动上线电子邮件
* **生日营销活动** — 在客户生日或周年纪念日发送个性化消息
* **重新参与** — 使用回馈营销活动定位非活动订阅者
* **放弃购买** — 向购物车中保留商品的客户发送提醒

**高级定位：**

* **A/B测试** — 拆分受众并测试不同的内容变体
* **动态分段** — 根据实时行为或属性创建区段
* **潜在客户得分** — 根据参与度计算和更新潜在客户得分
* **跨渠道编排** — 协调跨电子邮件、短信和推送的消息传递

**监视和警报：**

* **工作流监视** — 跟踪工作流状态并在失败时发送警报
* **投放监测** — 监测营销活动绩效和跳出率
* **数据库维护** — 自动清理旧日志和临时数据

**集成和同步：**

* **CRM同步** — 保持客户数据与Salesforce、Dynamics等同步
* **API集成** — 与电子商务平台、分析工具或自定义系统连接
* **事件触发的工作流** — 对来自网站或应用程序的实时事件做出反应

**相关主题：**

[工作流用例库](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [生成工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"} | [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [定位工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"} | [数据管理工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/about-data-management.html){target="_blank"}

+++

+++ 如何使用工作流更新 Campaign 数据？

在工作流中使用&#x200B;**[!UICONTROL Update data]**&#x200B;活动对数据库执行批量操作：

**支持的操作：**

* **插入** — 向数据库添加新记录
* **更新** — 根据匹配条件修改现有记录
* **插入或更新** — 添加新记录或更新现有记录（更新插入）
* **删除** — 删除符合特定条件的记录

**常见用例：**

* 在数据扩充后更新配置文件属性
* 与外部系统同步数据
* 维护基于行为的列表成员资格
* 清理和删除重复数据
* 应用批量状态更改（例如，选择退出、隔离）

配置协调键值以准确地匹配记录并选择更新选项（更新所有字段或仅更新空字段）。

**相关主题：**

[更新数据活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"} | [数据管理活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ 如何利用数据管理功能？

Campaign的数据管理活动可在工作流中执行复杂的数据操作，以实现复杂的定位和分段。

**密钥数据管理活动：**

* **扩充** — 将数据从相关表或外部源添加到工作群体
* **拆分** — 基于标准或随机分布的区段群体
* **重复数据删除** — 根据指定的键删除重复记录
* **更新数据** — 执行批量插入、更新或删除操作
* **更改维度** — 切换定向维度（例如，从收件人切换到订阅）
* **交集/并集/排除** — 组合或筛选多个群体

**常见用例：**

* 使用购买历史记录或行为数据丰富用户档案
* 针对不同的消息，将受众划分为多个组
* 在投放前删除重复项
* 集成来自外部数据库的数据（FDA — 联合数据访问）
* 创建复杂的多表查询和连接

这些活动允许您处理不直接位于主收件人表中的数据，并执行高级数据库操作。

**相关主题：**

[数据管理活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [定位工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"} | [扩充活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ 我能自动发送个性化的邮件吗？

是的。 工作流根据收件人数据、行为和自定义标准启用完全自动化的个性化消息营销活动。

**自动化工作流结构：**

1. **查询** — 根据条件选择目标受众
1. **扩充** — 从相关表中添加个性化数据
1. **拆分** — 针对不同的消息变体将分组归类（可选）
1. **投放** — 发送包含合并字段的个性化消息
1. **调度程序** — 为自动营销活动设置循环执行

**Personalization选项：**

* 使用收件人配置文件数据（名称、位置、首选项）
* 包括行为数据（购买历史记录、参与度分数）
* 根据区段或属性应用条件内容
* 计算动态值（会员积分、过期日期）

常见情景：生日营销活动、购物车放弃、忠诚度计划、回馈营销活动和事件触发的消息。

**相关主题：**

[Personalization指南](../send/personalize.md) | [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hans){target="_blank"} | [扩充活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ 如何使用工作流将受众分割到子集中？

使用&#x200B;**[!UICONTROL Split]**&#x200B;活动根据条件或分配规则将单个群体划分为多个子集。

**拆分方法：**

* **筛选条件** — 根据条件(如年龄组、位置、VIP状态)创建子集
* **百分比分布** — 为A/B测试随机拆分为相等百分比或自定义百分比
* **限制记录** — 限制子集大小（前N个记录、前X%、随机选择）
* **数据分组** — 为每个不同值创建一个子集（例如，每个国家/地区一个子集）

**常见用例：**

* 与控制组进行A/B测试
* 渠道偏好设置路由（电子邮件与短信）
* 渐进式转出（依次发送到10%和90%）
* 特定细分市场的报文传送服务(VIP、定期客户和新客户)
* 跨多个投放服务器进行负载平衡

每个拆分的子集流向单独的过渡，允许每个组进行不同的处理或投放。

**相关主题：**

[拆分活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"} | [A/B测试指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ 如何通过外部文件更新收件人数据？

是的。 使用工作流使用外部文件(CSV、TXT)中的值更新Campaign数据。

**工作流结构：**

1. **数据加载（文件）** — 加载外部文件并映射列
1. **扩充**（可选） — 添加其他数据或转换
1. **协调** — 定义密钥以将文件记录与数据库记录匹配（例如，电子邮件地址、收件人ID）
1. **更新数据** — 选择更新选项：
   * 仅更新匹配的记录
   * 更新现有字段或仅更新空字段
   * 如果没有找到匹配项，则插入新记录

**常见方案：**

* 通过CRM导出更新配置文件属性
* 从外部系统刷新订阅状态
* 同步忠诚度积分或客户得分
* 更新选择启用/选择禁用首选项
* 使用行为数据丰富用户档案

**最佳实践：**&#x200B;使用唯一标识符进行协调，在更新之前验证数据，使用小样本进行测试，并计划定期更新以进行同步。

**相关主题：**

[导入数据指南](../start/import.md) | [数据加载活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [更新数据活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

+++

+++ 如何识别和定位新的收件人？

将工作流与查询活动结合使用，以识别最近添加的收件人并触发自动欢迎营销活动。

**查询方法：**

在&#x200B;**[!UICONTROL Created date]**&#x200B;字段上创建查询筛选以选择在特定时间范围内（例如，最近24小时，上周）添加的收件人。

**自动欢迎工作流结构：**

1. **计划程序** — 每天运行或按特定时间间隔运行
1. **查询** — 选择自上次执行以来创建的收件人
1. **重复数据删除**（可选） — 确保没有重复项
1. **投放** — 发送欢迎邮件
1. **更新数据**（可选） — 将收件人标记为“已欢迎”

**具有聚合的高级技术：**

使用聚合函数动态识别最新添加项，并与之前处理的收件人进行比较，从而复杂地检测新收件人。

**相关主题：**

[查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [使用聚合](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"} | [欢迎计划](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何使用工作流活动？

活动工作流是使用四个主要类别的活动构建的，每个类别都有特定的用途：

**定位活动** — 定义和优化受众

* 查询、拆分、重复数据删除、扩充、交集、并集、排除
* 使用这些功能选择收件人、细分群体并组合数据源

**流控制活动** — 管理工作流逻辑和时间

* 调度程序、等待、测试、分支、AND — 连接、OR — 连接、跳转
* 控制执行流、添加条件和管理并行路径

**操作活动** — 执行操作并发送消息

* 投放、更新数据、数据加载（文件）、数据提取（文件）、JavaScript代码
* 执行数据库操作、文件传输和消息发送

**事件活动** — 对外部触发器做出反应

* 外部信号、文件收集器、HTTP传输、短信、电子邮件
* 处理传入数据和外部系统交互

要使用活动，请将它们从调色板拖到工作流画布中，双击以配置参数，并通过过渡将它们连接起来。

**相关主题：**

[定位活动引用](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [流量控制活动引用](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [操作活动引用](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"} | [事件活动引用](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}

+++

+++ 什么是工作流最佳实践？

按照以下最佳实践构建高效、可维护且可靠的工作流：

**设计和组织：**

* 为工作流和活动使用清晰的描述性名称
* 向文档逻辑添加标签和描述
* 以可视方式分组相关活动以提高可读性
* 将复杂的流程分解为多个较小的工作流

**性能优化：**

* 使用适当的过滤器限制查询结果大小
* 使用临时表进行中间数据存储
* 在非高峰时间安排资源密集型工作流
* 避免不必要的循环和过多的迭代

**错误处理和监视：**

* 向主管添加错误处理路径
* 为失败的工作流配置警报
* 完全执行前使用小数据样本进行测试
* 定期查看执行日志以了解性能问题

**维护和治理：**

* 存档或删除过时的工作流
* 版本控制工作流更改和文档修改
* 限制工作流的复杂性（目标为少于20个活动）
* 将工作流模板用于重复模式

**安全和数据管理：**

* 应用适当的操作员权限
* 通过工作流清理来清理临时数据
* 避免对值进行硬编码 — 使用变量和选项
* 定期审查和优化性能不佳的工作流

**相关主题：**

[工作流最佳实践指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [生成工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"} | [监视工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

## Campaign设置 {#settings}

使用正确的设置、集成和配置来配置Campaign实例，以优化营销操作。

+++ 我能改变 Campaign 界面的语言吗？

这取决于您使用的界面。 **客户端控制台**&#x200B;语言已修复，但&#x200B;**Campaign Web UI**&#x200B;允许个人用户更改其语言首选项。

**客户端控制台（桌面应用程序）：**

* 语言在创建实例时设置，无法更改
* 客户端控制台和服务器必须使用相同的语言
* 每个Campaign实例都以单一语言运行
* 对于英语安装，您可以选择美式英语还是英式英语（二者的日期和时间格式有所不同）

**Campaign Web UI：**

* 用户可以通过个人资料首选项独立更改其界面语言
* 日期、时间和数字的区域设置特定格式支持多种语言
* 您的Web UI语言首选项与Campaign服务器和客户端控制台语言无关


[在Campaign Web UI中更改语言](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [开始使用Campaign客户端控制台](connect.md)

+++

+++ 我可以将Campaign v8与其他Adobe解决方案结合使用吗？

是的。 Campaign v8与Adobe Experience Cloud解决方案无缝集成，以创建强大而统一的营销生态系统。 作为托管Cloud Service， v8旨在与Adobe的企业应用程序进行本机集成。

**可用的密钥集成：**

* **Adobe Experience Platform** — 利用统一的客户配置文件和实时数据
* **Adobe Analytics** — 跨渠道测量促销活动绩效和客户行为
* **Adobe Target** — 根据客户区段和行为对内容进行个性化
* **Adobe Experience Manager** — 集中内容创建和资源管理
* **Adobe Audience Manager** — 跨平台生成和激活受众区段

**优势：**&#x200B;统一的客户数据、一致的用户体验、简化的工作流程以及增强的个性化功能。

**设置：**&#x200B;与Adobe解决方案的集成需要Adobe Identity Management System (IMS)身份验证，该身份验证自动为Campaign v8托管云服务配置。

[Adobe Campaign集成](../connect/integration.md) | [与Adobe ID连接](connect.md)

+++

+++ 如何在 Campaign 实例上设置跟踪功能？

Campaign v8提供全面的跟踪，以监控收件人与消息的交互。 跟踪要求正确配置实例和消息设置。

**您可以跟踪的内容：**

* **电子邮件打开次数** — 通过跟踪像素（1x1透明图像）
* **链接点击次数** — 所有URL自动转换为跟踪链接
* **取消订阅** — 选择退出链接跟踪
* **镜像页面查看次数** — 收件人查看Web版本时
* **自定义参数** — 将跟踪数据添加到URL以进行高级分析

**关键配置步骤：**

1. 在实例设置(由Adobe for v8管理)中配置跟踪服务器URL
2. 在投放属性中启用跟踪
3. 自动为单个链接或所有链接设置跟踪
4. 定义跟踪有效期和日志保留

**最佳实践：**&#x200B;在发送到主受众之前，请始终使用验证测试跟踪，以确保链接正确工作并捕获数据。

[跟踪和监视投放](tracking.md) | [配置跟踪的链接](../send/email.md)

+++

+++ 如何配置电子邮件可投放性?

电子邮件可投放性取决于技术配置、内容质量和发件人信誉。 Campaign v8提供了一些工具和设置来优化收件箱放置。

**基本配置步骤：**

* **域身份验证** — 设置SPF、DKIM和DMARC记录以验证您的发送域
* **IP预热** — 逐渐增加新IP上的发送量以建立信誉
* **发件人配置** — 使用一致的、可识别的发件人地址和名称
* **退回管理** — 配置隔离规则以自动处理硬退回和软退回
* **反馈循环** — 设置投诉处理以管理垃圾邮件报告

**内容最佳实践：**

* 使用SpamAssassin测试电子邮件以检查垃圾邮件分数
* 保持适当的文本与图像比例
* 在HTML旁包含纯文本版本
* 始终提供取消订阅链接
* 避免垃圾邮件触发词语和过度大写

**监控：**&#x200B;使用Campaign的可投放性报告跟踪退回率、投诉率和收件箱位置。 对于Campaign v8，Adobe提供基础架构级别的可投放性优化。

[关于Campaign中的可投放性](../send/about-deliverability.md) | [可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}

+++

+++ 我能将 Campaign 连接到哪些外部数据库？

Campaign v8支持到主要企业数据库系统的联合数据访问(FDA)连接，使您能够利用现有的数据基础架构。

**支持的数据库：**

* **云数据库：** Amazon Redshift、Google BigQuery、Snowflake、Azure Synapse Analytics
* **企业数据库：** Oracle、Microsoft SQL Server、PostgreSQL、MySQL
* **数据仓库：** Teradata， Vertica， SAP HANA
* **大数据：**&#x200B;通过Hive的Hadoop

**特定于平台的注意事项：**&#x200B;支持的数据库版本和连接要求各不相同。 Campaign v8作为托管Cloud Service可能对外部数据库访问具有特定的网络和安全要求。

**重要提示：**&#x200B;请务必查看Campaign v8版本的官方兼容性矩阵，以确认对特定数据库版本的支持，并确保外部数据库连接器的许可正确。

[兼容性矩阵](compatibility-matrix.md) | [配置FDA连接](../connect/fda.md)

+++

+++ Adobe Campaign是否可以与CRM系统集成？

是的。 Campaign提供了本机CRM连接器，以便在Campaign和您的CRM系统之间无缝进行双向同步，从而确保跨平台保持一致的客户数据。

**支持的CRM系统：**

* **Salesforce** — 潜在客户、联系人、客户、商机、营销活动
* **Microsoft Dynamics 365** — 联系人、帐户、潜在客户、自定义实体
* 通过自定义API集成实现的其他CRM

**同步的内容：**

* **从CRM到Campaign：**&#x200B;联系人记录、帐户信息、潜在客户、自定义字段、分段数据
* **从Campaign到CRM：**&#x200B;投放日志、跟踪数据、参与量度、活动响应、订阅状态

**同步模式：**

* **已计划** — 按定义的间隔（每小时、每天）自动同步
* **手动** — 操作员触发的按需同步
* **实时** — 通过API即时更新（自定义开发）

**配置：**&#x200B;使用Campaign的内置CRM连接器助手将CRM字段映射到Campaign属性，选择要同步的表，并计划同步。 连接器处理冲突解决并维护数据一致性。

**最佳实践：**&#x200B;从只读同步开始到测试映射，然后启用双向同步。 监控同步日志是否有错误，并维护两个系统中的干净数据。

[CRM连接器配置](../connect/crm.md) | [工作流CRM活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html){target="_blank"}

+++

+++ 如何清除客户端控制台缓存？

清除客户端控制台缓存可解决许多常见的显示和功能问题。 缓存存储有时可能会损坏或过时的本地配置文件。

**何时清除缓存：**

* 新品牌元素（徽标、颜色）显示不正确
* 导出/导入函数意外失败
* 配置更改后未更新界面元素
* 性能问题或控制台响应缓慢
* 升级到新客户端控制台版本后

**清除缓存的步骤：**

1. 打开Campaign客户端控制台
2. 转到&#x200B;**[!UICONTROL File]**&#x200B;菜单
3. 选择&#x200B;**[!UICONTROL Clear the local cache...]**
4. 出现提示时确认操作
5. 重新启动客户端控制台



[安装和配置客户端控制台](connect.md)

+++

+++ 我可以配置用户界面设置吗？

是的。 Campaign管理员可以自定义用户界面，以匹配组织品牌并优化用户体验。 在实例或用户级别配置设置。

**您可以自定义的内容：**

* **品牌** — 徽标、颜色和视觉标识元素
* **默认视图** — 主页布局、文件夹结构可见性
* **列表配置** — 数据列表中的默认列、排序顺序和筛选器
* **导航** — 可用的菜单项和快捷键
* **区域设置** — 日期/时间格式、数字格式、时区
* **通知** — 电子邮件通知、应用程序内通知、工作流通知

**配置级别：**

* **实例范围** — 应用于所有用户（需要管理员权限）
* **特定于用户** — 个人首选项和个人设置
* **操作员组** — 所有组成员继承的设置


[配置UI设置](../config/ui-settings.md) | [用户权限](gs-permissions.md)

+++

+++ 能否创建自定义字段和表？

是的。 Campaign灵活的数据模型允许您使用自定义字段扩展内置模式并创建全新的表以满足特定业务需求。

**您可以自定义的内容：**

* **向现有表添加字段** — 使用会员积分、自定义偏好设置、外部ID扩展收件人表
* **创建新的自定义表** — 存储产品、交易、忠诚度层、自定义实体
* **定义关系** — 将自定义表链接到现有Campaign表
* **扩展表单** — 更新UI以显示和编辑自定义字段

**常见用例：**

* 存储其他配置文件属性(客户存留期值、首选商店、VIP状态)
* 使用自定义属性管理产品目录
* 跟踪自定义事件和交互
* 集成外部系统ID以进行数据同步
* 构建行业特定的数据模型（零售、金融、旅游）


[扩展数据模型](../dev/extend-schema.md) | [架构结构](../dev/schemas.md) | [数据模型最佳实践](../dev/datamodel-best-practices.md)

+++

## 报告 {#reporting}

深入了解Campaign的报告功能，包括内置的报告、自定义报告以及多维数据集等数据分析工具。

+++ 如何创建新报告？

Campaign会根据您的需求和技术专业知识提供多种报告选项。 您可以使用内置报告、在客户端控制台中创建自定义报告，或在Campaign Web UI中设计可视化仪表板。

**报告选项：**

* **内置报告** — 可从&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡访问的现成投放、营销活动和跟踪报告
* **描述性分析** — 具有向导驱动界面的任何数据的快速统计报告
* **自定义报告** — 技术用户使用报告编辑器生成的高级报告
* **Web UI仪表板** — 具有拖放界面的现代可视化报表和仪表板
* **多维数据集** — 多维数据探索和透视表分析

**重要信息：**&#x200B;营销活动专为营销运营报告而设计，而不是作为专门的业务智能工具。 为了满足复杂的分析需求，请考虑与Adobe Analytics或专用的BI平台集成。

[开始使用报告](../reporting/gs-reporting.md) | [Campaign Web UI报告](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ 如何设计并分享有关群体的统计报告？

使用Campaign的描述性分析工具，快速生成任何群体数据的统计报告。 此向导驱动功能可帮助您分析分布、趋势和模式，而无需技术专业知识。

**可以分析的内容：**

* 收件人人口统计和分段细分
* Campaign绩效指标和响应率
* 配置文件属性的分布（年龄、位置、首选项）
* 投放统计和参与模式
* 自定义字段值和数据质量量度

**如何创建：**&#x200B;选择任何列表或查询结果→右键单击→ **[!UICONTROL Actions > Analyze]** →选择分析类型（定性或定量）→配置显示选项→生成报告。

**共享：**&#x200B;将报告导出到Excel/PDF或保存到&#x200B;**[!UICONTROL Reports]**&#x200B;文件夹，以便具有相应权限的团队访问。

[描述性分析](../reporting/built-in-reports.md)

+++

+++ 如何根据我的数据设计高级报告？

Campaign提供两种创建高级自定义报表的方法：客户端控制台中的技术报表，用于进行复杂的分析；以及可视化功能板，用于更轻松地构建报表。

在客户端控制台中，您可以：

* 使用SQL查询和自定义计算构建复杂报表
* 创建包含图表、表和透视表的多页报表
* 设计条件格式和动态内容
* 访问完整的Campaign数据模型和外部数据库(FDA)


[创建自定义报告（客户端控制台）](../reporting/custom-reports.md)

+++

+++ 什么是多维数据集？如何将其用于报表？

多维数据集是多维数据结构，它使业务用户能够在没有技术技能的情况下通过透视表探索和分析Campaign数据。 将它们视为可简化复杂报表的预配置数据模型。


* 技术用户创建和配置多维数据集，这些多维数据集定义维度（时间、地理位置、渠道）和度量（打开、点击、收入）
* 企业用户在创建报表时选择多维数据集，并拖放维度以浏览数据
* 根据多维数据集配置自动聚合和计算数据
* 结果可以显示为透视表、图表或导出到Excel


[使用多维数据集浏览数据](../reporting/gs-cubes.md)

+++

+++ 我能利用在线调查的回答创建报告吗？

是！ Campaign包含一个“调查”模块，允许您创建在线调查表并生成关于调查响应的内置报告。

**重要信息：**&#x200B;调查管理在Campaign v8企业版(FFDA)部署中不可用。 [了解详情](../architecture/enterprise-deployment.md)。

**调查功能：**

* 创建具有多个页面和问题类型的在线问卷
* 收集数据库或本地变量中的响应
* 查看调查响应的实时跟踪
* 生成关于调查答案的专用报告（按问题细分、一般统计数据）
* 将调查响应导出到Excel、PDF或CSV以供进一步分析
* 在定位工作流中使用调查数据来个性化营销活动

**内置调查报告：**

* **常规报告** — 随时间变化的响应趋势、按来源和语言的分布
* **答案细分** — 每个问题的详细答案细分
* **文档报告** — 调查结构的可视表示形式

**高级分析：**

* 从&#x200B;**[!UICONTROL Responses]**&#x200B;选项卡访问调查响应并导出数据
* 在工作流中使用&#x200B;**[!UICONTROL Survey responses]**&#x200B;活动，根据收件人的回答来定位收件人
* 将调查数据与其他Campaign数据相结合，以实现分段和个性化
* 创建自定义报告和多维数据集以进行多维度调查分析


[调查入门](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [调查报告](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ 如何共享对报告的访问权限？

Campaign提供了灵活的选项，用于与不同的用户组共享报告，根据角色和责任控制可见性和访问权限。

**报表访问控制：**

* **文件夹权限** — 将报告放入具有用户组相应读/写权限的文件夹中
* **已命名的权限** — 分配查看、创建或修改报告的特定权限
* **显示上下文** — 定义报告的显示位置：在&#x200B;**[!UICONTROL Reports]**&#x200B;文件夹、营销活动选项卡或投放屏幕中
* **Web UI共享** — 通过Campaign Web UI与团队成员共享仪表板链接

**如何配置访问权限：**

1. 将报告保存到客户端控制台中的特定文件夹
2. 配置相关操作员组的文件夹访问权限
3. 定义报表属性：报表类型、显示上下文和可用性
4. 在更广泛的转出之前测试目标组中的用户访问权限

**最佳实践：**&#x200B;为具有定制访问权限的不同团队（营销、运营、管理）创建专用报表文件夹。 记录报表目的并刷新计划。

[自定义报告](../reporting/custom-reports.md) | [用户权限](gs-permissions.md)

+++

+++ 能否以不同格式导出报表？

是的，Campaign支持客户端控制台和Web UI报表的多种导出格式，从而能够轻松地与利益相关者共享并与其他工具集成。

**可用的导出格式：**

* **Excel (.xlsx)** — 最适合数据操作、进一步分析和透视表
* **PDF** — 适用于演示文稿、执行摘要和打印的报告
* **CSV** — 非常适合将数据导入到其他系统和BI工具中
* **OpenDocument (.ods)** — 开源电子表格格式
* **XML** — 用于系统集成和自动处理

**如何导出：**

* **客户端控制台：**&#x200B;打开报告→单击&#x200B;**[!UICONTROL Export]**&#x200B;按钮→选择格式→保存文件
* **Web UI：**&#x200B;打开仪表板→单击导出图标→选择格式→下载
* **自动导出：**&#x200B;使用工作流和导出活动安排定期导出

**最佳实践：**

* 使用Excel生成需要利益相关者分析和注释的报表
* 将PDF用于发送给执行官或存档以供遵从法规的静态报告
* 使用CSV与数据仓库或外部分析工具集成
* 测试导出的报表，确保格式化和数据准确性

[自定义报告](../reporting/custom-reports.md) | [Campaign Web UI报告](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## 开发人员 {#developers}

访问面向开发人员的技术信息，包括数据模型详细信息、架构、API和自定义功能。

+++ 什么是Campaign数据模型？

Campaign的数据模型是一种模式驱动的关系数据库结构，它定义了对营销数据进行组织和关联的方式。 它包含核心营销对象（收件人、投放、营销活动）的内置表，可以扩展以满足您的特定业务需求。

**关键数据模型概念：**

* **架构** — 描述表结构、字段和关系的XML定义
* **内置表** — 核心营销实体（收件人、投放、工作流、营销活动）
* **链接** — 表之间的关系(1-1、1-N、N-N)
* **枚举** — 下拉字段的预定义值列表
* **扩展** — 添加到标准模型中的自定义字段和表

**主内置架构：**

* **收件人(nms:recipient)** — 客户个人资料和联系信息
* **投放(nms:delivery)** — 电子邮件、短信和推送营销活动
* **工作流(xtk:workflow)** — 自动化流程
* **营销活动(nms:operation)** — 营销活动编排
* **跟踪日志** — 打开次数、点击次数和参与数据

**为什么重要：**&#x200B;了解数据模型对于创建工作流、构建查询、扩展架构和开发自定义集成至关重要。 基于模式的方法可确保数据一致性，并启用强大的查询功能。

[Campaign数据模型](../dev/datamodel.md) | [数据模型最佳实践](../dev/datamodel-best-practices.md)

+++

+++ 如何使用 Campaign 模式？

架构是Campaign数据结构的基础，以XML格式定义表、字段和关系。 了解架构对于自定义、集成和高级工作流开发至关重要。

**定义什么架构：**

* **表结构** — 数据库表及其对应的应用程序对象
* **字段属性** — 数据类型、标签、验证规则和默认值
* **关系** — 表（联接）与基数之间的链接
* **索引** — 针对查询性能优化了数据库
* **访问控制** — 用户可以查看和修改哪些字段

**正在处理架构：**

* 在客户端控制台中&#x200B;**查看架构：**&#x200B;通过&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;访问
* **扩展架构：**&#x200B;创建扩展架构（例如，`cus:recipient`扩展`nms:recipient`）以添加自定义字段而不修改核心架构
* **创建自定义架构：**&#x200B;为特定于业务的数据生成全新的表
* **更新数据库：**&#x200B;使用&#x200B;**[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;应用架构更改

**常见用例：**

* 向收件人表添加自定义字段（公司ID、忠诚度级别、偏好设置）
* 创建产品、商店或事务处理的自定义表
* 定义自定义表和内置表之间的关系
* 实施特定于业务的数据模型

**重要信息：**&#x200B;从不直接修改内置架构。 始终使用扩展架构以保持升级兼容性和Adobe支持。

[开始使用架构](../dev/schemas.md) | [扩展架构](../dev/extend-schema.md)

+++

+++ 如何使用自定义收件人表？

当您的业务需要不同的数据结构来进行定位时（例如，B2B帐户、订阅者、潜在客户或外部联系人），Campaign允许您使用自定义表而不是内置的收件人表。

**为什么使用自定义收件人表：**

* 定位B2B公司或组织单位，而不是个人联系人
* 将订阅者数据与主客户数据库分开
* 使用来自其他系统的现有客户表
* 使用单独的联系表实施多品牌体系结构
* 遵守特定的数据治理要求

**实施步骤：**

1. 创建用于定义收件人表结构的自定义模式
2. 包括必填字段（电子邮件、主键、排除标志）
3. 配置目标映射以将您的表与投放链接
4. 更新投放模板以使用新的目标映射
5. 调整工作流和查询以引用自定义表

**关键注意事项：**

* 自定义收件人表必须包含用于投放（电子邮件、排除项、跟踪）的必填字段
* 工作流和表单需要进行调整才能与自定义结构配合使用
* 某些内置功能可能需要自定义
* 在迁移生产活动之前，测试至关重要

**最佳实践：**&#x200B;在考虑自定义表之前，请先扩展标准收件人表。 自定义收件人表会增加复杂性，应仅在真正必要时使用。

[自定义收件人表](../dev/custom-recipient.md) | [目标映射](../audiences/target-mappings.md)

+++

+++ 在 Campaign 中定义查询的最佳实践是什么？

Campaign的查询编辑器是一款功能强大的可视化工具，可在不了解SQL的情况下构建数据库查询。 掌握该工具对于有效的定位、分段和数据分析至关重要。

**使用查询的位置：**

* **工作流活动** — 查询、拆分、更新数据、扩充活动
* **投放目标** — 定义营销活动的收件人群体
* **列表** — 创建动态或静态收件人列表
* **报告** — 生成自定义数据提取和分析
* **筛选器** — 创建可重复使用的定位条件

**查询最佳实践：**

* **开始简单** — 增量生成查询，在每个步骤进行测试
* **使用筛选维度** — 利用表(收件人→投放→跟踪日志)之间的关系
* **优化性能** — 索引频繁查询的字段，避免复杂的计算字段
* **利用预定义过滤器** — 重复使用和组合现有过滤器，以保持一致性
* **使用小样本进行测试** — 先验证查询逻辑，然后在完整数据库上运行
* **记录复杂查询** — 添加有关维护和知识传授的说明

**常见查询模式：**

* 定位打开了特定投放的收件人：筛选链接到收件人的跟踪日志
* 查找无效联系人：查询上次交货日期或跟踪活动
* 按行为分段：将投放、跟踪和用户档案标准结合使用
* 排除以前的收件人：使用集操作（并集、交集、排除）

**访问通用查询编辑器：** **[!UICONTROL Tools > Generic query editor]**，以便在工作流外部进行临时数据库探索和数据提取。

[查询编辑器](../start/query-editor.md) | [工作流中的查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ 如何导入数据包？

数据包允许您在实例之间导出和导入Campaign配置（架构、工作流、类型、过滤器）和数据。 这对于在组织间将配置从开发部署到生产或共享组件至关重要。

**可以打包的内容：**

* **配置对象** — 架构、工作流、类型规则、表单、筛选器
* **营销活动组件** — 投放模板、营销活动模板、内容块
* **应用程序设置** — 操作员、操作员组、文件夹结构
* **数据** — 收件人列表、种子地址、内容片段
* **自定义开发** - JavaScript代码、SQL脚本、Web应用程序


**包类型：**

* **用户包** — 您创建和导出的自定义配置
* **平台包** - Adobe提供的功能和更新
* **数据包** — 包含实际的数据记录，而不仅仅是结构

**最佳实践：**

* 始终从相同或更低版本的Campaign导出资源包
* 在生产之前在开发环境中测试包导入
* 文档包内容和依赖项
* 对包XML文件使用版本控制
* 在导入主包之前备份实例

[使用数据包](../dev/packages.md)

+++

+++ 在哪里可以找到Campaign v8 API的列表？

Campaign v8提供了全面的API文档，其中涵盖了SOAP API（适用于客户端控制台交互）和REST API（适用于现代集成）。 API参考包括所有可用的方法、参数和响应格式。

**Campaign API类型：**

* **SOAP API** - Campaign客户端控制台操作、架构操作和工作流控制的传统API
* **REST API** — 用于外部系统集成、配置文件管理和事件触发的现代HTTP API
* **JavaScript API** — 工作流活动和自定义业务逻辑的服务器端脚本API

**API文档资源：**

* **完整API引用：**&#x200B;包含方法签名、参数和示例的完整SOAP API文档
* **REST API指南：**&#x200B;用户档案、事件和组织单位的现代REST端点
* **JavaScript API：**&#x200B;工作流脚本和Web应用程序中可用的服务器端函数

**常见API用例：**

* 将Campaign与CRM、ERP或自定义应用程序集成
* 自动执行活动操作和工作流
* 在系统之间实时同步数据
* 构建自定义监控和警报解决方案
* 为Campaign数据和操作创建外部界面

**访问：**&#x200B;[Campaign v8 API文档](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hans){target="_blank"}

+++


+++ 如何从API监测工作流？

Campaign API允许您以编程方式控制和监视工作流的执行，从而实现外部监控系统、自动警报和自定义编排解决方案。

**您可以通过API执行的操作：**

* **开始工作流** — 以编程方式触发工作流执行
* **暂停/恢复工作流** — 控制工作流执行流
* **停止工作流** — 终止正在运行的工作流
* **查询工作流状态** — 检查工作流是否正在运行、已暂停或已完成
* **检索日志** — 访问工作流执行日志和错误消息
* **监视活动进度** — 跟踪单个工作流活动完成

**API方法：**

* `xtk:workflow#Start` — 启动工作流实例
* `xtk:workflow#Pause` — 暂停正在运行的工作流
* `xtk:workflow#Stop` — 停止工作流执行
* `xtk:workflow#GetState` — 获取当前工作流状态
* `xtk:workflow#GetLogs` — 检索执行日志

**常见用例：**

* 构建显示工作流运行状况的自定义监测仪表板
* 在工作流失败或运行时间过长时实施自动警报
* 从外部计划程序或事件系统编排工作流
* 跨多个Campaign实例创建工作流依赖项
* 生成自定义工作流执行报告

**最佳实践：**&#x200B;将API监视与工作流审核跟踪相结合，以实现全面的工作流管理。 使用外部监视工具跟踪工作流SLA和性能指标。

[通过API控制工作流](../dev/api/controlling-a-workflow.md)

+++

+++ 如何更新数据库结构？

修改Campaign模式（添加字段、创建表、更改数据类型）后，必须更新物理数据库结构以应用更改。 此同步确保数据库与您的架构定义匹配。

**需要数据库更新时：**

* 向现有架构添加新字段
* 创建自定义表或扩展内置表
* 修改字段属性（数据类型、长度、必需状态）
* 在表之间添加或删除链接
* 为查询优化创建新索引


**重要注意事项：**

* **首先备份** — 始终在结构更改之前备份数据库
* **开发中的测试** — 在生产之前验证开发环境中的架构更改
* **停机时间计划** — 大型结构更改可能需要短暂的维护时段
* 托管云服务的&#x200B;**&#x200B;** — 与Adobe支持部门协调重大更改
* **可逆性** — 某些更改（如删除字段）可能会导致数据丢失

**最佳实践：**&#x200B;使用架构版本控制和更改跟踪。 记录所有自定义架构修改，以进行维护和疑难解答。

[更新数据库结构](../dev/update-database-structure.md) | [扩展架构](../dev/extend-schema.md)

+++

+++ Campaign v8有哪些限制？

Campaign v8引入了体系结构更改（特别是在FFDA部署中），这些更改不仅显着提高了性能，而且还与Campaign Classic v7存在一些差异。 了解这些内容有助于规划迁移并设定适当的期望值。

**主要v8注意事项：**

* **FFDA架构** — 企业部署使用具有不同数据访问模式的云数据库(Snowflake)
* **设备更新** — 数据更新应在工作流中完成，不应通过API或直接数据库访问完成
* **实时写入** — 已针对批处理操作（而非高频单个更新）进行优化
* **数据模型** — 某些架构自定义需要不同的方法
* **外部数据库访问** - FDA（联合数据访问）配置与v7不同

**功能在FFDA部署中不可用：**

* 调查（在标准v8部署中提供）
* 营销资源管理(MRM)
* 某些特定的连接器配置

**迁移注意事项：**

* 使用直接数据库写入的自定义代码需要重构
* API集成可能需要进行调整才能进行批量处理
* 工作流应遵循用于数据操作的FFDA最佳实践
* 测试对于验证自定义开发至关重要

**重要信息：**&#x200B;随着Adobe继续增强v8，这些限制会不断演变。 请参阅最新文档以了解当前状态和路线图。

[Campaign v7到v8的迁移](../start/v7-to-v8.md#limitations) | [FFDA架构](../architecture/enterprise-deployment.md)

+++

## 隐私 {#privacy}

了解Adobe Campaign如何帮助您遵守GDPR和CCPA等隐私法规以及管理数据主体请求。

+++ Campaign中的关键隐私概念是什么？

Campaign通过用于管理数据主体权限、同意和数据保留的工具，帮助您遵守隐私法规(GDPR、CCPA、PDPA、LGPD)。 关键概念包括隐私法规、个人数据识别、数据主体权限（访问、删除、可移植性）、同意管理和数据保留策略。

作为“数据控制者”，您负责处理数据主体请求、维护同意记录并确保透明的数据使用。

[隐私管理](../start/privacy.md)

+++

+++ 如何确保Campaign中的隐私合规性？

Campaign提供了隐私合规工具，但法律责任由您承担。 与您的隐私项目的法律顾问合作。

**基本操作：**

* 建立处理数据主体请求（访问、删除）的流程
* 通过时间戳和范围跟踪实施同意管理
* 在所有营销电子邮件中包含取消订阅链接
* 审核数据源并删除未使用的数据
* 应用最低权限访问控制

Campaign提供隐私核心服务集成、同意跟踪、自动删除工作流和合规性审核跟踪。

[隐私管理](../start/privacy.md)

+++

+++ 如何在Campaign中收集和管理用户同意？

有效同意需要有效、具体、知情且可撤销的同意。 用户必须执行明确的操作 — 无预选框或静默作为同意。 出于不同目的（未捆绑）单独提供同意，提供明确的解释，并维护带有时间戳的记录。

**最佳实践：**&#x200B;提供详细的选择加入选项，定期刷新同意，使首选项中心易于访问，并在建立信任时提供同意框架。

Campaign中的&#x200B;**技术实现：**

Campaign提供订阅服务、首选项中心、选择退出标记以及用于跟踪同意的自定义同意字段。

* 扩展同意字段（日期、类型、来源）的收件人模式
* 为每种同意类型创建订阅服务
* 构建首选项中心Web窗体
* 使用工作流在定位中强制同意
* 维护审核跟踪

请咨询法律顾问，以确保您的实施符合法规要求。

[订阅服务](../start/subscriptions.md) | [隐私和同意](../start/privacy.md#consent-retention-roles) | [隐私管理](../start/privacy.md)

+++

+++ 处理删除请求时会删除哪些数据？

Campaign会自动删除链接到数据主体的所有数据：收件人用户档案、投放和跟踪日志、具有所有权关系的自定义数据、订阅历史记录以及Web跟踪数据。

**工作方式：** Campaign删除架构定义中指向收件人的链接具有`integrity="own"`的所有数据，确保跨相关表进行级联删除。

您可以通过修改架构中的链接完整性来自定义删除范围，但请先咨询法律顾问。 删除是永久性的，无法撤消。

[隐私管理](../start/privacy.md) | [架构链接](../dev/schemas.md)

+++

+++ 隐私删除是否会影响我的投放报告？

没有。促销活动报表基于预先计算的汇总量度（发送总数、打开次数、点击次数），而不是针对单个日志的实时查询。 删除单个收件人数据不会更改历史聚合统计信息。

总体投放统计信息和性能量度保持不变，而单个跟踪日志和个人详细信息将被删除。 这样，您就可以在尊重数据主体权利的同时，维护营销分析。

[隐私管理](../start/privacy.md) | [报告](../reporting/gs-reporting.md)

+++

+++ 如何阻止重新导入已删除的数据？

您必须从所有源系统中删除数据，而不仅仅是Campaign。 数据通常从外部系统（CRM、电子商务、数据仓库）流动。

**必需的操作：**&#x200B;识别所有数据源、从源系统中删除、添加到排除/禁止列表、更新导入工作流以遵循删除标志，并记录该过程。

作为数据控制者，您负责在整个技术生态系统中完全删除数据。

[隐私管理](../start/privacy.md) | [导入工作流](../config/workflows.md)

+++

+++ 已删除的用户能否再次选择加入？

是的。 删除后，数据主体可以再次选择加入。 Campaign会创建一个全新的收件人记录，其中不包含指向之前已删除数据的链接 — 该用户档案从头开始创建。

Campaign的审核记录会记录删除事件和新用户档案的创建，以展示合规性，并显示在删除后会免费提供新的选择加入。

[隐私管理](../start/privacy.md) | [订阅](../start/subscriptions.md)

+++

## 仍然需要帮助？ {#get-help}

找不到您要查找的内容？ 以下是帮助您成功使用Adobe Campaign v8的其他资源。

### 社区支持

与其他Campaign用户和Adobe专家联系，分享知识并获得答案。

* **[Adobe Campaign社区](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** — 提问、共享解决方案并与Campaign社区建立联系
* **[Experience League论坛](https://experienceleaguecommunities.adobe.com/){target="_blank"}** — 浏览所有Adobe产品的讨论
* **[Campaign社区办公时间](https://experienceleague.adobe.com/){target="_blank"}** — 与Adobe专家一起参加实时会议

### 文档与学习

访问全面的指南、教程和培训材料。

* **[Campaign v8文档主页](../campaign-home.md)** — 完整产品文档
* **[Campaign教程](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html){target="_blank"}** — 逐步视频指南和实践教程
* **[新增功能](whats-new.md)** — 最新特性和功能
* **[发行说明](release-notes.md)** — 当前和以前的发行信息
* **[版本和升级](upgrades.md)** — 了解Campaign的版本、升级以及如何检查您的版本
* **[最佳实践](delivery-best-practices.md)** — 针对常见任务的推荐方法

### 技术资源

查找详细的技术文档和开发人员资源。

* **[Campaign API](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hans){target="_blank"}** — 完整API参考文档
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.en)** — 向文档投稿
* **[技术说明](https://experienceleague.adobe.com/zh-hans/docs/campaign/technotes-ac/technotes-home){target="_blank"}** — 深入的技术文章
* **[兼容性矩阵](compatibility-matrix.md)** — 支持的系统和版本
* **[版本和升级常见问题解答](upgrades.md#upgrades-faq)** — 检查您的版本并了解升级情况

### 支持和服务

从Adobe支持团队获取帮助并管理您的实例。

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** — 记录支持案例并管理用户
* **[Adobe客户关怀](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** — 联系支持团队
* **[控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans){target="_blank"}** — 管理您的Campaign实例设置
* **[系统状态](https://status.adobe.com/){target="_blank"}** — 检查Adobe服务状态

### 培训和认证

通过官方的Adobe培训和认证计划提升您的技能。

* **[Adobe数字学习服务](https://learning.adobe.com/){target="_blank"}** — 官方讲师指导课程和自学课程
* **[Adobe Campaign认证](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** — 通过专业认证验证您的专业知识
* **[Experience League学习路径](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** — 引导式学习历程

### 其他有用资源

* **[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=zh-Hans){target="_blank"}** - Classic v7用户参考
* **[Campaign Web UI文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}** — 新Web界面指南
* **[可投放性最佳实践](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}** — 优化电子邮件投放
* **[产品更新](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current){target="_blank"}** — 最新Adobe Experience Cloud更新

**上次更新日期：** 2025年11月 | **适用于：** Campaign v8.6及更高版本

*发现错误或想提出改进建议？ [在GitHub上编辑此页面](https://github.com/AdobeDocs/campaign.en/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

