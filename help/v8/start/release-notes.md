---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 34%

---

# 最新版本{#latest-release}

此页面列出了&#x200B;**最新 Campaign v8 版本**&#x200B;中的新功能、改进和修复。

## 8.4.3 版 {#release-8-4-3}

>[!CAUTION]
>
> 必须升级客户端控制台。在[此页面](../start/connect.md#download-ac-console)中了解如何升级您的客户端控制台。

_2023年1月27日_

**改进**

* 修复了营销服务器与中间源服务器之间的传递指示器同步问题。 (NEO-50724) <!--OKKKK-->
* 修复了导出工作流时可能导致错误的问题。 (NEO-50555) <!--OKKKK-->
* 修复了扩展之前扩展的架构时的问题。 (NEO-49118) <!--OKKKK-->
* 修复了在链接定义中使用具有相同标识符的两个扩充活动时的问题。 (NEO-48851)
* 修复了两个投放准备失败问题。 如果处理的潜在选件数量过高，投放准备可能会失败。 第二个问题是，将图像URL定义为要在文本格式投放中跟踪的URL。 (NEO-48807) <!--OKKKK-->
* 修复了可能导致工作流失败的问题，该问题导致工作流将覆盖在非FFDA帐户的外部帐户中定义的仓库名称。 (NEO-43209) <!--OKKKK-->
* 改进了Web应用程序的安全性，以防止DDoS攻击。 (NEO-50757) <!--OKKKK-->
* 改进了 **[!UICONTROL Consolidated tracking]** (nms:trackingStats)FDA表以避免重复。 (NEO-46409)
* 修复了使用 `enableIf` 在逻辑运算符条件中。 以前的逻辑条件被覆盖。 (NEO-45815)  <!--OKKKK-->
* 付费工作流中优化了活动用户档案的生成，以提高性能。 (NEO-47658) <!--OKKKK-->
* 修复了当映像节点 (img) 包含具有个性化字段的 URL 时，HTML 文件导入的问题。(NEO-48396)
* 修复了在 **拆分** 工作流活动。 (NEO-45899) <!--OKKKK-->
* 修复了对 nmsDeliveryMapping 文件夹具有读取访问权限的用户尝试运行活动或工作流时会导致错误的问题。(NEO-48230)
* 修复了投放的 HTML 选项卡的性能问题，该问题可能会在大型 HTML 代码中出现。(NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* 修复了阻止用户使用 **合并所选行** 工作流选项。 (NEO-48488)
* 修复了SnowflakeFDA连接器在扩充期间使用“0或1基数简单连接”选项时导致记录丢失的问题。 (NEO-48737)
* 对 log4j 库的其余引用已从 Windows 上的 Campaign 安装中移除。(NEO-44851)
* 修复了在&#x200B;**查询**&#x200B;工作流活动的附加数据中添加&#x200B;**已打开的收件人** (estimatedRecipientOpen) 指标时，可能会导致错误的问题。(NEO-46665)
* 通过多次投放，工作流中的跟踪URL管理已得到改进，从而提高性能。 (NEO-50894) <!--OKKKK-->
* 修复了可能导致使用Xtkfolder的模式复制失败的问题。 (NEO-46787) <!--OKKKK-->
* 修复了可能导致在NmsSubscription表中删除“lastModified”自定义列的问题。 (NEO-48402)
