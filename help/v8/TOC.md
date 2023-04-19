---
audience: end-user
user-guide-title: Campaign v8
description: Campaign v8 文档
breadcrumb-title: Campaign 概述
title: Campaign v8 文档
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 94%

---


# Adobe Campaign v8 文档 {#campaign-v8}

+ [Campaign v8 文档](campaign-home.md)
+ 版本和最新更新 {#releases}
   + [早期发行说明](start/e-release-notes.md)
   + [发行说明](start/release-notes.md)
   + 之前的发行说明 {#previous-rn}
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [护栏](start/ac-guardrails.md)
   + [已知问题](start/known-issues.md)
   + [兼容性矩阵](start/compatibility-matrix.md)
+ 入门 {#new}
   + [Adobe Campaign 入门](start/get-started.md)
   + [重要功能](start/whats-new.md)
   + [组件和流程](start/ac-components.md)
   + [连接到 Campaign](start/connect.md)
   + Campaign UI {#ac-ui}
      + [了解 Campaign 界面](start/campaign-ui.md)
      + [自定义 Campaign 界面](start/customize-ui.md)
      + [管理文件夹和视图](audiences/folders-and-views.md)
   + [从 Classic v7 到 v8](start/v7-to-v8.md)
   + [常见问题解答](start/campaign-faq.md)
+ Campaign 管理 {#campaigns}
   + [活动入门](start/campaigns.md)
   + [营销活动编排 >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=zh-Hans)
   + 发送消息 {#send}
      + [消息入门](start/create-message.md)
      + [使用投放模板](send/create-templates.md)
      + 电子邮件 {#emails}
         + [设计和验证电子邮件](send/email.md)
         + [链接到镜像页面](send/mirror-page.md)
         + [发送和监测电子邮件](send/send.md)
      + [短信](send/sms.md)
      + [推送通知](send/push.md)
      + [LINE 消息](send/line.md)
      + [直邮](send/direct-mail.md)
      + [Twitter](send/twitter.md)
      + 事务性消息 {#real-time}
         + [事务型消息入门](send/transactional.md)
         + [创建和发布模板](send/transactional-template.md)
         + 事件管理 {#event}
         + [收集和处理事件](send/event-processing.md)
         + [了解事件描述](send/event-description.md)
         + [发送和监视消息](send/delivery-execution.md)
      + 失败、退回和隔离{#failures}
         + [隔离](send/quarantines.md)
         + [投放失败](send/delivery-failures.md)
      + [发送时间优化](send/predictive.md)
      + [管理订阅](start/subscriptions.md)
      + 个性化内容{#personalize}
         + [个性化入门](send/personalize.md)
         + [个性化数据](send/personalization-data.md)
         + [添加个性化字段](send/personalization-fields.md)
         + [使用个性化块](send/personalization-blocks.md)
         + [创建条件](send/conditions.md)
      + 验证投放{#validate}
         + [预览和验证](send/preview-and-proof.md)
         + [投放分析](send/delivery-analysis.md)
+ 用户档案和受众管理 {#audience}
   + [用户档案和受众入门](audiences/gs-audiences.md)
   + [使用受众](start/audiences.md)
   + [访问用户档案](audiences/view-profiles.md)
   + 添加用户档案 {#add-profiles}
      + [手动创建用户档案](audiences/create-profiles.md)
      + [从文件导入用户档案](audiences/import-profiles.md)
      + [使用外部用户档案](audiences/external-profiles.md)
      + [在 Web 窗体中收集用户档案数据](audiences/collect-profiles.md)
      + [使用目标映射](audiences/target-mappings.md)
   + 创建受众 {#create-audiences}
      + [创建联系人列表](audiences/create-audiences.md)
      + [创建和管理过滤器](audiences/create-filters.md)
   + [与 Adobe 解决方案共享受众](start/shared-audiences.md)
   + [最佳实践](audiences/audiences-best-practices.md)
+ 内容管理 {#content}
   + [设计 Web 应用程序和表单](dev/webapps.md)
+ 隐私和安全管理 {#privacy}
   + [管理隐私请求](start/privacy.md)
   + [安全准则](config/security.md)
+ 决策管理 {#offers}
   + [实时互动入门](interaction/interaction.md)
   + [环境和架构](interaction/interaction-architecture.md)
   + [最佳实践](interaction/interaction-best-practices.md)
   + 定义设置{#interaction-settings}
      + [创建运算符](interaction/interaction-operators.md)
      + [创建环境](interaction/interaction-env.md)
      + [创建预定义过滤器](interaction/interaction-predefined-filters.md)
      + [创建优惠空间](interaction/interaction-offer-spaces.md)
   + [创建优惠目录](interaction/interaction-offer-catalog.md)
   + [创建优惠](interaction/interaction-offer.md)
   + [发送优惠（出站）](interaction/interaction-send-offers.md)
   + 提供优惠（入站）{#inbound}
      + [上下文](interaction/interaction-present-offers.md)
      + [在网页中调用优惠](interaction/interaction-integration.md)
      + [管理匿名互动](interaction/anonymous-interactions.md)
   + [报告和历史记录](interaction/interaction-tracking.md)
   + [用例](interaction/interaction-use-cases.md)
+ 报告和分析 {#analytics}
   + [跟踪和监测](start/tracking.md)
   + 使用报告{#reports}
      + [报告入门](reporting/gs-reporting.md)
      + 创建多维数据集{#cubes}
         + [多维数据集入门](reporting/gs-cubes.md)
         + [创建多维数据集](reporting/cube-indicators.md)
         + [使用多维数据集创建报告](reporting/cube-tables.md)
         + [自定义多维数据集](reporting/customize-cubes.md)
      + 内置报告{#ac-reports}
         + [内置报告列表](reporting/built-in-reports.md)
         + [全局报告](reporting/global-reports.md)
         + [投放报告](reporting/delivery-reports.md)
         + [内置量度计算](reporting/metrics-calculation.md)
      + [自定义报告](reporting/custom-reports.md)
+ 数据管理 {#data}
   + [工作流入门](config/workflows.md)
   + [导入数据](start/import.md)
   + [工作流文档](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=zh-Hans)
+ 集成 {#connect}
   + [将 Campaign 与其他解决方案配合使用](connect/integration.md)
   + [Campaign + Experience Platform](connect/ac-aep.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Experience Cloud Triggers](connect/ac-triggers.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + 外部数据库](connect/fda.md)
   + Campaign + 您的 CRM {#ac-crm}
      + [CRM 连接器入门](connect/crm.md)
      + [使用 Campaign 和 SFDC](connect/ac-sfdc.md)
      + [使用 Campaign 和 Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [同步数据](connect/crm-data-sync.md)
+ 管理 {#admin}
   + 用户和权限 {#permissions}
      + [权限入门](start/gs-permissions.md)
      + [管理用户权限](start/manage-permissions.md)
      + [添加文件夹权限](start/folder-permissions.md)
   + [控制面板](config/self-service.md)
+ 架构和配置 {#config}
   + 架构 {#architecture}
      + [全局原则](architecture/general-architecture.md)
      + [架构](architecture/architecture.md)
      + FDA Snowflake 部署 {#fda}
         + [什么是 FDA-Snowflake？](architecture/fda-deployment.md)
      + 企业 (FFDA) 部署{#ffda}
         + [什么是 Campaign FFDA？](architecture/enterprise-deployment.md)
         + 特征 {#ffda-characteristics}
            + [密钥管理和唯一性](architecture/keys.md)
            + [新 API](architecture/new-apis.md)
            + [API 暂存机制](architecture/staging.md)
            + [复制机制](architecture/replication.md)
   + 实施 {#implement}
      + [实施步骤](start/implement.md)
      + [自定义实例](dev/customize.md)
      + [数据模型最佳实践](dev/datamodel-best-practices.md)
   + 设置和配置 {#configuration}
      + [用户界面设置](config/ui-settings.md)
      + [电子邮件设置](config/email-settings.md)
      + [事务性消息设置](config/transactional-msg-settings.md)
      + [将 Campaign SDK 与您的应用程序集成  — 已弃用页面](config/push-config.md)
      + [外部帐户](config/external-accounts.md)
+ 开发人员资源 {#developer}
   + [Campaign 数据模型](dev/datamodel.md)
   + 模式和表单{#shemas-forms}
      + [使用模式](dev/schemas.md)
      + [创建模式](dev/create-schema.md)
      + [扩展模式](dev/extend-schema.md)
      + [筛选模式](dev/filter-schema.md)
      + [模式结构](dev/schema-structure.md)
      + [数据库映射](dev/database-mapping.md)
      + [限制 PI 视图](dev/restrict-pi-view.md)
      + [使用自定义收件人表格](dev/custom-recipient.md)
      + [更新数据库](dev/update-database-structure.md)
      + [输入表单](dev/forms.md)
   + [Campaign API](dev/api.md)
+ [Campaign 控制面板 >](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)
+ [Campaign 自动化指南 >](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=zh-Hans)
