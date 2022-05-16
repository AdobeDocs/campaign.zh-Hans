---
audience: end-user
user-guide-title: Campaign v8
description: Campaign v8 文档
breadcrumb-title: Campaign v8
title: Campaign v8 文档
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 94%

---


# Adobe Campaign v8 文档 {#campaign-v8}

+ [Campaign v8 文档](campaign-home.md)
+ 新增功能 {#new}
   + [重要功能](start/whats-new.md)
   + [发行说明](start/release-notes.md)
   + [已知限制](start/known-limitations.md)
   + [Classic v7 到 v8](start/capability-matrix.md)
+ 开始 {#start}
   + [入门](start/get-started.md)
   + [组件和流程](start/ac-components.md)
   + Campaign UI {#ac-ui}
      + [了解 Campaign 界面](start/campaign-ui.md)
      + [自定义 Campaign 界面](start/customize-ui.md)
   + [使用受众](start/audiences.md)
   + [导入数据](start/import.md)
   + [创建活动](start/campaigns.md)
   + [发送消息](start/create-message.md)
   + [管理订阅](start/subscriptions.md)
   + [跟踪和监测](start/tracking.md)
   + [指标和报表](start/reporting.md)
   + [常见问题解答](start/campaign-faq.md)
+ 实施 {#implement}
   + [实施步骤](start/implement.md)
   + [自定义实例](dev/customize.md)
   + [安全准则](config/security.md)
   + [设计 Web 应用程序和表单](dev/webapps.md)
   + [数据模型最佳实践](dev/datamodel-best-practices.md)
+ 部署 {#deploy}
   + [兼容性矩阵](start/compatibility-matrix.md)
   + [连接到 Campaign](start/connect.md)
   + [权限](start/permissions.md)
   + [控制面板](config/self-service.md)
+ 用户档案和受众 {#profiles-and-audiences}
   + [入门](audiences/gs-audiences.md)
   + [访问用户档案](audiences/view-profiles.md)
   + 添加用户档案 {#add-profiles}
      + [手动创建用户档案](audiences/create-profiles.md)
      + [从文件导入用户档案](audiences/import-profiles.md)
      + [使用外部用户档案](audiences/external-profiles.md)
      + [在 Web 窗体中收集用户档案数据](audiences/collect-profiles.md)
   + 创建受众 {#create-audiences}
      + [创建联系人列表](audiences/create-audiences.md)
      + [创建和管理过滤器](audiences/create-filters.md)
   + [管理文件夹和视图](audiences/folders-and-views.md)
   + [最佳实践](audiences/audiences-best-practices.md)
+ 发送消息{#send}
   + [电子邮件](send/email.md)
   + [短信](send/sms.md)
   + [推送通知](send/push.md)
   + [LINE 消息](send/line.md)
   + [直邮](send/direct-mail.md)
   + [社交媒体营销](send/twitter.md)
   + [事务性消息](send/transactional.md)
   + 失败、退回和隔离{#failures}
      + [隔离](send/quarantines.md)
      + [投放失败](send/delivery-failures.md)
+ 实时互动{#interaction}
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
+ 配置{#config}
   + [使用工作流实现自动化](config/workflows.md)
   + [管理数据](config/replication.md)
   + [电子邮件设置](config/email-settings.md)
   + [事务性消息设置](config/transactional-msg-settings.md)
   + [将 Campaign SDK 与您的应用程序集成](config/push-config.md)
   + [外部帐户](config/external-accounts.md)
+ 连接{#connect}
   + [与其他解决方案配合使用](connect/integration.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Experience Cloud Triggers](connect/ac-triggers.md)
   + [Campaign + RTCDP](connect/ac-rtcdp.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + 外部数据库](connect/fda.md)
   + Campaign + 您的 CRM {#ac-crm}
      + [CRM连接器入门](connect/crm.md)
      + [使用Campaign和SFDC](connect/ac-sfdc.md)
      + [使用Campaign和Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [同步数据](connect/crm-data-sync.md)
+ 开发人员资源{#architecture}
   + [全局原则](dev/general-architecture.md)
   + [架构](dev/architecture.md)
   + [数据模型](dev/datamodel.md)
   + 模式和表单{#shemas-forms}
      + [使用模式](dev/schemas.md)
      + [密钥管理和唯一性](dev/keys.md)
      + [创建模式](dev/create-schema.md)
      + [扩展模式](dev/extend-schema.md)
      + [筛选模式](dev/filter-schema.md)
      + [模式结构](dev/schema-structure.md)
      + [数据库映射](dev/database-mapping.md)
      + [限制 PI 视图](dev/restrict-pi-view.md)
      + [使用自定义收件人表格](dev/custom-recipient.md)
      + [更新数据库](dev/update-database-structure.md)
      + [输入表单](dev/forms.md)
   + API {#api}
      + [入门](dev/api.md)
      + [新 API](dev/new-apis.md)
      + [API 暂存机制](dev/staging.md)
+ [Campaign 控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)
