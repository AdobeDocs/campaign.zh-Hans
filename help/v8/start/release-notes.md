---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: ba27d1e56f7354e500e747f01a27412f8d553e2b
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 21%

---

# 最新版本 {#latest-release}

本页列出了Campaign v8 （控制台）**最新版本**&#x200B;中的新功能、改进和修复。 在[此页面](upgrades.md)中了解有关Campaign版本、版本和升级的详细信息。 其他版本列于本文档的先前版本部分。

>[!BEGINSHADEBOX]

在此页中&#x200B;****

* Campaign v8.6 - [版本8.6.4](#release-8-6-4)
* Campaign v8.7 - [版本8.7.3](#release-8-7-3)

>[!ENDSHADEBOX]


## 版本 8.7.3 {#release-8-7-3}

_2025 年 2 月 14 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#features-8-7-3}

* **事务性消息的动态报告** — 您现在可以在动态报告用户界面中监视事务性消息。 通过这些报表，营销人员能够实时查看事务型消息的所有报表量度和维度，以及通过模板发送的投放的细分。 [了解更多信息](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **事务性消息传递REST API** — 现在为电子邮件提供了基于事件的事务性API。 [了解更多信息](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### 修复 {#fixes-8-7-3}

此版本中修复了以下问题：

NEO-79373， NEO-81908， NEO-83081。


## 版本 8.6.4 {#release-8-6-4}

_2025年1月15日_

### 一般改进 {#improvements-8-6-4}

* 在[Enterprise (FFDA)部署](../../v8/architecture/enterprise-deployment.md)上下文中的投放分析期间，营销活动应用程序稳定性已得到改进。
* 此版本附带改进和增强的FFDA架构机制，包括密钥管理、暂存和数据复制。
* 已为[企业(FFDA)部署](../../v8/architecture/enterprise-deployment.md)引入新的技术工作流。 这些工作流通过将并行复制请求集中到相应的表中，来复制投放和相关数据。 这些工作流以`Replicate nms`开头。 [了解更多信息](../architecture/replication.md)
* 工作流属性中现在有新的&#x200B;**启用监视程序监督器以保持工作流永久运行**&#x200B;选项。 启用此选项后，工作流会在发生错误后自动重新启动。 如果工作流仍然出错，默认情况下，每30秒重新启动一次。 要调整此间隔，您可以创建一个新的`XtkWorkflow_WatchdogTimerTimeout`选项并设置Integer数据类型以指定新延迟。 此选项只应在技术工作流中启用。 [了解更多信息](../../automation/workflow/workflow-properties.md#execution)

### 安全性改进 {#security-8-6-4}

已更新通过&#x200B;**[!UICONTROL Adobe Experience Cloud]**&#x200B;外部帐户与Adobe解决方案和应用程序的连接，以加强安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 兼容性更新 {#comp-8-6-4}

* 现在支持将 Databricks 用作 Adobe Campaign 联合数据访问 (FDA) 的外部数据库。请参阅[此页面](compatibility-matrix.md#FederatedDataAccessFDA)以了解详情。

* 现已提供新的Amazon Redshift FDA ODBC连接器。 它提供了改进的连接性、更轻松的维护以及增强的兼容性。 此新版本提供了以下改进：

   * 新的连接器基于ODBC接口，该接口与我们最新的FDA连接器一致。 这可确保长期支持。
   * 它还引入了一种使用s3存储桶的新数据加载机制，显着提高了性能。

  仍可使用旧版连接器。 如果您想要试用新版，请联系您的Adobe代表。

### 修复 {#fixes-8-6-4}

此版本中修复了以下问题：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512 NEO-81520， NEO-81566， NEO-81704， NEO-81908， NEO-82195， NEO-82591， NEO-82592， NEO-82640， NEO-82665， NEO-82781， NEO-82920， NEO-83081 83096 83137 83143。

