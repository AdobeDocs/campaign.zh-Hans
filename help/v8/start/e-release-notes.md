---
title: Campaign v8早期发行说明
description: Campaign v8早期版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---

# 早期发行说明 {#e-new-release}

本页介绍下一个Campaign v8版本中包含的改进和修复。 在发行日期之前，此内容可能会发生更改，恕不另行通知。 此处提供了正式的发行说明 [页面](../start/release-notes.md).

## 8.3.9 版 {#release-8-3-9}

>[!CAUTION]
>
> 必须升级客户端控制台。 在此中了解如何升级您的客户端控制台 [页面](../start/connect.md#download-ac-console).

_2022年10月7日_

**改进**

* 修复了在启用FeatureFlag_GZIP_Compression选项时，影响MID实例上投放日志状态更新的问题。 (NEO-49183)
* 的 **数据库清理** 技术工作流现在还可处理自定义暂存模式。 (NEO-48974)
* 修复了可能导致投放保留在 **待定** 状态（即使达到联系日期）。 (NEO-48079、NEO-48251)
* 改进了在SOAP调用期间处理无效XML字符串时的稳定性。 (NEO-48027)
* 修复了在排除已的收件人步骤期间，当定向大量收件人时，列入阻止列表可能会减慢投放分析速度的问题。 (NEO-48019)
* 为了防止向种子地址发送校样时速度变慢，现在将种子成员的所有连续复制分组到一个复制请求中。 (NEO-44844)
* 修复了在使用外部投放模式发送短信消息时导致个性化问题的问题。 (NEO-46415)
* 修复了在尝试预览任何消息中心存档事件中的投放时显示错误的问题。 (NEO-43620)
* 修复了工作流中可能导致在使用 **数据加载（文件）** 活动。 该过程以100%的速度停止，但从未结束。 (NEO-47269)
* 修复了在投放使用日历和拆分模式时导致创建不必要的DeliveryParts的问题。 (NEO-48634)
* 修复了使用基于日历的批次时的性能问题。 (NEO-48451)
* 修复了在自定义架构上创建新目标映射后，可能导致投放列表屏幕中出现错误消息的问题。 (NEO-49237)
* 修复了在MTA过程中投放达到特定大小时可能发生的问题。 (NEO-46097)
* 修复了跟踪日志无法返回与收件人浏览器相关的数据的问题。 (NEO-46612)
* 修复了在日语环境升级后期出现的问题。 (NEO-46640)
* 修复了在使用 **查询** 活动和过滤表。 当列名称包含“Update”一词时，出现编译错误，标识符无效，并出现以下消息：“已更新的行数”。 (NEO-46485)
* 修复了阻止 **[!UICONTROL Replicate Staging data]** (fdaReplicateStagingData)技术工作流即使在执行过程中发生错误时也无法停止。 (NEO-46280)
* 修复了在暂存工作流出错且保留期完全过期时，可能导致数据丢失的问题。 (NEO-48975)
* 修复了使用Campaign将数据注入Snowflake云数据库时的问题 **查询** 活动和 **更改数据源** 活动：当数据中存在反斜线字符时，该过程会失败。 源字符串未转义，并且数据在Snowflake时未正确处理。 (NEO-45549)
