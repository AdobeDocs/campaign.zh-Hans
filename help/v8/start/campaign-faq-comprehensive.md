---
title: Campaign v8 常见问题解答
description: 获取有关设置、配置、消息传递、工作流等的常见Adobe Campaign v8问题的答案
feature: Overview
role: User
level: Beginner
keywords: 常见问题解答， Campaign v8，问题，回答，帮助，支持，故障排除
hide: true
hidefromtoc: true
source-git-commit: 09911f7112a89b2cc5235b71bbcaa963ae739aed
workflow-type: tm+mt
source-wordcount: '9652'
ht-degree: 28%

---

# 常见问题解答 {#faq}

快速获取有关Adobe Campaign v8的最常见问题的答案。 无论您是刚刚入门还是正在寻找高级配置帮助，您都可以找到以下按主题排列的答案。

**是营销活动的新用户？**&#x200B;以[一般问题](#general)和[关键概念](#key-concepts)开始。\
**需要技术帮助？**&#x200B;检查[开发人员](#developers)和[促销活动设置](#settings)。\
**找不到您的答案？**&#x200B;访问我们的[社区论坛](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}或[联系支持人员](#get-help)。

>[!TIP]
>
>使用Ctrl+F(在Mac上按Cmd+F)在此页面上搜索特定关键词。 单击任意问题以展开答案。


## 一般问题 {#general}

获取有关Adobe Campaign v8的最常见问题的答案，包括如何连接、升级和获取支持。

+++ 如何连接到 Campaign v8？

您需要下载并安装 Campaign 客户端控制台才能连接到 Adobe Campaign。

[单击此处以了解详情](connect.md)。

从Campaign v8.6版本开始，您可以访问&#x200B;**Campaign Web用户界面**，该界面可通过集中式Adobe Experience Cloud环境使用。 Experience Cloud是Adobe的集成式数字营销应用程序、产品和服务系列。

[在此页面中](campaign-ui.md#ac-web-ui)了解如何连接到 Adobe Experience Cloud 并访问 Adobe Campaign Web 界面。

请参阅 [Adobe Campaign Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}以了解详情。

>[!TIP]
>
>**连接问题疑难解答：**
>
>* 验证您的Adobe ID凭据是否正确
>* 确保您的客户端控制台版本与服务器版本匹配
>* 检查网络连接和防火墙设置
>* 如果遇到问题，清除客户端控制台缓存
>* 联系管理员以验证用户权限

**相关主题：**

* [安装客户端控制台](connect.md)
* [Campaign用户界面](campaign-ui.md)
* [用户权限](gs-permissions.md)

+++

+++ Campaign v8是否可以安装在内部部署或混合环境中？

Campaign v8 仅以托管云服务的形式提供，并完全由 Adobe 托管。

+++

+++ 如何将 Campaign 升级到最新版本？

Adobe Campaign 会定期更新。每年都会发布包含新功能、改进和修复的次要版本。此外，我们还定期发布仅包含累积修复的内部版本。

这种定期更新旨在让您掌握最新、最充分的信息，保持环境的安全，并改进您对我们产品的体验。这就是为什么我们认为运行最新版本的 Adobe Campaign 至关重要的原因。

>[!NOTE]
>
>作为托管Cloud Services用户，您的实例会由Adobe通过新版本升级。

+++

+++ 如何改进电子邮件可投放性？

电子邮件可投放性是每个发件人的营销计划取得成功的重要因素，其特点是不断变化的标准和规则。想要在这个数字化的世界中取得成果，就必须定期调整电子邮件策略，并考虑关键可投放性趋势，以便最好地吸引受众。

请参阅本指南以了解[可投放性最佳实践](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}

要了解如何在 Campaign 中实施可投放性，请参阅[本指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=zh-Hans){target="_blank"}

>[!TIP]
>
>**关键可投放性提示：**
>
>* 维护干净的电子邮件列表并定期删除不活动的订阅者
>* 使用双重选择加入确保参与的收件人
>* 监测发件人信誉和IP信誉
>* 使用SPF、DKIM和DMARC验证电子邮件
>* 立即遵循取消订阅请求
>* 在发送给大型受众之前测试电子邮件

**相关主题：**

* [关于可投放性](../send/about-deliverability.md)
* [控制消息内容](../send/control-message-content.md)
* [监测投放能力](../send/monitoring-deliverability.md)
* [SpamAssassin](../send/spamassassin.md)

+++

+++ 如何确认我的投放已成功发送，并且未出现错误？

Adobe Campaign 提供了一组仪表板和工具来监测电子邮件投放。

[阅读 Campaign Classic v7 文档以了解](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=zh-Hans){target="_blank"}如何确认邮件已发送、监测执行情况并在发生错误时采取行动。

+++

+++ 是否能监测工作流的执行？

请参阅[此页面](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}以了解如何监测 Campaign 工作流执行情况

+++

+++ 哪些系统和组件与 Campaign v8 兼容？

在 [Adobe Campaign 兼容性矩阵](compatibility-matrix.md)中，您可以获得支持 Campaign 最新版本的所有系统和组件的列表。

+++

+++ 如何下载Campaign？

可以从 Adobe 下载中心获取安装程序和客户端控制台。

作为管理员用户，请访问Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/zh-hans/campaign.html){target="_blank"}下载Adobe Campaign。

在此页面[上了解有关分发中心](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hans){target="_blank"}的更多信息。

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

可通过 Campaign 客户端控制台的 **Help > About...** 菜单查看您的[版本号和构建号](connect.md#ac-version)。

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

* [权限入门](gs-permissions.md)
* [管理用户权限](manage-permissions.md)
* [添加文件夹权限](folder-permissions.md)

+++

+++ 如何确保Campaign的隐私合规性？

Adobe Campaign提供一套工具，可帮助您确保符合GDPR、CCPA和其他隐私法规的隐私合规性。

[了解更多](../start/privacy.md)有关隐私管理以及Adobe Campaign为帮助您遵守隐私要求而提供的工具和功能。

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

* [工作流快速入门](../config/workflows.md)
* [构建您的第一个工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}
* [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}
* [监测工作流执行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

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

* [创建您的第一个投放](create-message.md) — 分步指南
* [使用投放模板](../send/create-templates.md) — 节省模板时间
* [投放最佳实践](delivery-best-practices.md) — 成功建议
* [定义电子邮件内容](../send/defining-the-email-content.md) — 内容创建选项
* [预览和验证](../send/preview-and-proof.md) — 发送前测试
* [配置并发送](../send/configure-and-send.md) — 发送的最后步骤
* [个性化内容](../send/personalize.md) — 添加动态个性化

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

* [开始使用短信](../send/sms/sms.md) — 完整的短信指南
* [短信投放设置](../send/sms/sms-delivery-settings.md) — 配置选项
* [SMPP外部帐户设置](../send/sms/smpp-external-account.md) — 提供程序设置
* [创建短信投放](../send/sms/create-sms.md) — 分步创建
* [短信内容](../send/sms/sms-content.md) — 内容设计指南
* [发送短信验证](../send/sms/sms-proofs.md) — 测试短信
* [监控SMS](../send/sms/sms-monitor.md) — 跟踪和分析投放

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

* [创建并发送推送通知](../send/push.md) — 完成推送指南
* [配置推送通知渠道](../send/push-settings.md) — 渠道设置
* [设计Android富推送](../send/rich-push-android.md) - Android富通知
* [设计iOS富推送](../send/rich-push-ios.md) - iOS富通知
* [使用数据收集进行配置](../send/push-data-collection.md) — 新版的修订集成方法
* [跟踪和监视](tracking.md) — 分析推送性能

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

* [跟踪和监控消息](tracking.md)
* [投放报告](../reporting/delivery-reports.md)
* [了解投放失败](../send/delivery-failures.md)
* [配置跟踪的链接](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}(Campaign Classic v7文档)

+++

+++ 如何翻译错误消息？

错误消息是用外文显示的？[此页面](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hans){target="_blank"}中列出了所有错误消息及其译文。

+++

+++ 我能在 Campaign 中创建 Web 窗体并收集回答吗？

是的。 使用&#x200B;**Campaign Web Applications和Forms**（客户端控制台）创建Web表单，以便完全控制表单逻辑和验证；或者使用&#x200B;**Campaign登陆页面**(Web UI)，为订阅和商机开发提供现代化的拖放界面。 两者都会将数据直接收集到Campaign中，并集成到工作流中以自动执行操作。

[了解有关Web应用程序和表单的更多信息](../dev/webapps.md) | [Campaign Web UI登陆页面](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8与先前版本 {#v7-differences}

了解Campaign v8与先前版本（Classic v7和Standard）之间的主要差异，包括架构、部署、迁移路径和功能更改。

+++ Campaign v8与先前版本之间有何主要区别？

Campaign v8是Adobe Campaign的完全再造，专为现代云原生架构而设计，与Campaign Classic v7和Campaign Standard相比有显着改进：

**部署模型：**

* **v8：**&#x200B;仅限Managed Cloud Services — 由Adobe完全托管和管理
* **v7/Standard：**&#x200B;内部部署、混合或托管选项可用
* **优点：**&#x200B;零基础架构管理、自动扩展、企业级安全性

**架构和性能：**

* 使用PostgreSQL数据库的&#x200B;**v8：**&#x200B;增强型完全FDA (FFDA)架构
* **v8：**&#x200B;已针对处理数百万个配置文件和高容量发送进行了优化
* **v8：**&#x200B;查询性能和数据处理速度得到了显着改进
* **好处：**&#x200B;大型操作和复杂营销活动的性能更高

**用户界面：**

* **v8：**&#x200B;新的Campaign Web用户界面以及客户端控制台
* **v8：**&#x200B;响应式现代设计，用户体验得到改进
* **v8：**&#x200B;简化的营销活动创建和管理工作流
* **优势：**&#x200B;更快上手、更轻松地执行营销活动、更易于访问

**升级和维护：**

* **v8：**&#x200B;由Adobe管理的自动升级 — 始终在最新的稳定版本上
* **v7：**&#x200B;需要手动升级规划和执行
* **优点：**&#x200B;减少了维护负担，可立即访问新功能，无需停机

**API和集成：**

* **v8：**&#x200B;具有增强的性能和可靠性的现代REST API
* **v8：**&#x200B;与Adobe Experience Cloud解决方案无缝集成
* **优势：**&#x200B;更简单的集成、更好的互操作性、现代开发实践

[了解关于Campaign v8关键功能的更多信息](whats-new.md)

**相关主题：**

* [从 Campaign Classic v7 到 v8](v7-to-v8.md)
* [从 Campaign Standard 到 v8](acs-to-v8.md)
* [Campaign v8 架构](../architecture/architecture.md)
* [护栏和限制](ac-guardrails.md)

+++

+++ 我应该从Campaign Classic v7还是Campaign Standard迁移到v8？

**Campaign v8非常适合于需要：**&#x200B;的组织

* **大量营销活动** — 发送数百万封邮件，其性能和可靠性都得到了提高
* **企业可扩展性** — 无性能顾虑地扩展数据库和营销活动
* **新式Web用户界面** — 直观、响应式的Campaign Web UI，可加快活动创建并改善用户体验
* **云原生优势** — 利用自动更新、托管基础设施和弹性扩展
* **长期支持** - Campaign v8是Adobe的具有扩展支持的战略平台，而以前的版本将在未来几年内停止支持
* **减少IT开销** — 消除基础架构管理和升级计划

**何时考虑迁移：**

* 您的当前Campaign实例处理大量数据（数百万个配置文件）
* 您遇到复杂工作流或定位的性能问题
* 您希望降低基础架构管理和维护成本
* 您需要与其他Adobe Experience Cloud解决方案无缝集成
* 您仍然在计划重大升级或基础架构更新
* **您需要经得起未来考验的技术** - Campaign Classic v7和Campaign Standard将终止支持，使v8成为战略性长期解决方案
* **您的团队需要新式界面** — 新的Campaign Web UI为营销人员提供了更直观、更易访问的体验

**迁移注意事项：**

* 自动迁移尚不可用 — Adobe提供迁移支持和指南
* v8仅限于Managed Cloud Service（无内部部署或混合部署）
* 某些技术实施可能与v7不同 — 请查看[兼容性矩阵](compatibility-matrix.md)
* 数据迁移和测试需要规划和资源

**后续步骤：**
请联系您的Adobe代表：

* 评估您的迁移准备情况和时间表
* 了解用例的特定优势
* 规划迁移策略和资源分配
* 访问迁移工具和支持

**相关主题：**

* [从Campaign Classic v7到v8](v7-to-v8.md) - v7用户的详细比较和迁移指南
* [从Campaign Standard到v8](acs-to-v8.md) — 标准用户的迁移路径
* [Campaign v8功能矩阵](../start/compatibility-matrix.md)

+++

+++ 哪些Campaign Classic v7功能与v8不同或不可用？

Campaign v8通过增强功能提供了大多数Campaign Classic v7功能，但某些功能会因云原生架构而发生更改：

**在v8中不可用：**

* **内部部署和混合部署** - v8仅为托管式云服务
* **直接数据库访问** — 改用提供的API和工具
* **客户管理的基础结构** - Adobe管理所有的基础结构

**v8中的不同实施：**

* **技术工作流** — 某些已针对云架构进行了优化，可能会工作方式不同
* **数据库结构** — 增强的FFDA架构可能需要架构调整
* **自定义集成** — 可能需要更新基于云的架构
* **低级自定义项** — 有些自定义项在托管环境中需要不同的方法

在v8中增强或替换了&#x200B;**：**

* **内部版本升级** — 现在为自动(Adobe托管)而不是手动
* **性能优化** — 由Adobe基础架构优化处理
* **安全修补程序** — 由Adobe自动应用
* **备份和恢复** — 作为服务的一部分由Adobe管理


**重要信息：**&#x200B;大多数营销和运营功能在v8中可用并得到了改进。 Adobe在云环境中管理技术和基础架构级别的功能。

[查看完整的兼容性矩阵](compatibility-matrix.md)以了解详细信息。

**相关主题：**

* [护栏](ac-guardrails.md)
* [v7到v8过渡指南](v7-to-v8.md)

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

>[!TIP]
>
>将工作流用于需要定期更新的列表，以及需要手动创建的一次性分段列表。

[创建受众](../audiences/create-audiences.md) | [列出更新活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ 如何在发送邮件前删除重复的群体？

在投放之前使用工作流中的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活动删除重复的收件人。 将其放在您的&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Delivery]**&#x200B;活动之间，然后选择您的重复数据删除条件（通常是电子邮件地址或收件人ID）以及要保留的记录。

>[!TIP]
>
>发送之前请始终删除重复项，以确保每个人仅收到您的消息一次。

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

>[!TIP]
>
>要获得最佳的电子邮件设计体验，请使用Campaign Web UI中的&#x200B;**电子邮件Designer**，它提供了现代化的拖放功能和内置的响应模板，而不是导入原始HTML。

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

>[!NOTE]
>
>AI助手仅在Campaign Web UI中可用，当前仅支持英语。 用户需要适当的权限，并且必须同意用户协议。

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


>[!TIP]
>
>使用Campaign Web UI可通过现代设计工具更快、更直观地创建电子邮件。 可使用客户端控制台执行复杂的定位或基于工作流的高级营销活动。

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

>[!TIP]
>
>定期监控隔离列表。 提高隔离率通常意味着数据质量问题需要引起注意，然后才能影响发件人的声誉。

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

* [构建工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}
* [工作流活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"}
* [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

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

* [导入最佳实践](../start/import.md)
* [数据加载活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}
* [循环导入工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ 是否能监测工作流的执行？

是的。 Campaign提供全面的工作流监控功能，以跟踪执行情况、发现问题和优化性能。

**监视选项：**

* **工作流仪表板** — 查看实时执行状态、进度和活动状态
* **执行日志** — 访问每个活动和过渡的详细日志
* **审核跟踪** — 跟踪工作流修改和执行历史记录
* **警报和通知** — 针对失败或特定情况设置电子邮件警报

**主要监视功能：**

* 视觉状态指示器（待定、进行中、已完成、失败）
* 执行时间跟踪以实现性能优化
* 用于疑难解答的活动级错误消息
* 根据需要暂停、停止或重新启动工作流

从&#x200B;**[!UICONTROL Administration > Production > Objects created automatically > Campaign workflows]**&#x200B;或直接从工作流仪表板访问监控。

**相关主题：**

* [监测工作流执行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}
* [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [开始工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html?lang=zh-Hans){target="_blank"}

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

* [更新数据活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}
* [数据管理活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

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

* [数据管理活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"}
* [定位工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"}
* [扩充活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

* [Personalization指南](../send/personalize.md)
* [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hans){target="_blank"}
* [扩充活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

* [拆分活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"}
* [A/B测试指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

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

* [导入数据指南](../start/import.md)
* [数据加载活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}
* [更新数据活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

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

* [查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}
* [使用聚合](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}
* [欢迎计划](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hans){target="_blank"}

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

* [定位活动引用](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}
* [流量控制活动引用](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}
* [操作活动引用](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}
* [事件活动引用](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}

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

* [工作流最佳实践指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [构建工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}
* [监测工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

## Campaign设置 {#settings}

使用正确的设置、集成和配置来配置Campaign实例，以优化营销操作。

+++ 我能改变 Campaign 界面的语言吗？

创建实例时可选择 Campaign 语言。之后将无法改变语言设置。如需详细信息，请参阅[此部分](../start/connect.md)。

Adobe Campaign用户界面提供多种语言版本：英语、法语、德语、日语等。 请注意，客户端控制台和服务器必须使用相同的语言设置。每个 Campaign 实例只能以一种语言运行。

如果是英语，在安装 Campaign 时可以选择美式英语还是英式英语：二者的日期和时间格式有所不同。

+++

+++ 我可以将Campaign v8与其他Adobe解决方案结合使用吗？

您可以将 Adobe Campaign 的投放功能和高级活动管理功能与帮助您个性化用户体验的解决方案结合起来。

[了解如何使用其他Adobe解决方案](../connect/integration.md)和[如何在Campaign中设置IMS](../start/connect.md)。

+++

+++ 如何在 Campaign 实例上设置跟踪功能？

作为经验丰富的用户，您可以在Campaign实例上配置跟踪功能。

[了解详情](../start/tracking.md)。

+++

+++ 如何配置电子邮件可投放性?

除了[Adobe可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}之外，请查阅可投放性技术建议，了解如何配置实例以最大程度地提升Campaign投放能力。

[了解详情](../send/about-deliverability.md)。

+++

+++ 如何实施内容批准？

借助 Campaign，您能够以协作模式为营销活动的主要步骤设置审批流程。对于每个活动，您可以批准投放目标、内容和成本。负责批准工作的Adobe Campaign操作员收到电子邮件通知后，可通过控制台或Web连接批准或拒绝批准相关请求。

[了解详情](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=zh-Hans){target="_blank"}并了解在Campaign中实施投放内容审批的步骤。

+++

+++ 如何访问存储在外部数据库中的数据？

Adobe Campaign 提供了联合数据访问 (FDA) 选项，以处理存储在一个或多个外部数据库中的信息：无需改变 Adobe Campaign 数据的结构就可以访问外部数据。

[了解详情](../connect/fda.md)。

+++

+++ 我能将 Campaign 连接到哪些外部数据库？

[兼容性表](compatibility-matrix.md)中列出了通过联合数据访问 (FDA) 与 Campaign 兼容的外部数据库。

+++

+++ Adobe Campaign是否可以与CRM系统集成？

Adobe Campaign 提供各种 CRM 连接器，可将您的 Adobe Campaign 平台链接到第三方系统。通过这些 CRM 连接器，您可以同步处理联系人、帐户、购买等。您可以使用这些 CRM 连接器轻松地将您的应用程序与各第三方和商务应用程序相集成。

通过这些连接器，可快速轻松地集成数据：Adobe Campaign提供了一个专用助手，用于从CRM中提供的表中收集和选择数据。 并且可确保双向同步处理，让整个系统中的数据随时保持最新。

[了解更多](../connect/crm.md)如何将CRM工具与Adobe Campaign同步。

+++

+++ 如何清除客户端控制台缓存？

如果您遇到新徽标未正确反映或者导出数据等问题，您可能需要清除客户端控制台缓存。

注销并关闭客户端控制台。 根据您的操作系统导航到以下位置：

* Windows： `C:\Users\<Username>\AppData\Roaming\Neolane\NL_5\`
* Mac： `~/Library/Application Support/Neolane/NL_5/`

删除XML配置文件（保留`nlclient_cnx.xml`），然后重新登录到客户端控制台。

+++

+++ 我可以配置用户界面设置吗？

是，作为管理员，您可以为用户自定义Campaign UI设置。 [了解详情](../config/ui-settings.md)。

+++

+++ 能否创建自定义字段和表？

是的，Campaign v8允许您使用自定义字段和表扩展数据模型。 了解如何[扩展架构](../dev/extend-schema.md)。

+++

## 报告 {#reporting}

深入了解Campaign的报告功能，包括内置的报告、自定义报告以及多维数据集等数据分析工具。

+++ 如何创建新报告？

除了内置的报告，Adobe Campaign 还可用于在不同的上下文中生成各种报告，以满足不同的需求。

Adobe Campaign 不是专门的报告创建工具：在 Adobe Campaign 中创建的报告主要让您查看已汇总的数据。

[了解有关Campaign报告功能的更多信息](../reporting/gs-reporting.md)。

+++

+++ 如何设计并分享有关群体的统计报告？

Adobe Campaign [描述性分析报告](../reporting/built-in-reports.md)允许您设计并分享有关群体的统计报告。

[了解详情](../reporting/built-in-reports.md)。

+++

+++ 如何根据我的数据设计高级报告？

使用Campaign v8，您可以[创建高级报告](../reporting/custom-reports.md)。 作为专家级用户，您将能够根据您的数据构建、更新和分发自定义报告。

您还可以使用Campaign Web用户界面创建报告和仪表板。 [了解详情](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}。

+++

+++ 什么是多维数据集以及如何创建此类报告？

您可以扩展数据库探索和分析能力，同时使最终用户更容易配置报告和表：他们只需在创建其报告或表时选择现有（已经过完全配置）多维数据集，以处理计算、度量和统计。

创建和配置多维数据集后，报告查询框和 Web 应用程序中即会使用这些多维数据集。它们可以在数据透视表中使用和操作。

了解如何利用多维数据集[探索数据](../reporting/gs-cubes.md)。

+++

+++ 我能利用在线调查的回答创建报告吗？

Campaign v8没有内置调查功能。 您可以使用Adobe Experience Manager或其他Web解决方案来创建调查。

但是，您可以使用报告功能来分析任何收集的数据并创建自定义报告。

+++

+++ 如何在Campaign界面中共享对报告的访问权限？

您可以定义报告在 Adobe Campaign UI 中显示的上下文。如需有关报告访问权限的详细信息，请参阅[此部分](../reporting/custom-reports.md)。

+++

+++ 能否以不同格式导出报表？

可以，您可以以Excel、PDF或CSV等不同格式导出Campaign报表。 [了解详情](../reporting/custom-reports.md)。

+++

## 开发人员 {#developers}

访问面向开发人员的技术信息，包括数据模型详细信息、架构、API和自定义功能。

+++ 什么是Campaign数据模型？

Adobe Campaign 数据库的概念数据模型由一组内置表及它们之间的交互组成。应用中所承载数据的物理和逻辑结构以 XML 格式进行描述。它遵循Adobe Campaign特有的语法，称为模式。

[详细了解 Campaign 数据模型](../dev/datamodel.md)。

[此页面列出了最佳实践](../dev/datamodel-best-practices.md)。

+++

+++ 如何使用 Campaign 模式？

在 Adobe Campaign 中，数据架构用于：

* 定义应用程序内的数据对象如何与底层数据库表的联系起来。
* 定义 Campaign 应用程序中不同数据对象之间的链接。
* 定义并描述每个对象中包含的个别字段。

[开始使用表和架构](../dev/schemas.md)，了解如何使用数据架构、扩展和自定义Campaign来满足您的需求。

+++

+++ 如何使用自定义收件人表？

您可以在Campaign中创建并实施非内置的收件人表，以发送消息。

[了解详情](../dev/custom-recipient.md)

+++

+++ 在 Campaign 中定义查询的最佳实践是什么？

Adobe Campaign 查询编辑器是一款功能强大的工具，可用于探索数据和创建分段。

您可在软件的多个级别上找到 Adobe Campaign 查询工具：创建目标群体、细分客户、提取和过滤跟踪日志、构建过滤器等。

您可以使用通用查询编辑器查询 Campaign 数据库。可通过 **Tools > Generic query editor...** 菜单访问查询编辑器。它可让您提取数据库中存储的信息，将其整理、分组、排序等。例如，用户可以找到在给定的期间内，在新闻稿的链接上点击超过 n 次的收件人。通过这个工具，您可根据自己的需求收集、排序和显示结果。

[了解详情](../start/query-editor.md)。您还可以参阅[Campaign自动化指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}。

+++

+++ 如何导入数据包？

使用 Adobe Campaign，您可以通过数据包系统导出或导入平台配置和数据。数据包支持以 XML 格式文件的形式显示 Adobe Campaign 数据库的实体。数据包中包含的每个实体由其全部数据表示。

数据包的原理是导出数据配置，并将它集成到另一个 Adobe Campaign 系统中。

[了解更多](../dev/packages.md)有关如何使用数据包导入和导出Campaign配置。

+++

+++ 在哪里可以找到Campaign v8 API的列表？

所有 Campaign API（包括其完整说明）均在此[专用文档](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hans){target="_blank"}中提供。

+++

+++ 什么是Campaign REST API？

Campaign v8公开了一组REST API，可让您通过将Adobe Campaign与您使用的技术面板连接，为Adobe Campaign创建集成并构建您自己的生态系统。

[了解详情](../dev/api/get-started-apis.md)。

+++

+++ 如何从API监测工作流？

在[此专用页面](../dev/api/controlling-a-workflow.md)中了解如何使用Campaign API监测工作流。

+++

+++ 如何更新数据库结构？

如果修改Campaign数据架构，则需要更新数据库结构。 在[本节](../dev/update-database-structure.md)中了解详情。

+++

+++ Campaign v8有哪些限制？

与Campaign Classic v7相比，Campaign v8存在一些限制，详情请参阅[此页面](../start/v7-to-v8.md#limitations)。

+++

## 隐私 {#privacy}

了解Adobe Campaign如何帮助您遵守GDPR和CCPA等隐私法规以及管理数据主体请求。

+++ 有关隐私的关键术语有哪些？

以下所列项目链接到与 Adobe Campaign 中的隐私和同意相关的关键术语和概念：

* [隐私管理法规](../start/privacy.md#privacy-regulations)
* [个人数据和角色](../start/privacy.md#personal-data)
* [访问权与被遗忘权](../start/privacy.md#right-access-forgotten)
* [同意、保留和角色](../start/privacy.md#consent-retention-roles)

+++

+++ Adobe Campaign 关于遵守最新隐私法规的建议是什么？

Adobe 不提供法律建议。您应与您自己的法律顾问合作，以确保其采取所有必要措施为 GDPR、CCPA、PDPA、LGPD 或任何其他适用法规做准备。

**准备数据访问和删除请求**

* 确定接收/响应数据主体请求的流程，包括指定隐私联系人。

* 审查存储在 Adobe Campaign 中的各种客户数据并确定唯一标识符（可能有多个）。

* 确定确认数据主体身份的验证/身份验证策略和流程。

* 确保数据主体响应易于理解。

**考虑同意**

* 列出并根据需要更新 GDPR 数据捕获的所有接触点（即，考虑语言、同意机制和同意日志）。

* 确保所有营销电子邮件都包含取消订阅链接。

* 评估电子邮件营销的全球战略，以确定特定于地理位置的实施。

**了解数据**

* 审查数据流入 Adobe Campaign 的所有数据导入和捕获源，并记录哪些字段用于您的营销工作。

* 从 Adobe Campaign 数据库中删除任何未使用的数据属性。

* 使用 Adobe Campaign 中可用的数据获取捕获该数据的意图，并为收件人提供更好的个性化体验。

* 审查和更新数据访问权限，以帮助确保 Adobe Campaign 用户只能充分利用运行其营销活动所需的数据，但不能访问超出此范围的任何数据。

* 确保每个 Adobe Campaign 用户都具有相应的访问权限来执行其所需的任务，但没有用于执行其他任务的任何其他权限。

+++

+++ 数据控制者如何在对用户参与度影响最小的情况下获取同意？

在需要针对特定营销活动获得同意的情况下，消费者同意需要有效（即，无“沉默即同意”框或预选框）、未捆绑，并且不能有条件地提供服务。

甚至可能存在需要刷新某些同意才能继续使用数据的情况。

营销人员应该接受这些加强的同意要求，作为品牌互动和忠诚度以及客户满意度和信任度的真实指标。

+++

+++ 数据控制者如何能够在 Adobe Campaign 中管理同意？

Adobe Campaign 已经提供通过自定义数据字段或通过一个或多个服务在比大多数营销人员所使用更多的级别管理同意的功能。

营销人员应咨询其法律顾问以获取有关如何继续的指导，然后利用已内置到 Adobe Campaign 的功能。

例如，扩展 Adobe Campaign 中的数据模型，从而不仅跟踪用户已选择加入的情况，还跟踪选择加入的时间戳，以及用于捕获确切同意范围的某类指标。

+++

+++ 数据控制者可以删除 Adobe Campaign 中的哪些数据来响应数据主体的客户请求？

与数据主体关联的所有数据都将删除，包括现成表格和自定义表格。

技术上，链接到 `integrity="own"` 的数据主体的所有数据都将删除。

作为数据控制者，您可以选择通过更改数据架构中定义的链接的完整性来自定义此数据（例如，如果您有业务理由不删除某些数据）。

+++

+++ 删除投放和跟踪日志后报告会受到什么影响？

Adobe Campaign 中的报告基于根据投放和跟踪日志中的汇总数据计算所得的指标。因此，删除个别日志应当不会影响报告中显示的指标。

+++

+++ 我是否需要注意在以后某个日期可能重新导入数据？

在Adobe Campaign中，记录通常从外部数据源上传。

作为数据控制者，您将需要确保在收到删除请求时，从所有系统中删除有关数据主体的所有必要数据。

+++

+++ 其数据已从 Adobe Campaign 中清除的数据主体是否可以稍后再次选择加入？

数据主体可能再次选择加入，或者在从 Adobe Campaign 中删除其数据后添加为新收件人。

您可以使用审计跟踪，其中详细说明了上次删除的执行时间和新收件人的创建时间。

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
* **[最佳实践](delivery-best-practices.md)** — 针对常见任务的推荐方法

### 技术资源

查找详细的技术文档和开发人员资源。

* **[Campaign API](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hans){target="_blank"}** — 完整API参考文档
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.en)** — 向文档投稿
* **[技术说明](https://experienceleague.adobe.com/zh-hans/docs/campaign/technotes-ac/technotes-home){target="_blank"}** — 深入的技术文章
* **[兼容性矩阵](compatibility-matrix.md)** — 支持的系统和版本

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

