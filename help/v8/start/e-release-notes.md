---
title: 早期 Campaign v8 发行说明
description: 早期 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 68%

---

# 早期发行说明 {#e-new-release}

此页面介绍了下一个 Campaign v8 版本中包含的改进和修复。在发行之日前，此内容可能会有所变动，恕不另行通知。[此页面](../start/release-notes.md)中提供了正式的发行说明。

## 版本 8.6.1 {#release-8-6-1}

_2024 年 2 月 14 日_


### 新增功能 {#new-8-6-1}

* 从此版本开始，您可以访问新的 **Campaign Web 用户界面**，该界面可通过中央 Adobe Experience Cloud 环境使用。Experience Cloud 是 Adobe 的数字营销应用程序、产品和服务的集成系列。通过其直观的界面，您可以快速访问云应用程序、产品功能和服务。[在此页面中](campaign-ui.md#ac-web-ui)了解如何连接到 Adobe Experience Cloud 并访问 Adobe Campaign Web 界面。

* 客户端控制台的32位版本现已弃用。 从8.6开始，客户端控制台将仅以64位提供。 客户端控制台可无缝升级到64位版本。 有关如何升级操作系统的详细信息，请参阅此 [技术说明](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=zh-Hans){target="_blank"}.


### 一般改进 {#improvements-8-6-1}

* Campaign v8.6 提高了&#x200B;**电子邮件投放跟踪指标的吞吐量**。通过我们优化的流程，可以减少跟踪收录和计算时间，并且可以更快地检查投放关键指标。

* 您现在可以将Campaign v8实例连接到Azure synapse外部数据库。 此连接通过新的外部帐户管理。

* Adobe Campaign v8现在集成了 **Adobe Experience Manager as a Cloud Service**，创作功能通过Adobe Campaign Web用户界面专门提供。

* 您现在可以使用 **Adobe Experience Manager Assets library** 与您的Experience Cloud资源放在一起，即使 **与Adobe Experience Cloud集成** 软件包安装在您的Adobe Campaign实例上。

* 不能再从客户端控制台创建运算符。 现在，您需要使用Admin Console。 [了解详情](../start/gs-permissions.md)。

* 已更新多个第三方工具以优化安全性。

### 可投放性更新 {#deliverability-8-6-1}

* 到 2024 年 2 月，任何通过 Google 或 Yahoo! 发送超过 5000 封电子邮件的公司将必须开始使用身份验证技术，即“基于域的邮件身份验证、报告和符合性”(DMARC)。确保为您在 Adobe Campaign 中使用的所有子域设置 DMARC 记录。[了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=zh-Hans){target="_blank"}

* 自 2024 年 6 月 1 日起，Google 和 Yahoo! 将要求发件人使用一键式 List-Unsubscribe 功能。Adobe Campaign 现在支持此选项。[了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=zh-Hans#one-click-list-unsubscribe){target="_blank"}


### 修复 {#fixes-8-6-1}

此版本修复了以下问题：
NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406、NEO-61580、NEO-61199、NEO-60786、NEO-59544、NEO-59198、NEO-59059、NEO-58637、NEO-55197、NEO-52542、NEO-50488、NEO-47789