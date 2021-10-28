---
audience: end-user
user-guide-title: Campaign v8
description: Campaign v8 文档
breadcrumb-title: Campaign v8
title: Campaign v8 文档
source-git-commit: 889400a238f32968464f1425bb7d6c2dc3ff3cd0
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 86%

---


# Adobe Campaign v8 文档 {#campaign-v8}

+ [Campaign v8 文档](campaign-home.md)
+ 新增功能 {#start}
   + [重要功能](start/whats-new.md)
   + [发行说明](start/release-notes.md)
   + [已知限制](start/known-limitations.md)
   + [Classic v7 到 v8](start/capability-matrix.md)
+ 开始 {#start}
   + [入门](start/get-started.md)
   + [用户档案和受众](start/audiences.md)
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
+ 发送{#send}
   + [电子邮件](send/email.md)
   + [短信](send/sms.md)
   + [推送通知](send/push.md)
   + [LINE 消息](send/line.md)
   + [直邮](send/direct-mail.md)
   + [事务性消息](send/transactional.md)
   + 通过Campaign交互管理优惠{#interaction}
      + [实时互动入门](send/interaction.md)
      + [环境和架构](send/interaction-architecture.md)
      + [最佳实践](send/interaction-best-practices.md)
      + 定义设置{#interaction}
         + [创建运算符](send/interaction-operators.md)
         + [创建环境](send/interaction-env.md)
         + [创建预定义过滤器](send/interaction-predefined-filters.md)
         + [创建优惠空间](send/interaction-offer-spaces.md)
      + [创建优惠目录](send/interaction-offer-catalog.md)
      + [创建优惠](send/interaction-offer.md)
      + [发送优惠 （出站）](send/interaction-send-offers.md)
      + 提供选件（入站）{#inbound}
         + [上下文](send/interaction-present-offers.md)
         + [在网页中调用选件](send/interaction-integration.md)
         + [管理匿名交互](send/anonymous-interactions.md)
      + [报告和历史记录](send/interaction-tracking.md)
      + [用例](send/interaction-use-cases.md)
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
   + [Campaign + 您的 CRM](connect/crm.md)
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
