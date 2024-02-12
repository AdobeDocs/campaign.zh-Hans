---
title: 早期 Campaign v8 发行说明
description: 早期 Campaign v8 版本
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 9fceeb04344f891fbfd8af1e643b2ad5331db158
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 21%

---

# 早期发行说明 {#e-new-release}

此页面介绍了下一个 Campaign v8 版本中包含的改进和修复。在发行之日前，此内容可能会有所变动，恕不另行通知。[此页面](../start/release-notes.md)中提供了正式的发行说明。

## 8.6.1版 {#release-8-6-1}

_2024年2月14日_


### 新增功能 {#new-8-6-1}

* 从此版本开始，您有权访问新的 **Campaign Web用户界面**，可通过中心的Adobe Experience Cloud环境使用。 Experience Cloud 是 Adobe 的数字营销应用程序、产品和服务的集成系列。通过其直观的界面，您可以快速访问云应用程序、产品功能和服务。了解如何连接到Adobe Experience Cloud并访问Adobe Campaign Web界面 [本页内容](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8现在集成了 **Adobe Experience Manager as a Cloud Service**，创作功能通过Adobe Campaign Web用户界面专门提供。

* 您现在可以使用 **Adobe Experience Manager Assets library** 与您的Experience Cloud资源放在一起，即使 **与Adobe Experience Cloud集成** 软件包安装在您的Adobe Campaign实例上。


### 一般改进 {#improvements-8-6-1}

* Campaign v8.6提高了以下各项的吞吐量 **电子邮件投放跟踪指标**. 通过我们优化的流程，可缩短跟踪摄取和计算时间，并且您可以更快地检查投放关键指标。


### 可投放性更新 {#deliverability-8-6-1}

* 到2024年2月，任何公司通过Google或Yahoo！ 必须开始使用一种称为基于域的消息身份验证报告和符合性(DMARC)的身份验证技术。 确保为您与Adobe Campaign一起使用的所有子域设置了DMARC记录。 [了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=zh-Hans){target="_blank"}

* 从2024年6月1日开始，Google和Yahoo！ 将要求发件人遵守一键式列表取消订阅。 Adobe Campaign现在支持此选项。 [了解详情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### 修复 {#fixes-8-6-1}

本发行版中修复了以下问题：NEO-67892、NEO-67235、NEO-66797、NEO-66462、NEO-65091、NEO-65036、NEO-64984、NEO-64680、NEO-63973、NEO-63879、NEO-63815、NEO-63657、NEO-63539、NEO-63387、NEO-63294、NEO-63174、NEO-62964、NEO-62750、NEO-62686、NEO-62455， NEO-62406， NEO-61580， NEO-61199， NEO-60786， NEO-59544， NEO-59198， NEO-59059 58637 55197 52542 50488 47789