---
title: Campaign v8（控制台） 2023年发行说明
description: 2023 Campaign v8 版本的功能和改进列表
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: 69ef7e81d5fc0f5cf0dc74fa16d970ef89607331
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 77%

---

# 2024版发行说明 {#2024-rn}

此页面列出了&#x200B;**2024 Campaign v8版本**&#x200B;中的新功能、改进和修复。


## 版本 8.6.2 {#release-8-6-2}

_2024 年 2 月 23 日_

### 修复 {#fixes-8-6-2}

此版本修复了以下问题：

* 修复了中间源实例上可能出现的性能问题 (NEO-72595)。

## 版本 8.6.1 {#release-8-6-1}

_2024 年 2 月 14 日_

### 新增功能 {#new-8-6-1}

* 从此版本开始，您可以访问新的 **Campaign Web 用户界面**，该界面可通过中央 Adobe Experience Cloud 环境使用。Experience Cloud 是 Adobe 的数字营销应用程序、产品和服务的集成系列。通过其直观的界面，您可以快速访问云应用程序、产品功能和服务。[在此页面中](campaign-ui.md#ac-web-ui)了解如何连接到 Adobe Experience Cloud 并访问 Adobe Campaign Web 界面。


* Adobe Campaign v8 现已集成 **Adobe Experience Manager as a Cloud Service**，仅通过 Adobe Campaign Web 用户界面提供创作功能。[了解详情](../connect/ac-aem.md)

* 现在，如何在 Adobe Campaign 实例上安装了与 Adobe Experience Cloud 包的集成，您可以将 **Adobe Experience Manager Assets 库**&#x200B;与 Experience Cloud Assets 一起使用。[了解详情](../connect/ac-aem.md#assets-library)

### 一般改进 {#improvements-8-6-1}

* Campaign v8.6 提高了&#x200B;**电子邮件投放跟踪指标的吞吐量**。通过我们优化的流程，可以减少跟踪收录和计算时间，并且可以更快地检查投放关键指标。


### 可投放性更新 {#deliverability-8-6-1}

* 到 2024 年 2 月，任何通过 Google 或 Yahoo! 发送超过 5000 封电子邮件的公司将必须开始使用身份验证技术，即“基于域的邮件身份验证、报告和符合性”(DMARC)。确保为您在 Adobe Campaign 中使用的所有子域设置 DMARC 记录。[了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=zh-Hans){target="_blank"}

* 自 2024 年 6 月 1 日起，Google 和 Yahoo! 将要求发件人使用一键式 List-Unsubscribe 功能。Adobe Campaign 现在支持此选项。[了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=zh-Hans#one-click-list-unsubscribe){target="_blank"}


### 修复 {#fixes-8-6-1}

此版本中修复了以下问题：

NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455、NEO-62406、NEO-61580 -61199， NEO-60786， NEO-59544， NEO-59198， NEO-59059， NEO-58637 55197 52542 50488 47789
