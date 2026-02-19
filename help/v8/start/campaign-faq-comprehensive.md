---
title: Campaign v8 常见问题解答
description: 获取有关设置、配置、消息传递、工作流等的常见Adobe Campaign v8问题的答案
feature: Overview
role: User
level: Beginner
keywords: 常见问题解答， Campaign v8，问题，回答，帮助，支持，故障排除
version: Campaign v8
exl-id: 8b4f6343-5dc5-4401-ad6f-9c1ddbb23168
source-git-commit: da2274cfd19bb067fcc1e990360093f161d5638a
workflow-type: tm+mt
source-wordcount: '10485'
ht-degree: 10%

---

# 常见问题解答 {#faq}

快速获取有关Adobe Campaign v8的最常见问题的答案。 无论您是刚刚入门还是正在寻找高级配置帮助，您都可以找到以下按主题排列的答案。

**是营销活动的新用户？**&#x200B;从[快速入门](#getting-started)开始，学习要点。\
**需要版本帮助？**&#x200B;检查[升级](#upgrades)以了解版本信息和升级过程。\
**从v7或Standard迁移？**&#x200B;请参阅[Campaign v8与先前版本](#v7-differences)的差异和过渡指南。\
**需要技术帮助？**&#x200B;检查[开发人员](#developers)和[促销活动设置](#settings)。\
**找不到您的答案？**&#x200B;访问我们的[社区论坛](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=zh-Hans){target="_blank"}或[联系支持人员](#get-help)。

**提示：**&#x200B;使用Ctrl+F(在Mac上按Cmd+F)搜索此页面上的特定关键字。 单击任意问题以展开答案。


## 快速入门 {#getting-started}

了解开始使用Adobe Campaign v8的要点，从安装和连接到创建首批营销活动。

+++ 什么是Adobe Campaign v8？

Adobe Campaign v8是一个功能强大的跨渠道营销自动化平台，可帮助您跨电子邮件、移动设备、社交和线下渠道创建、协调和投放个性化营销活动。 它结合了强大的营销数据库、活动编排引擎和实时互动功能，以便与客户在整个历程中互动。

**关键功能：**&#x200B;多渠道营销活动管理、受众细分和定位、工作流自动化、大规模个性化、实时和批量消息传递、报告和分析、与Adobe Experience Cloud集成。

**是什么使得v8独一无二：**&#x200B;云原生架构（仅限托管云服务）、由Snowflake数据库提供支持的企业级性能、自动升级、增强的安全性，以及与Adobe Experience Platform的双向集成。

**非常适用于：**&#x200B;跨多个渠道和客户接触点管理复杂、大量营销活动的企业营销团队。

**相关主题：**

[Campaign v8产品说明](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"} | [v8的新增功能](whats-new.md) | [入门指南](get-started.md)

+++

+++ 如何下载Campaign？

可以从 Adobe 下载中心获取安装程序和客户端控制台。

作为管理员用户，请访问Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/zh-hans/campaign.html){target="_blank"}下载Adobe Campaign。

在此页面[上了解有关分发中心](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hans){target="_blank"}的更多信息。

+++

+++ 如何连接到 Campaign v8？

您需要下载并安装Campaign客户端控制台才能连接到Adobe Campaign。 [了解详情](connect.md)。

从Campaign v8.6版本开始，您可以访问&#x200B;**Campaign Web用户界面**，该界面可通过集中式Adobe Experience Cloud环境使用。 Experience Cloud是Adobe的集成式数字营销应用程序、产品和服务系列。

在本页[中了解如何连接到Adobe Experience Cloud并访问Adobe Campaign Web界面](campaign-ui.md#ac-web-ui)。 请参阅 [Adobe Campaign Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}以了解详情。


**相关主题：**

[安装客户端控制台](connect.md) | [Campaign用户界面](campaign-ui.md) | [用户权限](gs-permissions.md)

+++

+++ 我可以使用Adobe ID连接到Campaign v8吗？

是！ 通过与IMS (Adobe Identity Management System)集成，用户可使用其Adobe ID连接到Adobe Campaign控制台。 该集成具有以下优势︰

* 所有 Experience Cloud 解决方案都可以使用相同的 ID。
* 使用具有不同集成的 Adobe Campaign 时，可以记住该连接。
* 密码管理策略更安全。
* 使用联合 ID 帐户（外部 ID 提供商）。

[了解更多](connect.md)如何使用Adobe ID访问Campaign v8。

+++

+++ 我应该了解哪些 Campaign 用户界面概念?

请参阅[此部分](campaign-ui.md)，了解有关Adobe Campaign用户界面基础知识的更多信息。

从Campaign v8.6版本开始，您还可以访问新的&#x200B;**Campaign Web用户界面**，该界面可通过集中式Adobe Experience Cloud环境使用。

[请参阅Adobe Campaign Web用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}以了解详情。

+++

+++ 如何设置用户权限?

作为 Campaign 管理员，您可以为组织的用户设置权限。

这些权限是一组权利或限制，可授权或拒绝用户执行以下操作：

* 访问特定功能
* 访问特定数据
* 创建、修改和/或删除数据

**相关主题：**

[开始使用权限](gs-permissions.md) | [管理用户权限](manage-permissions.md) | [添加文件夹权限](folder-permissions.md)

+++

+++ 如何选择消息的受众？

Campaign提供了多种定位方法以便为消息选择正确的受众：

**定位方法：**

* **查询编辑器** — 使用对收件人属性、行为或人口统计的可视化筛选器构建受众
* **列表** — 使用预定义的静态或动态收件人列表
* **文件导入** — 为一次性活动上传外部收件人文件
* **工作流** — 使用查询、拆分和扩充活动创建复杂的定位逻辑
* **预定义过滤器** — 应用现成的过滤器（活动客户、订阅者、VIP）
* 来自Adobe Experience Platform的&#x200B;**区段** — 利用统一的用户档案和实时区段

您可以组合多个标准（位置、购买历史记录、参与度），并使用排除项、交叉点或合并来优化受众。

**相关主题：**

[在Campaign v8中定义受众](../audiences/gs-audiences.md) | [查询编辑器](query-editor.md) | [目标映射](../audiences/target-mappings.md)

+++

+++ 如何创建并发送第一封电子邮件？

在Campaign v8中创建您的第一封电子邮件很简单。 您可以从模板开始，选择目标受众，使用个性化设计内容，使用验证对其进行测试，然后发送。 Campaign提供两种用于创建电子邮件的界面：适用于高级用户的功能齐全的&#x200B;**客户端控制台**，以及用于更快、更直观地构建电子邮件的现代&#x200B;**Campaign Web UI**。

**5个关键步骤：**

1. **创建投放** — 从电子邮件模板开始或从头开始创建
2. **定义受众** — 使用查询、列表或工作流选择收件人
3. **设计内容** — 使用电子邮件设计器创建包含个性化字段的邮件
4. **发送测试验证** — 验证跨设备和电子邮件客户端的渲染和内容
5. **分析和发送** — 运行投放分析以检查错误，然后发送电子邮件

**相关主题：**

[电子邮件设计和验证](../send/email.md) | [创建第一个投放](create-message.md) | [传递模板](../send/create-templates.md) | [个性化内容](../send/personalize.md)

+++

+++ 如何翻译错误消息？

错误消息是用外文显示的？[此页面](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hans){target="_blank"}中列出了所有错误消息及其译文。

+++

+++ 如何记录问题？

要联系Adobe客户支持，请连接到[Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}以创建案例或启动聊天会话。

需要具有正确权限的个人帐户。 如果您无法登录，请通过Experience League请求访问权限。 [了解详情](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

或者，加入[Campaign社区](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=zh-Hans){target="_blank"}以搜索答案或咨询专家。

+++

+++ 哪些系统和组件与 Campaign v8 兼容？

在 [Adobe Campaign 兼容性矩阵](compatibility-matrix.md)中，您可以获得支持 Campaign 最新版本的所有系统和组件的列表。

+++

+++ 我可以将Campaign v8与其他Adobe解决方案结合使用吗？

是的。 Campaign v8与Adobe Experience Cloud解决方案无缝集成，形成统一的营销生态系统。

**关键集成：** Adobe Experience Platform （统一配置文件、实时数据）、Adobe Analytics （性能衡量）、Adobe Target （个性化）、Adobe Experience Manager （内容管理）、Adobe Audience Manager （受众区段）。

**安装程序：**&#x200B;需要Adobe IMS身份验证，已为Campaign v8托管云服务自动配置。

**相关主题：**

[Adobe Campaign集成](../connect/integration.md) | [与Adobe ID连接](connect.md)

+++

+++ Campaign v8有哪些限制？

Campaign v8显着提高了性能，但与Campaign Classic v7存在一些体系结构差异，尤其是在FFDA部署中。

**关键注意事项：**

* **FFDA架构** — 使用具有不同数据访问模式的云数据库(Snowflake)
* **数据更新** — 应在工作流中完成，而不是通过直接数据库访问
* **批次优化** — 已针对批次操作（而非高频单个更新）进行优化
* **在FFDA中不可用** — 调查、营销资源管理(MRM)、某些特定连接器

**迁移影响：**&#x200B;使用直接数据库写入的自定义代码需要重构；API集成可能需要调整以适合批次处理。

随着Adobe增强v8，这些限制也在不断发展。 请参阅最新文档以了解当前状态。

**相关主题：**

[Campaign v7到v8的迁移](../start/v7-to-v8.md#limitations) | [FFDA架构](../architecture/enterprise-deployment.md)

+++

+++ 作为Campaign Classic v7用户，我是否可以迁移到Campaign v8？

从现有 Campaign Classic v7 环境进行自动迁移的功能尚不可用。

Campaign v8 **仅**&#x200B;作为托管式云服务提供，不能部署在内部部署或混合环境中。

有关迁移流程的更多信息，请联系您的 Adobe 代表。

在[Campaign v8与先前版本](#v7-differences)部分了解详情。

+++


## 升级次数 {#upgrades}

了解如何检查您的Campaign版本、了解升级过程并随时了解新版本。 Campaign v8托管云服务以最小的中断自动处理升级。

+++ 我的 Campaign 是什么版本？

可通过 Campaign 客户端控制台的 **Help > About...** 菜单查看您的[版本号和构建号](upgrades.md#version)。

+++

+++ 如何将 Campaign 升级到最新版本？

Adobe Campaign 会定期更新。每年都会发布包含新功能、改进和修复的次要版本。此外，我们还定期发布仅包含累积修复的内部版本。

这种定期更新旨在让您掌握最新、最充分的信息，保持环境的安全，并改进您对我们产品的体验。这就是为什么我们认为运行最新版本的 Adobe Campaign 至关重要的原因。

**注意：**&#x200B;作为Managed Cloud Services用户，您的实例已由Adobe升级为新版本。

了解有关[Campaign版本和升级的详细信息](upgrades.md)。

+++

+++ 如何通知我已发布新版本？

通过以下渠道及时了解新的Campaign版本：

* **Adobe代表** — 在新版本可用时直接联系您
* **发行说明** - [Campaign发行说明](release-notes.md)中记录的所有版本和更改
* **Adobe优先产品更新** - [订阅](https://www.adobe.com/cn/subscription/priority-product-update.html){target="_blank"}电子邮件通知
* **Campaign社区** — 加入[讨论](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=zh-Hans){target="_blank"}了解早期更新

作为托管Cloud Services用户，Adobe可处理升级并协调与您之间的计时。

**相关主题：**

[发行说明](release-notes.md) | [新增功能](whats-new.md) | [促销活动版本和升级](upgrades.md)

+++

+++ 为什么我的组织需要升级？

升级到最新Campaign版本对于安全性、性能和支持质量至关重要。

**主要优点：**

* **增强的安全性** — 针对漏洞的保护、最新的修补程序、增强的数据保护
* **更好的支持** — 更快的问题解决，访问错误修复，对最新版本的优先支持
* **增强的性能** — 优化数据库和工作流、更好的可扩展性、更可靠的操作
* **新功能** — 最新功能、改进的Adobe Experience Cloud集成、现代UI增强功能

Adobe强烈建议运行最新版本。 作为托管云服务客户，升级由Adobe以最低的中断执行。

**相关主题：**

[促销活动版本和升级](upgrades.md) | [新增功能](whats-new.md) | [兼容性矩阵](compatibility-matrix.md)

+++

+++ 升级的流程和时间线是什么？

作为托管云服务客户，Adobe管理整个升级过程，并将对运营的影响降至最低。

**进程：**

1. **通知** - Adobe会提前几周通知您
2. **计划** — 与您的Adobe代表一起安排在最佳时间升级
3. **准备** - Adobe准备环境并进行验证
4. **执行** - Adobe以最小的停机时间升级基础架构
5. **验证** — 由Adobe进行的升级后测试
6. **客户端控制台升级** — 升级客户端控制台以匹配服务器版本

**您的职责：**

* 协调内部利益相关者进行时间安排
* [将客户端控制台](connect.md#upgrade-ac-console)升级到新版本
* 升级后测试活动和工作流
* 向Adobe支持部门报告问题

Adobe执行基础设施升级。 您不需要在服务器上执行任何技术操作。

**相关主题：**

[促销活动版本和升级](upgrades.md) | [升级客户端控制台](connect.md#upgrade-ac-console) | [发行说明](release-notes.md)

+++


## Campaign v8与先前版本 {#v7-differences}

了解Campaign v8与先前版本（Classic v7和Standard）之间的主要差异，包括架构、部署、迁移路径和功能更改。 无论您是来自Campaign Classic v7还是Campaign Standard，都可以了解新增功能以及如何平稳过渡。


+++ Campaign v8与先前版本之间有何主要区别？

Campaign v8基于现代云原生架构而构建，具有显着改进：

* **仅限Managed Cloud Services** — 完全由Adobe托管（无内部部署/混合选项）
* **卓越的性能** — 高达2000万次操作/小时，具有完全联合数据访问(FFDA)体系结构
* **新的Campaign Web UI** — 经典控制台旁提供现代、直观的界面
* **自动升级** — 始终使用最新版本，无需停机时间
* **增强功能** - AI助手、富推送通知、升级的短信、改进的与Adobe Experience Cloud的集成

**对于Campaign Classic v7用户：**&#x200B;了解[从v7过渡到v8](v7-to-v8.md)，包括架构更改、功能不可用和迁移注意事项。

**对于Campaign Standard用户：**&#x200B;了解到v8[和](acs-to-v8.md)Campaign Standard迁移指南[的](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}过渡路径。

**相关主题：**

[Campaign v8关键功能](whats-new.md) | [Campaign v8架构](../architecture/architecture.md) | [功能矩阵](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [护栏和限制](ac-guardrails.md)

+++

+++ 我应该从Campaign Classic v7还是Campaign Standard迁移到v8？

Campaign v8是Adobe的平台，非常适合需要大量促销活动（每小时2000万项操作）、现代Web UI、云原生优势和长期支持的组织。

**主要优点：**

* **对于Campaign Standard用户** — 熟悉的Web UI、功能等同性（动态报告、REST API、登陆页）、顺利的数据迁移
* **对于Campaign Classic v7用户** — 双界面（控制台+ Web UI），更好的性能，自动升级，增强的FFDA架构

**如果您：**，请考虑迁移

* 处理大量数据或遇到性能问题
* 希望减少IT开销和基础架构管理
* 需要Adobe Experience Cloud/Platform集成
* 希望采用具有自动更新的未来防护技术

**后续步骤：**&#x200B;请联系您的Adobe代表以评估迁移准备情况并访问迁移工具。

**相关主题：**

[从Campaign Classic v7到v8](v7-to-v8.md) | [Campaign Standard过渡指南](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [功能矩阵](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

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

+++ 如何将我的Campaign Classic v7内部部署或混合环境迁移到Adobe Managed Services？

迁移到Adobe Managed Services提供了从内部部署/混合部署v7到云的战略途径，可改进可扩展性、安全性和降低IT开销。 在过渡到Campaign v8之前，这通常是垫脚石。

**关键点：**

* 没有可用的自动迁移工具 — 需要手动规划和执行
* 强烈建议支持Adobe Professional Services
* 其优势包括云基础架构、自动安全修补程序、专家支持和更轻松的v8途径
* 迁移包括尽职调查、环境审核、数据清理、暂存迁移和生产切换

**快速入门：**&#x200B;请联系您的Adobe代表以评估您的环境，并使用Adobe Professional Services制定详细的迁移计划。

了解有关[迁移到Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605?profile.language=zh-Hans){target="_blank"}的更多信息，包括挑战、最佳实践和详细的迁移路线图。

+++

+++ Campaign v8中的主要术语和功能区别是什么？

Campaign v8通过增强功能提供了大多数v7/Standard功能，但某些术语和功能有所不同。 您将在下面找到关键更改摘要。

**关键术语更改(Campaign Standard → v8)：**

* **架构**→自定义资源 | **投放**→消息 | 产品用户→ **操作员**
* 安全组→**操作员组** | 组织单位→ **文件夹权限**

**Campaign Web UI更新：**

* **配置文件**→收件人 | **测试配置文件**→种子地址 | 投放分析→ **投放准备**
* 列出→**个受众** | 电子邮件预览→**模拟内容**

**在v8中不可用：**

* 内部部署/混合部署（仅限托管式云服务）
* 直接数据库访问（使用API）
* 手动基础架构管理(由Adobe管理)

**Campaign Standard用户的新功能：**

* 动态报告、集中式品牌、REST API、登陆页面改进、可视化片段

**相关主题：**

[功能矩阵](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [v7到v8过渡指南](v7-to-v8.md) | [Campaign Standard到v8的过渡](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## 轮廓和受众 {#audiences}

查找有关管理营销策划的用户档案、创建受众、导入数据和定向收件人等问题的答案。

+++ 如何创建收件人？

在客户端控制台中为各个用户档案手动创建收件人，从文件(CSV/TXT)导入以进行批量添加，使用Web表单进行自助注册，或通过外部系统的API进行集成。 使用导入工作流进行定期数据加载。

**相关主题：**

[手动创建配置文件](../audiences/create-profiles.md) | [从文件导入用户档案](../audiences/import-profiles.md) | [使用Web窗体收集配置文件](../audiences/collect-profiles.md)

+++

+++ 如何导入用户档案？

Campaign提供了多种导入方法：使用导入向导导入简单的文件；基于工作流的导入以进行复杂转换；通过SFTP中的计划工作流重复导入；导入API以进行程序集成。

对于文件导入，请准备数据文件（CSV/TXT、UTF-8编码），使用导入向导或工作流，将列映射到Campaign字段，定义更新/插入规则，并首先使用小示例进行测试。 使用工作流进行定期导入并应用重复数据删除规则。

**相关主题：**

[导入数据指南](../start/import.md) | [循环导入工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=zh-Hans){target="_blank"} | [数据加载活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何为投放创建测试用户档案？

通过测试用户档案（种子地址），可定向不符合所规定定向标准的收件人，从而能够在向主要受众发送内容之前对投放进行测试。 通过&#x200B;**[!UICONTROL Seed addresses]**&#x200B;在投放属性中添加它们或使用&#x200B;**[!UICONTROL Seed addresses]**&#x200B;文件夹。

了解有关[测试用户档案](../audiences/test-profiles.md)的更多信息。

+++

+++ 如何定义营销活动的目标群体？

Campaign提供了多种定位方法：使用可视条件构建查询、定位现有列表或区段、从外部文件(CSV、TXT)导入收件人或应用预定义过滤器。 您可以将标准与AND/OR逻辑相结合，排除特定群体，使用控制组，以及拆分以进行A/B测试。 始终在发送前预览目标群体大小。

**相关主题：**

[定义营销活动目标](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hans){target="_blank"} | [查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hans){target="_blank"} | [创建受众](../audiences/create-audiences.md)

+++

+++ 如何创建用户档案列表？

列表是一组静态的收件人，您可以在投放中定位并在营销活动中重复使用。

**三种创建方法：**

* **手动创建：**&#x200B;导航到&#x200B;**[!UICONTROL Profiles and Targets > Lists]**&#x200B;并单击&#x200B;**[!UICONTROL Create]**。 通过查询、单个选择或文件夹添加收件人。

* **工作流自动化：**&#x200B;使用&#x200B;**[!UICONTROL List update]**&#x200B;活动从查询结果或导入的数据中自动创建和维护列表。

* **导入期间：**&#x200B;在导入用户档案时创建一个列表以将其另存为可重复使用的组。

**提示：**&#x200B;使用工作流处理需要定期更新的列表，以及手动创建的一次性分段。

**相关主题：**

[创建受众](../audiences/create-audiences.md) | [列出更新活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何在发送邮件前删除重复的群体？

在投放之前使用工作流中的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活动删除重复的收件人。 将其放在您的&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Delivery]**&#x200B;活动之间，然后选择您的重复数据删除条件（通常是电子邮件地址或收件人ID）以及要保留的记录。

**提示：**&#x200B;发送前始终删除重复项，以确保每个人只收到一次您的消息。

了解有关[重复数据删除活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=zh-Hans){target="_blank"}的更多信息

+++

+++ 如何识别和定位新闻稿的订阅者？

Campaign通过信息服务自动跟踪新闻稿订阅。 要定位订阅者，请执行以下操作：

* 使用&#x200B;**[!UICONTROL Query]**&#x200B;活动并筛选&#x200B;**[!UICONTROL Subscriptions]** >选择新闻稿服务
* 通过选择&#x200B;**[!UICONTROL To > Subscribers of an information service]**&#x200B;直接从投放中定位订阅者
* 使用&#x200B;**[!UICONTROL Subscription Services]**&#x200B;工作流活动生成订阅者列表

Campaign跟踪订阅/退订历史记录，并自动管理选择加入/选择退出。

**相关主题：**

[管理订阅](../start/subscriptions.md) | [查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hans){target="_blank"}

+++

+++ 从目标群体中排除用户档案的最佳实践是什么？

在工作流中使用&#x200B;**[!UICONTROL Exclusion]**&#x200B;活动从目标中删除不需要的用户档案。 将其放在定向活动之后，并定义要排除的群体。

了解有关[排除活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=zh-Hans){target="_blank"}的更多信息

+++


## 消息设计 {#design}

了解如何在Campaign v8中设计有效的营销消息，包括电子邮件模板、个性化技术和多语言内容。 在客户端控制台中设计消息，或在Campaign Web UI中使用现代的&#x200B;**Email Designer**，以增强可视化编辑体验。

+++ 在Campaign中设计电子邮件的最佳实践是什么？

关键准则：确保实现移动响应式设计，将HTML 4.0/XHTML兼容代码与内联CSS一起使用，使用替换文本优化图像（小于100 KB），使用个性化合并字段，在发送之前跨电子邮件客户端进行测试，并包含纯文本版本。 将电子邮件总大小控制在500 KB以下以实现最佳可投放性。

**相关主题：**

[电子邮件设计指南](../send/email.md) | [投放最佳实践](delivery-best-practices.md)

+++

+++ 什么是投放模板？

投放模板是预配置的投放，可保存所有设置和参数以供在多个营销活动中重复使用。 模板包括目标规则、内容设计、个性化、技术设置（发件人、回复）和类型规则。 创建一次并重复使用，以保持一致性并加快活动创建。

了解如何[创建投放模板](../send/create-templates.md)

+++

+++ 在 Campaign 中能轻松导入现有的 HTML 以制作电子邮件吗?

是的。 通过直接复制/粘贴将HTML内容导入内容编辑器、从计算机上传文件或从URL加载。 确保您的HTML使用具有内联CSS的电子邮件兼容代码(HTML 4.0/XHTML)，并将图像托管在公共服务器上。 Campaign会自动将个性化和跟踪添加到导入的HTML。

**提示：**&#x200B;要获得最佳的电子邮件设计体验，请在Campaign Web UI中使用&#x200B;**电子邮件Designer**，它提供现代拖放功能和内置响应模板，而不是导入原始HTML。

了解如何[导入HTML内容](../send/defining-the-email-content.md)

+++

+++ 如何在 Campaign 中创建基于订阅的新闻稿？

是的。 使用Campaign的信息服务管理新闻稿订阅。 关键功能包括自动选择加入/选择退出处理、订阅跟踪、合规性管理(GDPR、CAN-SPAM)、多新闻稿支持、注册表单的Web集成以及面向订阅者的目标交付。

了解如何[管理订阅](../start/subscriptions.md)

+++

+++ 如何个性化各种消息？

Campaign提供个性化功能，根据收件人数据、行为和偏好创建相关的定向消息。

**Personalization选项：**

* **个性化字段** — 插入收件人数据（例如，`"Hello {{firstName}}")`）
* **个性化块** — 使用预定义或自定义的内容块
* **条件内容** — 根据收件人条件显示不同的内容
* **行为数据** — 利用浏览历史记录、购买模式或参与量度

在发送之前测试个性化，以验证合并字段和条件逻辑是否正常工作。

**相关主题：**

[Personalization指南](../send/personalize.md) | [个性化字段](../send/personalization-fields.md) | [条件内容](../send/conditions.md)

+++

+++ 如何个性化电子邮件主题行？

个性化的主题行会显着增加开放率。 Campaign允许您动态插入收件人数据、应用条件逻辑和测试变体以优化参与。

**Personalization技术：**

* **基本字段** — 插入名字、姓氏、位置： `"<%@ firstName %>, exclusive offer for you"`
* **条件内容** — 按区段列出的不同主题： `"<% if (recipient.gender == 'F') { %>Special offer just for you<% } else { %>Exclusive deal inside<% } %>"`
* **动态数据** — 包括购买历史记录、会员积分或帐户信息
* **表情符号** — 添加视觉吸引力（首先跨电子邮件客户端进行测试）

**最佳实践：**&#x200B;不超过50个字符，发送前测试个性化令牌，使用A/B测试进行优化，避免垃圾邮件触发词，包括价值主张或紧迫性。

**相关主题：**

[个性化字段](../send/personalization-fields.md) | [条件内容](../send/conditions.md)

+++

+++ 我能发送多语言邮件吗？

是的。 Campaign v8提供多语言功能，其中&#x200B;**Campaign Web UI**&#x200B;提供了最简单的方法。 Web UI通过语言变体提供本机多语言交付 — 将语言变体添加到交付中，并且Campaign会根据收件人的首选语言自动发送相应的版本。 可用于电子邮件、推送通知、短信和事务型消息。

主要功能：自动内容复制、基于语言的自动发送、默认语言回退和轻松的变量管理。

客户端控制台还支持使用条件内容和工作流的多语言内容，但需要更多手动配置。

**相关主题：**

[多语言投放(Web UI)](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [条件内容（客户端控制台）](../send/conditions.md)

+++

+++ 我可以将Web窗体本地化吗？

是的。 Campaign Web应用程序支持多语言本地化。 为所有表单元素（标签、按钮、消息、错误文本）定义翻译，并根据收件人配置文件或浏览器设置自动进行语言检测。 单个Web应用程序支持多种语言版本，并在需要时回退到默认语言。

了解有关[Web应用程序本地化的详细信息](../dev/webapps.md)

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

**相关主题：**

[AI助手概述](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI助手用例](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [品牌一致性](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## 测试和发送消息 {#send}

了解测试、验证、发送和跟踪营销消息的最佳实践，以确保成功交付营销活动。

+++ 如何改进电子邮件可投放性？

电子邮件可投放性是每个发件人的营销计划取得成功的重要因素，其特点是不断变化的标准和规则。想要在这个数字化的世界中取得成果，就必须定期调整电子邮件策略，并考虑关键可投放性趋势，以便最好地吸引受众。

请参阅本指南以了解[可投放性最佳实践](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}

要了解如何在 Campaign 中实施可投放性，请参阅[本指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=zh-Hans){target="_blank"}

**相关主题：**

[开始使用可投放性](../send/about-deliverability.md) | [控制邮件内容](../send/control-message-content.md) | [监视投放能力](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ 如何确认我的投放已成功发送，并且未出现错误？

**发送前：**&#x200B;运行投放分析，发送测试校样，查看警告，验证目标计数。

**发送期间/发送后：**&#x200B;监视投放仪表板（已发送、已投放、退回、错误）、检查投放日志、跟踪成功/退回率、查看隔离的地址。

**最佳实践：**&#x200B;设置警报，对大卷使用批次，先对小卷进行测试，定期清理收件人数据库，监视发件人信誉。

**相关主题：**

[跟踪和监视投放](../send/tracking.md) | [投放最佳实践](delivery-best-practices.md)

+++

+++ 什么是投放分析？

投放分析是Campaign在发送之前运行的验证阶段。 它计算目标群体、验证内容、检查错误、应用分类规则并估计投放量。

Campaign生成显示警告和错误的日志。 错误会阻止投放，必须修复；警告是建议性的。 发送前请务必查看分析日志。

请参阅[投放分析指南](../send/delivery-analysis.md)以了解详情

+++

+++ 为何要创建验证？

校样是在发送给主受众之前验证投放的测试消息。 使用校样验证个性化、测试跨电子邮件客户端的内容渲染、确认链接和跟踪工作、检查图像和附件，以及验证移动响应性。

验证有助于在错误到达成千上万的收件人之前捕获错误、支持利益相关者批准和测试收件箱放置。 将验证发送到多个电子邮件客户端和设备，并始终在生产发送之前获得批准。

在[验证和预览指南](../send/preview-and-proof.md)中了解详情

+++

+++ 如何在 Adobe Campaign 中使用种子地址？

种子地址是特殊收件人，会自动添加到每次投放以进行测试、质量保证和监控，这与您的目标条件不匹配。 对于持续监控、收件箱放置测试、直邮验证和利益相关者可见性非常有用。

**与校对的主要差异：**

* **种子地址** — 已自动添加到生产投放，计入发送数量
* **验证** — 测试在生产之前发送，不计入卷，用于验证

在&#x200B;**[!UICONTROL Resources > Campaign management > Seed addresses]**&#x200B;中管理种子地址。 保持较小的列表以避免影响投放量度。

请参阅[种子地址指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=zh-Hans){target="_blank"}以了解详情

+++

+++ 如何设置发送邮件前的批准流程？

Campaign提供审批工作流程，以确保报文在发送前符合质量标准。 在营销活动或投放级别为内容、目标、提取（直邮）和预算配置批准。

**设置：**

在&#x200B;**[!UICONTROL Administration > Access management > Operator groups]**&#x200B;中创建操作员组，然后在营销活动或投放属性中分配审批组。 Campaign会向批准、拒绝或请求更改的审阅人发送通知电子邮件。

**对于独立投放（不在营销活动中）：**

使用&#x200B;**验证作为您的审批流程**。 将验证发送到您的审批组进行验证，并始终在做出更改后发送新验证，以确保利益相关者查看最新版本。

**相关主题：**

[投放验证](../send/preview-and-proof.md) | [营销活动审批](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=zh-Hans){target="_blank"}

+++

+++ 我能否对投放运行A/B测试？

是！ Campaign允许您运行A/B测试（也称为拆分测试），以通过比较不同变体的性能来优化主题行、内容、发件人名称、发送时间等。

**您可以测试的内容：**

* **主题行** — 比较不同主题之间的打开率
* **内容变体** — 测试不同的布局、行动号召或图像
* **发件人信息** — 测试发件人名称或发件人地址影响
* **发送时间** — 确定最佳传递窗口
* **Personalization策略** — 比较个性化内容与常规内容

**工作方式：**

1. 创建投放并定义测试变体（最多3个）
2. 拆分受众（测试区段通常为10-20%）
3. Campaign将变量发送到测试区段并跟踪性能
4. 入选变体会自动发送给剩余受众（或者您手动选择入选者）

**可用于：** Campaign Web UI和客户端控制台。 Web UI提供了更简单的设置以及可视化比较。

**相关主题：**

[投放分析](../send/delivery-analysis.md) | [发送和跟踪投放](../send/send.md)

+++

+++ 什么是类型规则？

类型规则是在投放分析期间应用的自动业务逻辑，用于验证和优化消息发送。 它们确保遵守营销政策，保护可投放性，并防止客户疲劳。

**主规则类型：**

* 列入阻止列表 **筛选规则** — 排除收件人（已、已取消订阅、已隔离）
* **压力规则** — 控制消息频率以避免收件人过多
* **容量规则** — 限制用于处理容量或ISP限制的邮件量
* **控制规则** — 检查邮件有效性（主题行、取消订阅链接、发件人格式）

规则将分组为类型，并在投放分析期间应用。 Campaign可以根据规则排除收件人、阻止投放或生成警告。

请参阅[类型规则指南](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=zh-Hans){target="_blank"}以了解详情

+++

+++ 如何分批次发送电子邮件？

是的。 波次发送将按计划间隔将投放拆分为多个批次。 这对于大型营销活动至关重要，这些活动可以平衡服务器负载、防止ISP带宽限制、通过新IP建立发件人信誉以及管理批次之间的选择退出/退回。

**配置：**

在投放属性中，启用波次发送并定义波次数（或批次大小）、波次间隔和波次分布（线性或自定义百分比）。 Campaign会自动划分目标群体，并按计划发送每个波次。

将批次用于大型营销活动，在继续之前监视首轮效果，并在批次之间留出足够的时间处理退回和选择退出。

了解如何[配置波次发送](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ 如何计划一次投放？

利用Campaign，可计划投放以备将来发送，从而优化发送时间并协调活动。

**计划选项：**

* **投放属性** — 立即发送、计划特定日期/时间，或延迟小时/天
* **营销活动级别** — 协调营销活动中的所有投放
* **工作流调度程序活动** — 对于定期投放、复杂模式和事件触发的营销活动

Campaign还支持联系日期优化（每个收件人的最佳发送时间）和时区适应（所有收件人的相同本地时间）。

了解如何[计划发送投放](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ 我可以将附件添加到电子邮件吗？

是的。 Campaign支持静态附件（所有收件人的同一文件）和个性化附件（根据用户档案数据，每个收件人的文件不同）。 在投放属性的&#x200B;**[!UICONTROL Attachments]**&#x200B;部分中添加附件。

**重要注意事项：**

* 将附件保持在1MB以下以实现最佳可投放性
* 附件可能会触发垃圾邮件过滤器；请在发送之前进行全面测试
* 避免电子邮件客户端通常会阻止的文件类型(.exe、.zip、.js)
* 对于大型文件，请考虑改用跟踪的下载链接

在生产发送之前，使用安全文件格式(PDF、JPEG、PNG、DOCX)并使用种子地址进行测试。

请参阅[电子邮件附件指南](../send/email.md#attachments)以了解详情

+++

+++ 如何在电子邮件投放中设置跟踪链接？

Campaign会自动将电子邮件中的所有URL转换为跟踪链接以监测收件人参与。 访问投放中的&#x200B;**[!UICONTROL Tracking]**&#x200B;部分，为每个链接配置跟踪设置。

**配置选项：**

* **启用/禁用跟踪** — 每个链接的控制跟踪
* **链接标签** — 为报表添加描述性名称(例如，“立即购买CTA”)
* **链接类别** — 按类型对链接进行分组以进行聚合分析
* **跟踪类型** — 跟踪点击次数、打开次数或两者

Campaign跟踪内容链接、镜像页面链接、取消订阅链接，并且可以包含用于电子邮件打开次数的可选跟踪像素。 使用有意义的标签和类别来简化报表并快速识别高性能内容。

**相关主题：**

[链接跟踪指南](../send/tracking.md) | [跟踪最佳实践](../send/send.md)

+++

+++ 我在哪里可以访问投放内容和跟踪日志？

直接从每个投放仪表板访问投放和跟踪日志。 在客户端控制台中，单击底部的&#x200B;**[!UICONTROL Delivery]**&#x200B;选项卡。 在Campaign Web UI中，导航到&#x200B;**[!UICONTROL Logs]**&#x200B;部分。

**可用日志：**

* **投放日志** — 已发送包含收件人详细信息和状态（已发送、挂起、失败）的邮件
* **跟踪日志** — 包含时间戳的收件人交互（打开、点击）
* **排除日志** — 已排除的收件人及其原因（隔离、类型规则、重复）
* **广播日志** — 完成发送历史记录，包括重试和错误

使用这些日志对投放问题进行故障诊断、分析参与和维护列表卫生。

**相关主题：**

[投放监视](../send/send.md) | [跟踪指南](../send/tracking.md)

+++

+++ 从何处获得投放报告？

Campaign提供全面的内置报告，用于分析投放性能、收件人参与和活动有效性。 从任何投放的&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡、营销活动仪表板或跨营销活动分析的全局&#x200B;**[!UICONTROL Reports]**&#x200B;菜单访问报告。

**关键报告包括：**

* **投放摘要** — 发送统计数据、打开次数、点击次数、退信次数和取消订阅次数
* **热门点击** — 链接性能的可视热图
* **跟踪指标** — 点进率和参与量度
* **无法投放** — 包含失败原因的退回分析

通过现代可视化图表，可在客户端控制台和Campaign Web UI中获取报表。

**相关主题：**

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

**相关主题：**

[隔离管理指南](../send/quarantines.md) | [退回管理](../send/delivery-failures.md)

+++

## 工作流 {#workflows}

了解如何在Adobe Campaign中使用工作流实现流程自动化、管理数据和编排复杂的营销活动。

+++ 什么是工作流？

Adobe Campaign 包括在不同的应用程序服务器模块之间编排所有流程和任务的工作流。您可以利用这个全面的图形环境设计各式流程，包括部分划分、活动执行、文件处理、人员参与等。工作流引擎会执行并跟踪这些流程。

例如，您可以使用某个工作流从服务器下载文件、解压缩，然后将其中包含的记录导入 Adobe Campaign 数据库。

此外，一个工作流也可能涉及到要通知一个或多个操作员，或者是可以作出决策和批准流程的相关人员。这样就可以创建一次投放行动，将内容相关任务指派给一位或多位操作员，指定目标并在开始投放前审批校样。

[了解工作流详细信息](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}。 您也可以阅读[工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"}。

**相关主题：**

[工作流入门](../config/workflows.md) | [构建您的第一个工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"} | [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [监视工作流执行](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=zh-Hans){target="_blank"}

+++

+++ 是否能监测工作流的执行？

是的。 Campaign提供了多种监控工具：工作流功能板（实时状态和错误）、工作流日志（详细的执行日志）、热图（可视化活动和瓶颈）、审核跟踪（跟踪修改）和警报（失败通知）。

要监视，请打开工作流并单击&#x200B;**日志**&#x200B;选项卡。 失败的活动以红色显示。

**相关主题：**

[监视工作流执行](https://experienceleague.adobe.com/zh-hans/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hans){target="_blank"}

+++

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

[生成工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"} | [工作流活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hans){target="_blank"} | [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ 如何自动执行循环活动？

使用带有&#x200B;**调度程序**&#x200B;活动的工作流自动执行定期运行的营销活动 — 每天、每周、每月或自定义间隔。 非常适用于欢迎电子邮件、生日消息、新闻稿发送、放弃的购物车提醒和定期报告。

**安装模式：**

1. **调度程序** — 定义频率（例如，“每个星期一上午9点”）
2. **查询** — 选择具有动态条件的目标受众
3. **扩充**（可选） — 添加个性化数据
4. **投放** — 配置您的消息（电子邮件、短信、推送）
5. **结束** — 工作流完成并等待下一次计划运行

**常见自动营销活动：**

* **欢迎系列** — 用于向新订阅者发送入门级电子邮件的每日工作流
* **生日电子邮件** — 每日检查具有生日内容的收件人，发送个性化消息
* **重新参与** — 每周使用回馈优惠定位非活动用户
* **新闻稿** — 已计划每周或每月内容分发
* **放弃购买** — 用于识别放弃购买者并向其发送消息的工作流（每小时）

**提示：**&#x200B;在工作流中使用&#x200B;**循环投放**&#x200B;类型单独跟踪每个执行并维护历史报告。

**相关主题：**

[调度程序活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html?lang=zh-Hans){target="_blank"} | [定期投放](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/sending-a-birthday-email.html){target="_blank"} | [Campaign自动化](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何在 Campaign 中导入数据？

**方法：**&#x200B;导入向导（一次性CSV/TXT）、基于工作流的导入（**[!UICONTROL Data loading (file)]**&#x200B;活动用于包含转换的复杂/循环导入）、REST API（程序化/实时同步）。

**最佳实践：**&#x200B;测试小示例、使用UTF-8编码、正确映射字段、应用重复数据删除、计划非高峰期的大导入。

**相关主题：**

[导入最佳实践](../start/import.md) | [数据加载活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=zh-Hans){target="_blank"} | [循环导入工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何确保导入期间的数据质量？

数据质量对于成功执行营销活动至关重要。 糟糕的数据会导致交付失败、资源浪费和法规遵从性风险。 Campaign提供了用于在导入过程中验证、清理和扩充数据的工具。

**数据验证步骤：**

1. **预导入验证** — 验证文件格式、编码(UTF-8)、列映射、必填字段是否存在
2. **重复数据删除** — 使用&#x200B;**[!UICONTROL Deduplication]**&#x200B;活动通过电子邮件、ID或自定义密钥识别和处理重复项
3. **数据扩充** — 使用&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动从现有Campaign表中添加缺失的数据
4. **格式标准化** — 使用JavaScript或扩充功能标准化电话号码、电子邮件地址、日期、国家/地区代码
5. **验证规则** — 应用约束（有效的电子邮件格式、必填字段、值范围）

**常见问题和修复：**

* **字符编码错误** →始终使用UTF-8编码
* **日期格式不匹配** →标准化为YYYY-MM-DD格式
* **电子邮件地址无效** →使用验证规则或JavaScript进行筛选
* **重复记录** →更新前始终包含重复数据删除活动
* **缺少必填字段** →设置默认值或拒绝不完整的记录

**最佳实践：**&#x200B;创建一个可重复使用的“数据质量”工作流模板，该模板包含可应用于所有导入的标准验证和清理活动。

**相关主题：**

[数据质量指南](../start/import.md) | [重复数据删除活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=zh-Hans){target="_blank"} | [扩充活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=zh-Hans){target="_blank"}

+++

+++ Campaign中常见的工作流用例有哪些？

工作流可自动化营销流程，包括：

**数据管理：**&#x200B;导入/加载数据、清理、扩充、列表管理\
**营销活动自动化：**&#x200B;欢迎系列、生日营销活动、重新参与、购物车放弃\
**高级定位：** A/B测试、动态分段、潜在客户评分、跨渠道编排\
**监控：**&#x200B;工作流/投放监控、警报、数据库维护\
**集成：** CRM同步、API集成、事件触发的工作流

**相关主题：**

[工作流用例库](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [生成工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans){target="_blank"} | [工作流最佳实践](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何使用工作流更新 Campaign 数据？

使用&#x200B;**[!UICONTROL Update data]**&#x200B;活动进行批量数据库操作：插入（添加新记录）、更新（修改现有记录）、插入或更新（更新插入）、删除（删除匹配记录）。

**常见用法：**&#x200B;更新配置文件属性，与外部系统同步，维护列表成员资格，清除/删除重复数据，应用批量状态更改。

配置协调键值以实现准确匹配，并选择更新选项。

**相关主题：**

[更新数据活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=zh-Hans){target="_blank"} | [数据管理活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ 如何利用数据管理功能？

数据管理活动可实现复杂操作：扩充（从相关表中添加数据）、拆分（区段人口）、重复数据删除（删除重复项）、更新数据（批量操作）、更改维度（切换定位维度）、交集/并集/排除（组合/过滤人口）。

**常见用途：**&#x200B;通过购买/行为数据扩充、细分受众、删除重复项、集成外部数据库(FDA)、创建复杂的多表查询。

**相关主题：**

[数据管理活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [扩充活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=zh-Hans){target="_blank"}

+++

+++ 我能自动发送个性化的邮件吗？

是的。 构建自动化工作流：查询（目标受众）→扩充（添加个性化数据）→拆分（可选区段）→投放（个性化消息）→调度程序（定期执行）。

**Personalization：**&#x200B;使用配置文件数据、行为数据、条件内容、动态值。 常见情景：生日营销活动、购物车放弃、忠诚度计划、回馈、事件触发的消息。

**相关主题：**

[Personalization指南](../send/personalize.md) | [工作流使用案例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何使用工作流将受众分割到子集中？

使用&#x200B;**[!UICONTROL Split]**&#x200B;活动划分群体：过滤条件(年龄、位置、VIP状态)、百分比分布（A/B测试）、限制记录（前N个，前X%个）、数据分组（每个值一个子集）。

**常见用法：** A/B测试、通道偏好设置路由、渐进式转出、特定区段的消息传递、负载平衡。 每个子集流向不同的过渡以进行不同的处理。

**相关主题：**

[拆分活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=zh-Hans){target="_blank"} | [A/B测试指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ 如何通过外部文件更新收件人数据？

是的。 工作流：数据加载（文件） →扩充（可选）→协调（匹配键，如电子邮件/ID）→更新数据（更新匹配的记录，如果没有匹配项，则插入新记录）。

**常见用法：**&#x200B;从CRM更新配置文件属性，刷新订阅状态，同步会员积分，更新选择加入/选择退出首选项。

**最佳实践：**&#x200B;使用唯一标识符，首先验证数据，使用示例进行测试，计划定期更新。

**相关主题：**

[导入数据指南](../start/import.md) | [数据加载活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=zh-Hans){target="_blank"} | [更新数据活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何识别和定位新的收件人？

查询&#x200B;**[!UICONTROL Created date]**&#x200B;字段以选择在特定时间范围内添加的收件人。

**自动欢迎工作流：**&#x200B;计划程序（每日运行） →查询（选择新收件人）→重复数据删除（可选）→投放（欢迎消息）→更新数据（标记为“已欢迎”）。

**高级：**&#x200B;使用聚合函数动态标识最近添加的内容。

**相关主题：**

[查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hans){target="_blank"} | [使用聚合](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何使用工作流活动？

四个活动类别：

**定位：**&#x200B;查询、拆分、重复数据删除、扩充、交集、并集、排除（定义/优化受众）\
**流控制：**&#x200B;调度程序、等待、测试、分支、AND — 连接、OR — 连接、跳转（管理逻辑/计时）\
**操作：**&#x200B;投放，更新数据，数据加载/提取，JavaScript代码（执行操作）\
**事件：**&#x200B;外部信号、文件收集器、HTTP传输（对触发器做出反应）

从调色板拖动，双击进行配置，使用过渡连接。

**相关主题：**

[定位活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=zh-Hans){target="_blank"} | [流量控制](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=zh-Hans){target="_blank"} | [操作活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=zh-Hans){target="_blank"}

+++

+++ 什么是工作流最佳实践？

**设计：**&#x200B;清除名称、添加标签/描述、分组相关活动、将复杂的流程分解为较小的工作流\
**性能：**&#x200B;限制查询大小，使用临时表，计划非高峰期，避免过多的循环\
**错误处理：**&#x200B;添加错误路径，配置警报，使用示例进行测试，查看日志\
**维护：**&#x200B;存档过时的工作流、版本控制、限制复杂性（&lt;20个活动）、使用模板\
**安全性：**&#x200B;应用权限，清除临时数据，使用未硬编码值的变量

**相关主题：**

[工作流最佳实践指南](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=zh-Hans){target="_blank"} | [监视工作流](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=zh-Hans){target="_blank"}

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


**相关主题：**

[在Campaign Web UI中更改语言](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [开始使用Campaign客户端控制台](connect.md)

+++

+++ 什么是Campaign控制面板以及如何访问它？

Campaign控制面板是一个基于Web的管理界面，通过跨Campaign实例管理设置和监控使用情况，可帮助Campaign管理员提高效率。 它提供自助服务功能，无需联系Adobe支持即可管理关键实例配置。

**关键功能：**

* **子域管理** — 委派和管理子域，监视SSL证书
* **存储监视** — 跟踪数据库使用情况并防止存储问题
* 列入允许列表 **SFTP管理** — 监视SFTP存储、管理IP和SSH密钥
* 列入允许列表 **实例设置** — 配置IP，管理URL权限，查看实例详细信息
* **活动配置文件监控** — 根据授权跟踪活动配置文件使用情况
* **性能监视** — 监视数据库和工作流性能
* **电子邮件可投放性** — 配置DMARC、BIMI和其他身份验证记录

**访问要求：**

* **仅限管理员用户** -控制面板仅限具有管理员权限的用户
* **Adobe IMS身份验证** — 使用Adobe ID通过Adobe Experience Cloud进行访问
* **Campaign v8托管云服务** — 仅适用于托管实例

**其他资源：**

[控制面板文档](https://experienceleague.adobe.com/zh-hans/docs/control-panel/using/control-panel-home){target="_blank"} | [控制面板教程视频](https://experienceleague.adobe.com/zh-hans/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ 如何检查操作员和权限是否遵循安全最佳实践？

Adobe Campaign v8提供了将顶级管理帐户和特权帐户的所有当前设置与推荐的安全默认值进行比较的功能。

* **当前设置（完全可见）：**&#x200B;可以在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Access management]**（客户端控制台或Campaign Web UI）中查看管理员帐户和特权帐户的所有设置： **[!UICONTROL Operators]**、**[!UICONTROL Operator groups]**、**[!UICONTROL Named rights]**（例如管理、审批管理）和文件夹级别的权限。 产品管理员还可以在[Campaign控制面板 列入允许列表](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans){target="_blank"}中查看实例级设置（IP、URL权限、实例详细信息等）。
* **推荐的安全默认值：** [安全准则](../config/security.md)为管理和特权帐户定义推荐的安全基线，包括：创建足够的安全组，为每个操作员分配适当的访问权限，以及限制对管理员操作员和管理员组的使用。 如果适用，另请参阅用于网络和加密强化的[增强型安全加载项](../config/enhanced-security.md)。
* **比较：**&#x200B;管理员将其当前配置与这些有文档记录的建议进行比较，以找出差距并调整安全默认值。

**相关主题：**

[开始使用权限](gs-permissions.md) | [安全准则](../config/security.md) | [增强的安全附加组件](../config/enhanced-security.md)

+++

+++ 域委派的程序是怎样的？

子域是域的一个分支，可用于隔离您的品牌或各种类型的流量（交易消息、营销信息等）。

>[!NOTE]
>
>作为托管云服务用户，请联系 Adobe 以将子域委派给 Adobe。

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

**相关主题：**

[跟踪和监视投放](../send/tracking.md) | [配置跟踪的链接](../send/tracked-links.md) | [测试跟踪](../send/testing-tracking.md)

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

**相关主题：**

[关于Campaign中的可投放性](../send/about-deliverability.md) | [可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何访问存储在外部数据库中的数据？

Campaign v8提供联合数据访问(FDA)，无需更改Campaign数据模型即可查询和使用存储在外部数据库中的数据。 您可以配置外部帐户，然后在工作流、查询和定位中使用FDA将外部数据与Campaign用户档案相结合。

FDA可用性和连接要求取决于您的部署和许可。 查看兼容性矩阵中支持的数据库和所需的版本。

**相关主题：**

[配置FDA连接](../connect/fda.md) | [兼容性矩阵](compatibility-matrix.md)

+++

+++ 我能将 Campaign 连接到哪些外部数据库？

Campaign v8支持到主要企业数据库系统（云数据库、企业数据库、数据仓库、大数据平台）的联合数据访问(FDA)连接。

支持的数据库版本和连接要求各不相同。 检查Campaign v8版本的[兼容性矩阵](compatibility-matrix.md)，确认支持特定数据库，并确保FDA连接器获得正确许可。

请参阅[配置FDA连接](../connect/fda.md)

+++

+++ Adobe Campaign是否可以与CRM系统集成？

是的。 Campaign提供本机CRM连接器，用于与主要CRM系统进行双向同步。 同步联系数据、潜在客户、帐户、投放日志、跟踪数据和参与量度。 支持计划、手动和实时（通过API）同步模式。

使用Campaign的CRM连接器助手来映射字段、选择表和计划同步。 检查[兼容性矩阵](compatibility-matrix.md)以了解支持的CRM版本。

**相关主题：**

[CRM连接器配置](../connect/crm.md) | [工作流CRM活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=zh-Hans){target="_blank"}

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

**如果问题仍然存在（高级）：**

关闭客户端控制台，然后从用户配置文件中手动删除本地缓存文件。

**手动缓存清理(Windows)：**

1. 在客户端控制台中，选择&#x200B;**[!UICONTROL File]** > **[!UICONTROL Clear the local cache...]**。
2. 注销并关闭客户端控制台。
3. 根据您的Windows版本，转到缓存位置。 对于Windows 10： `C:\Users\<Username>\AppData\Roaming\Neolane\NL_5\`
4. 删除`nlclient-config-<alphanumerical>.xml`文件及其关联的文件夹。

>[!IMPORTANT]
>
>不删除`nlclient_cnx.xml`。

Adobe支持部门可以确认适用于您的版本和操作系统的正确缓存位置，并指导您完成安全的手动清理。

在[安装和配置客户端控制台](connect.md)中了解详情

+++

+++ Adobe Campaign 可与轻型目录访问协议 (LDAP) 相集成吗？

没有。Campaign v8不支持LDAP集成。 身份验证使用Adobe IMS(Adobe ID或Federated ID)。 如果您是从Campaign Classic v7迁移，请查看不支持的功能和身份验证更改。

**相关主题：**

[连接到Campaign v8](connect.md) | [v8](v7-to-v8.md#gs-removed)中不受支持的功能

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

**相关主题：**

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

**相关主题：**

[扩展数据模型](../dev/extend-schema.md) | [架构结构](../dev/schemas.md) | [数据模型最佳实践](../dev/datamodel-best-practices.md)

+++

## 报告 {#reporting}

深入了解Campaign的报告功能，包括内置的报告、自定义报告以及多维数据集等数据分析工具。

+++ 如何创建新报告？

Campaign会根据您的需求和技术专业知识提供多种报告选项：内置报告、描述性分析、客户端控制台中的自定义报告以及多维数据集。

**报告选项：**

* **内置报告** — 可从&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡访问的现成投放、营销活动和跟踪报告
* **描述性分析** — 具有向导驱动界面的任何数据的快速统计报告
* **自定义报告** — 技术用户使用报告编辑器生成的高级报告
* **多维数据集** — 多维数据探索和透视表分析

**重要信息：**&#x200B;营销活动专为营销运营报告而设计，而不是作为专门的业务智能工具。 为了满足复杂的分析需求，请考虑与Adobe Analytics或专用的BI平台集成。

**相关主题：**

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

了解有关[描述性分析](../reporting/built-in-reports.md)的更多信息

+++

+++ 如何根据我的数据设计高级报告？

使用客户端控制台创建具有复杂分析功能的高级自定义报告。

在客户端控制台中，您可以：

* 使用SQL查询和自定义计算构建复杂报表
* 创建包含图表、表和透视表的多页报表
* 设计条件格式和动态内容
* 访问完整的Campaign数据模型和外部数据库(FDA)

了解如何[创建自定义报告（客户端控制台）](../reporting/custom-reports.md)

+++

+++ 什么是多维数据集？如何将其用于报表？

多维数据集是多维数据结构，它使业务用户能够在没有技术技能的情况下通过透视表探索和分析Campaign数据。 将它们视为可简化复杂报表的预配置数据模型。 此报告工具在客户端控制台和Campaign Web UI中均可用。

* 技术用户创建和配置多维数据集，这些多维数据集定义维度（时间、地理位置、渠道）和度量（打开、点击、收入）
* 企业用户在创建报表时选择多维数据集，并拖放维度以浏览数据
* 根据多维数据集配置自动聚合和计算数据
* 结果可以显示为透视表、图表或导出到Excel

了解如何[使用多维数据集](../reporting/gs-cubes.md)浏览数据

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

**高级分析：**

* 从&#x200B;**[!UICONTROL Responses]**&#x200B;选项卡访问调查响应并导出数据
* 在工作流中使用&#x200B;**[!UICONTROL Survey responses]**&#x200B;活动，根据收件人的回答来定位收件人
* 将调查数据与其他Campaign数据相结合，以实现分段和个性化
* 创建自定义报告和多维数据集以进行多维度调查分析

**相关主题：**

[调查入门](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [调查报告](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ 如何共享对报告的访问权限？

通过Campaign中的文件夹权限和已命名权限控制报表可见性。

**访问控制方法：**

* **文件夹权限** — 将报告放入具有用户组相应访问权限的文件夹中
* **已命名的权限** — 分配查看、创建或修改报告的权限
* **显示上下文** — 定义报告的显示位置（报告文件夹、活动选项卡、投放屏幕）

**设置：**&#x200B;将报告保存到特定文件夹→配置操作员组的文件夹访问权限→定义报告属性和显示上下文。

**相关主题：**

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

**相关主题：**

[自定义报告](../reporting/custom-reports.md) | [Campaign Web UI报告](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## 开发人员 {#developers}

访问面向开发人员的技术信息，包括数据模型详细信息、架构、API和自定义功能。

+++ 什么是Campaign数据模型？

Campaign的数据模型是一个模式驱动的关系数据库结构，由内置的表（收件人、投放、营销活动）组成，可根据您的业务需求对其进行扩展。

**关键概念：**&#x200B;架构（XML定义）、内置表、链接（关系）、枚举（值列表）、扩展（自定义字段/表）。

**主架构：**&#x200B;收件人(`nms:recipient`)、投放(`nms:delivery`)、工作流(`xtk:workflow`)、营销活动(`nms:operation`)、跟踪日志。

了解数据模型对于工作流、查询、架构扩展和集成至关重要。

**相关主题：**

[Campaign数据模型](../dev/datamodel.md) | [数据模型最佳实践](../dev/datamodel-best-practices.md)

+++

+++ 如何使用 Campaign 模式？

架构以XML格式定义Campaign的数据结构，指定表结构、字段属性、关系、索引和访问控制。

**正在处理架构：**

* **查看：**&#x200B;通过&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;进行的访问
* **扩展：**&#x200B;创建扩展架构（如`cus:recipient`）以添加自定义字段而不修改核心架构
* **创建：**&#x200B;为特定于业务的数据生成新表
* **更新：**&#x200B;通过&#x200B;**[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;应用更改

**常见用法：**&#x200B;将自定义字段添加到收件人表，创建自定义表，定义关系，实施特定于业务的模型。

**重要信息：**&#x200B;从不直接修改内置架构。 请始终使用扩展架构以提高升级兼容性。

**相关主题：**

[开始使用架构](../dev/schemas.md) | [扩展架构](../dev/extend-schema.md)

+++

+++ 如何使用自定义收件人表？

在针对B2B帐户、单独的订阅者数据、外部系统或多品牌体系结构时，请使用自定义收件人表，而不是标准的收件人表。

**实施：**&#x200B;创建包含必填字段（电子邮件、主键、排除项）的自定义架构→配置目标映射→更新投放模板→调整工作流/查询。

**关键注意事项：**&#x200B;必须包括必需的投放字段，工作流/表单需要调整，在生产迁移之前必须执行关键测试。

**最佳实践：**&#x200B;首先扩展标准收件人表。 由于增加了复杂性，因此仅在真正必要时使用自定义表。

**相关主题：**

[自定义收件人表](../dev/custom-recipient.md) | [目标映射](../audiences/target-mappings.md)

+++

+++ 在 Campaign 中定义查询的最佳实践是什么？

Campaign的查询编辑器可以不使用工作流活动、投放定位、列表、报告和过滤器中的SQL而直观地构建数据库查询。

**最佳实践：**

* 开始简单 — 增量构建，测试每个步骤
* 使用过滤维度 — 利用表关系
* 优化性能 — 为查询字段编制索引，避免复杂的计算
* 重复使用预定义过滤器以保持一致性
* 首先使用小样本进行测试
* 记录复杂查询

**常见模式：**&#x200B;目标投放打开者，查找不活动的联系人，按行为分段，排除以前的收件人。

**访问：** **[!UICONTROL Tools > Generic query editor]**&#x200B;以进行临时探索。

**相关主题：**

[查询编辑器](../start/query-editor.md) | [查询活动](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=zh-Hans){target="_blank"}

+++

+++ 如何导入数据包？

在客户端控制台中通过&#x200B;**[!UICONTROL Tools > Advanced > Import package]**&#x200B;导入包。 资源包中包含用于在实例之间部署的Campaign配置（架构、工作流、类型）和数据。

**包类型：**&#x200B;用户包（自定义配置）、平台包(Adobe提供)、数据包（实际数据）。

**最佳实践：**&#x200B;首先在开发环境中测试，在导入之前进行备份，然后从相同/较旧的版本导出。

在[使用数据包](../dev/packages.md)中了解详情

+++

+++ 在哪里可以找到Campaign v8 API的列表？

Campaign v8提供SOAP API（客户端控制台操作）、REST API（现代集成）和JavaScript API（工作流脚本）。

**常见用途：**&#x200B;与CRM/ERP集成、自动执行营销活动、同步数据、生成监控解决方案、创建外部界面。

**访问：**&#x200B;[Campaign v8 API文档](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hans){target="_blank"}

+++


+++ 如何从API监测工作流？

Campaign API允许您以编程方式控制工作流：开始、暂停/恢复、停止、查询状态、检索日志、监控活动进度。

**API终结点：** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**命令：** `{"method":"start"}`，`{"method":"pause"}`，`{"method":"resume"}`，`{"method":"stop"}`

**用例：**&#x200B;构建监视仪表板，实施自动警报，从外部调度程序进行编排，跨实例创建依赖关系，生成自定义报告。

**最佳实践：**&#x200B;将API监视与审核跟踪结合使用，以实现全面治理。

查看[通过API控制工作流](../dev/api/controlling-a-workflow.md)

+++

+++ 如何更新数据库结构？

修改架构（添加字段、创建表、更改数据类型）后，通过&#x200B;**[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;更新物理数据库结构以应用更改。

**需要时：**&#x200B;添加字段、创建/扩展表、修改字段属性、添加/删除链接、创建索引。

**重要信息：**&#x200B;请先备份，在开发环境中测试，为大型更改规划停机时间，与Adobe支持（托管云服务）协调，请注意，某些更改可能会导致数据丢失。


**相关主题：**

[更新数据库结构](../dev/update-database-structure.md) | [扩展架构](../dev/extend-schema.md)

+++

## 隐私 {#privacy}

了解Adobe Campaign如何帮助您遵守GDPR和CCPA等隐私法规以及管理数据主体请求。

+++ Campaign中的关键隐私概念是什么？

Campaign通过用于管理数据主体权限、同意和数据保留的工具，帮助您遵守隐私法规(GDPR、CCPA、PDPA、LGPD)。 关键概念包括隐私法规、个人数据识别、数据主体权限（访问、删除、可移植性）、同意管理和数据保留策略。

作为“数据控制者”，您负责处理数据主体请求、维护同意记录并确保透明的数据使用。

了解有关[隐私管理](../start/privacy.md)的更多信息

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

了解有关[隐私管理](../start/privacy.md)的更多信息

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

**相关主题：**

[订阅服务](../start/subscriptions.md) | [隐私和同意](../start/privacy.md#consent-retention-roles) | [隐私管理](../start/privacy.md)

+++

+++ 处理删除请求时会删除哪些数据？

Campaign会自动删除链接到数据主体的所有数据：收件人用户档案、投放和跟踪日志、具有所有权关系的自定义数据以及订阅历史记录。

**工作方式：** Campaign删除架构定义中指向收件人的链接具有`integrity="own"`的所有数据，确保跨相关表进行级联删除。

您可以通过修改架构中的链接完整性来自定义删除范围，但请先咨询法律顾问。 删除是永久性的，无法撤消。

**相关主题：**

[隐私管理](../start/privacy.md) | [架构链接](../dev/schemas.md)

+++

+++ 隐私删除是否会影响我的投放报告？

没有。促销活动报表基于预先计算的汇总量度（发送总数、打开次数、点击次数），而不是针对单个日志的实时查询。 删除单个收件人数据不会更改历史聚合统计信息。

总体投放统计信息和性能量度保持不变，而单个跟踪日志和个人详细信息将被删除。 这样，您就可以在尊重数据主体权利的同时，维护营销分析。

**相关主题：**

[隐私管理](../start/privacy.md) | [报告](../reporting/gs-reporting.md)

+++

+++ 如何阻止重新导入已删除的数据？

您必须从所有源系统中删除数据，而不仅仅是Campaign。 数据通常从外部系统（CRM、电子商务、数据仓库）流动。

**必需的操作：**&#x200B;识别所有数据源、从源系统中删除、添加到排除/禁止列表、更新导入工作流以遵循删除标志，并记录该过程。

作为数据控制者，您负责在整个技术生态系统中完全删除数据。

**相关主题：**

[隐私管理](../start/privacy.md) | [导入工作流](../config/workflows.md)

+++

+++ 已删除的用户能否再次选择加入？

是的。 删除后，数据主体可以再次选择加入。 Campaign会创建一个全新的收件人记录，其中不包含指向之前已删除数据的链接 — 该用户档案从头开始创建。

Campaign的审核记录会记录删除事件和新用户档案的创建，以展示合规性，并显示在删除后会免费提供新的选择加入。

**相关主题：**

[隐私管理](../start/privacy.md) | [订阅](../start/subscriptions.md)

+++

## 仍然需要帮助？ {#get-help}

找不到您要查找的内容？ 以下是帮助您成功使用Adobe Campaign v8的其他资源。

### 社区支持

与其他Campaign用户和Adobe专家联系，分享知识并获得答案。

* **[Adobe Campaign社区](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=zh-Hans){target="_blank"}** — 提问、共享解决方案并与Campaign社区建立联系
* **[Experience League论坛](https://experienceleaguecommunities.adobe.com/?profile.language=zh-Hans){target="_blank"}** — 浏览所有Adobe产品的讨论
* **[Campaign社区办公时间](https://experienceleague.adobe.com/zh-hans){target="_blank"}** — 与Adobe专家一起参加实时会议

### 文档与学习

访问全面的指南、教程和培训材料。

* **[Campaign教程](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=zh-Hans){target="_blank"}** — 逐步视频指南和实践教程
* **[新增功能](whats-new.md)** — 最新特性和功能
* **[发行说明](release-notes.md)** — 当前和以前的发行信息
* **[版本和升级](upgrades.md)** — 了解Campaign的版本、升级以及如何检查您的版本

### 技术资源

查找详细的技术文档和开发人员资源。

* **[Campaign API](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hans){target="_blank"}** — 完整API参考文档
* **[兼容性矩阵](compatibility-matrix.md)** — 支持的系统和版本
* **[版本和升级常见问题解答](upgrades.md)** — 检查您的版本并了解升级情况

### 支持和服务

从Adobe支持团队获取帮助并管理您的实例。

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** — 记录支持案例并管理用户
* **[Adobe客户关怀](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** — 联系支持团队
* **[控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans){target="_blank"}** — 管理您的Campaign实例设置
* **[系统状态](https://status.adobe.com/){target="_blank"}** — 检查Adobe服务状态

### 培训和认证

通过官方的Adobe培训和认证计划提升您的技能。

* **[Experience League帮助](https://experienceleague.adobe.com/zh-hans/browse/campaign/campaign-v8){target="_blank"}** - Campaign v8的帮助资源（Web UI和CLient控制台）
* **[Adobe数字学习服务](https://learning.adobe.com/){target="_blank"}** — 官方讲师指导课程和自学课程
* **[Adobe Campaign认证](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=zh-Hans){target="_blank"}** — 通过专业认证验证您的专业知识
* **[Experience League学习路径](https://experienceleague.adobe.com/zh-hans?lang=en#dashboard/learning){target="_blank"}** — 引导式学习历程

### 其他有用资源

* **[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=zh-Hans){target="_blank"}** - Classic v7用户参考
* **[Campaign Web UI文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}** — 新Web界面指南
* **[可投放性最佳实践](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans){target="_blank"}** — 优化电子邮件投放
