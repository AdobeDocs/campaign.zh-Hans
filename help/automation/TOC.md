---
audience: user
user-guide-title: Campaign 自动化指南
user-guide-description: Campaign 自动化指南
source-git-commit: 75b65efce6b37e3d948f6af4a89ea3b0a5ac1a86
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 84%

---


# Campaign自動化指南 {#automation}

+ [Campaign 自动化指南](home.md)
+ 使用工作流实现自动化 {#workflows}
   + 工作流入门 {#introduction}
      + [关于工作流](workflow/about-workflows.md)
      + 工作流程型別 {#wf-type}
         + [定位工作流](workflow/targeting-workflows.md)
         + [活动工作流](workflow/campaign-workflows.md)
         + [技术工作流](workflow/technical-workflows.md)
      + [构建工作流](workflow/build-a-workflow.md)
      + [最佳实践](workflow/workflow-best-practices.md)
      + [使用工作流数据](workflow/use-workflow-data.md)
   + 执行工作流{#executing-a-workflow}
      + [开始工作流](workflow/start-a-workflow.md)
      + [工作流生命周期](workflow/workflow-life-cycle.md)
      + [設定核准](workflow/define-approvals.md)
   + 监测工作流{#monitoring-workflows}
      + [监测工作流执行](workflow/monitor-workflow-execution.md)
      + [监测技术工作流](workflow/monitor-technical-workflows.md)
      + [工作流热图](workflow/heatmap.md)
   + 工作流活动 {#wf-activities}
      + [開始使用活動](workflow/activities.md)
      + 定位活动 {#targeting-activities}
         + [目標定位活動清單](workflow/targeting-activities.md)
         + [单元格](workflow/cells.md)
         + [更改数据源](workflow/change-data-source.md)
         + [更改维度](workflow/change-dimension.md)
         + [CRM 连接器](workflow/crm-connector.md)
         + [重复数据删除](workflow/deduplication.md)
         + [投放概要](workflow/delivery-outline.md)
         + [编辑架构](workflow/edit-schema.md)
         + [扩充](workflow/enrichment.md)
         + [排除](workflow/exclusion.md)
         + [增量查询](workflow/incremental-query.md)
         + [交集](workflow/intersection.md)
         + [列表更新](workflow/list-update.md)
         + [单元格优惠](workflow/offers-by-cell.md)
         + [优惠引擎](workflow/offer-engine.md)
         + [查询](workflow/query.md)
         + [读取列表](workflow/read-list.md)
         + [拆分](workflow/split.md)
         + [订阅服务](workflow/subscription-services.md)
         + [并集](workflow/union.md)
         + [更新数据](workflow/update-data.md)
      + 流量控制活动 {#flow-control-activities}
         + [流量控制活動清單](workflow/flow-control-activities.md)
         + [警报](workflow/alert.md)
         + [AND-连接](workflow/and-join.md)
         + [审批](workflow/approval.md)
         + [外部信号](workflow/external-signal.md)
         + [分叉](workflow/fork.md)
         + [跳转（开始点和结束点）](workflow/jump--start-point-and-end-point-.md)
         + [开始和结束](workflow/start-and-end.md)
         + [调度程序](workflow/scheduler.md)
         + [子工作流](workflow/sub-workflow.md)
         + [测试](workflow/test.md)
         + [时间约束](workflow/time-constraint.md)
         + [等待](workflow/wait.md)
      + 操作活动 {#action-activities}
         + [動作活動清單](workflow/action-activities.md)
         + [内容管理](workflow/content-management.md)
         + [连续投放](workflow/continuous-delivery.md)
         + [跨渠道投放](workflow/cross-channel-deliveries.md)
         + [数据提取（文件）](workflow/extraction--file-.md)
         + [数据加载（文件）](workflow/data-loading--file-.md)
         + [数据加载 (RDBMS)](workflow/data-loading--rdbms-.md)
         + [投放](workflow/delivery.md)
         + [投放控制](workflow/delivery-control.md)
         + [本地审批](workflow/local-approval.md)
         + [加载 (SOAP)](workflow/loading-soap.md)
         + [Nlserver 模块](workflow/nlserver-module.md)
         + [循环投放](workflow/recurring-delivery.md)
         + [SQL 代码和 JavaScript 代码](workflow/sql-code-and-javascript-code.md)
         + [SQL 数据管理](workflow/sql-data-management.md)
         + [更新聚合](workflow/update-aggregate.md)
      + 事件活动 {#event-activities}
         + [事件活動清單](workflow/event-activities.md)
         + [文件收集器](workflow/file-collector.md)
         + [文件传输](workflow/file-transfer.md)
         + [入站电子邮件](workflow/inbound-emails.md)
         + [入站短信](workflow/inbound-sms.md)
         + [Web 下载](workflow/web-download.md)
   + 用例 {#use-cases}
      + [关于工作流用例](workflow/workflow-use-cases.md)
      + 投放 {#deliveries}
         + [使用本地审批活动](workflow/local-approval-activity.md)
         + [发送生日电子邮件](workflow/send-a-birthday-email.md)
         + [加载投放内容](workflow/load-delivery-content.md)
         + [跨渠道投放工作流](workflow/cross-channel-delivery-workflow.md)
         + [具有自定义日期字段的电子邮件扩充](workflow/email-enrichment-with-custom-date-fields.md)
      + 监测 {#monitoring}
         + [向列表发送报告](workflow/send-a-report-to-a-list.md)
         + [监督工作流](workflow/workflow-supervision.md)
         + [向操作员发送个性化提醒](workflow/send-alerts-to-operators.md)
      + 数据管理 {#data-management}
         + [协调数据更新](workflow/coordinate-data-updates.md)
         + [创建摘要列表](workflow/create-a-summary-list.md)
         + [丰富数据](workflow/enrich-data.md)
         + [使用聚合](workflow/using-aggregates.md)
         + [使用重复数据删除活动的合并功能](workflow/deduplication-merge.md)
         + [设置循环导入工作流](workflow/recurring-import-workflow.md)
      + 设计查询 {#designing-queries}
         + [使用增量查询每季度更新列表](workflow/quarterly-list-update.md)
      + 查询和筛选{#designing-queries}
         + [查询收件人表](workflow/querying-recipient-table.md)
         + [查询投放信息](workflow/query-delivery-info.md)
         + [計算彙總](workflow/compute-aggregates.md)
         + [使用分组管理进行查询](workflow/query-grouping-management.md)
         + [使用多对多关系进行查询](workflow/query-many-to-many-relationship.md)
         + [添加明细列表类型计算字段](workflow/adding-enumeration-type-calculated-field.md)
         + [创建筛选](workflow/create-a-filter.md)
         + [筛选重复的收件人](workflow/filter-duplicated-recipients.md)
   + 高级设置 {#advanced-management}
      + [工作流属性](workflow/workflow-properties.md)
      + [高级参数](workflow/advanced-parameters.md)
      + [JavaScript 脚本和模板](workflow/javascript-scripts-and-templates.md)
      + [工作流中的 JavaScript 代码示例](workflow/javascript-in-workflows.md)
      + [访问外部数据库](workflow/accessing-an-external-database--fda-.md)
      + [管理权限](workflow/managing-rights.md)
      + [更改活动图像](workflow/change-activity-images.md)
      + [管理时区](workflow/managing-time-zones.md)
+ 营销活动编排 {#campaign-orchestration}
   + [营销活动入门](campaigns/set-up-campaigns.md)
   + [建立方案和行銷活動](campaigns/marketing-campaign-create.md)
   + [创建和配置模板](campaigns/marketing-campaign-templates.md)
   + [添加投放](campaigns/marketing-campaign-deliveries.md)
   + [选择受众](campaigns/marketing-campaign-target.md)
   + [管理文档和资产](campaigns/marketing-campaign-assets.md)
   + [设置和管理审批](campaigns/marketing-campaign-approval.md)
   + [循環和定期行銷活動](campaigns/recurring-periodic-campaigns.md)
   + [监测活动](campaigns/marketing-campaign-monitoring.md)
   + [供应商、库存和预算](campaigns/providers--stocks-and-budgets.md)
+ 行銷活動最佳化（附加元件）{#campaign-optimization}
   + [開始使用行銷活動型別](campaign-opt/campaign-typologies.md)
   + [筛选规则](campaign-opt/filtering-rules.md)
   + [控制规则](campaign-opt/control-rules.md)
   + [压力规则](campaign-opt/pressure-rules.md)
   + [一致性规则](campaign-opt/consistency-rules.md)
   + [应用规则](campaign-opt/apply-rules.md)
   + [活动模拟](campaign-opt/campaign-simulations.md)
+ 行銷資源管理（附加元件）{#mrm}
   + [開始使用行銷資源管理](mrm/about-marketing-resource-management.md)
   + [创建和管理任务](mrm/creating-and-managing-tasks.md)
   + [控制成本](mrm/controlling-costs.md)
   + [管理营销资源](mrm/managing-marketing-resources.md)
   + [论坛](mrm/discussion-forums.md)
+ 分散式行銷（附加元件） {#distributed-marketing}
   + [開始使用分散式行銷](distributed-marketing/about-distributed-marketing.md)
   + [创建本地活动](distributed-marketing/creating-a-local-campaign.md)
   + [创建协作活动](distributed-marketing/creating-a-collaborative-campaign.md)
   + [发布活动包](distributed-marketing/publishing-the-campaign-package.md)
   + [访问活动](distributed-marketing/accessing-campaigns.md)
   + [跟踪活动](distributed-marketing/tracking-a-campaign.md)
   + [用例](distributed-marketing/examples.md)
+ [Campaign v8檔案](https://experienceleague.adobe.com/docs/campaign/campaign-v8/campaign-home.html?lang=zh-Hans)