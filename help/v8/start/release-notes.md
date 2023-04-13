---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 44743e585119e8cd81a8fcc9b4d667c25c0d438e
workflow-type: ht
source-wordcount: '678'
ht-degree: 100%

---

# 最新版本{#latest-release}

此页面列出了&#x200B;**最新 Campaign v8 版本**&#x200B;中的新功能、改进和修复。

## 8.4.5 版 {#release-8-4-5}

_2023 年 4 月 3 日_

**修补程序**

* 修复了在将多个审批工作流程设置到同一计划时可能导致出现重复密钥约束错误的问题。(NEO-48968)
* 修复了 NEO-54474 (8.4.4) 引入的回归问题，该问题导致在数字内容编辑器 (DCE) 中上传图像时，“正文”标签的样式属性发生更改。(NEO-57697)
* 修复了当临时表具有定义为长整型而不是 uuid 的主键值时，使用 CRM 连接器导出数据会出现错误的问题。(NEO-54153)
* 修复了 8.4.1 中引入的回归问题，该问题可能导致打包导出、HTTP 联合数据访问和报告中出现错误。(NEO-57731)
* 修复了 8.3.8 中引入的回归问题，该问题可能导致无法正确为具有负 ID 的投放更新投放状态。(NEO-54675)
* 修复了使用 Big Query 连接器导入数据时布尔值字段的问题 (NEO-49181)

>[!CAUTION]
>
> 必须升级客户端控制台。在[此页面](../start/connect.md#upgrade-ac-console)中了解如何升级您的客户端控制台。

## 8.4.4 版 {#release-8-4-4}

_2023 年 3 月 8 日_

**安全性增强**

* 为了提高安全性，已将 Tomca 版本从 8.5.81 更新到 8.5.85。(NEO-50530)

**修补程序**

* 修复了可能导致无法在数字内容编辑器 (DCE) 的&#x200B;**编辑**&#x200B;选项卡中滚动的问题。(NEO-54474)
* 修复了复制期间可能导致 Web 服务器崩溃的问题。(NEO-53670)


>[!CAUTION]
>
> 必须升级客户端控制台。在[此页面](../start/connect.md#upgrade-ac-console)中了解如何升级您的客户端控制台。


## 8.4.3 版 {#release-8-4-3}


_2023 年 1 月 27 日_

**改进**

* 修复了营销服务器与中间源服务器之间的投放指标同步问题。 (NEO-50724) <!--OKKKK-->
* 修复了导出工作流时可能导致错误的问题。(NEO-50555) <!--OKKKK-->
* 修复了扩展之前已扩展的模式时出现的问题。(NEO-49118) <!--OKKKK-->
* 修复了在链接定义中使用具有相同标识符的两个扩充活动时出现的问题。(NEO-48851)
* 修复了两个投放准备失败的问题。如果处理的潜在优惠数量过多，投放准备可能会失败。将图像 URL 定义为要在文本格式投放中跟踪的 URL 时出现另一个问题。(NEO-48807) <!--OKKKK-->
* 修复了可能导致工作流失败的问题，即工作流会覆盖针对非 FFDA 帐户在外部帐户中定义的仓库名称。(NEO-43209) <!--OKKKK-->
* 改进了 Web 应用程序的安全性，从而防止 DDoS 攻击。(NEO-50757) <!--OKKKK-->
* 改进了 **[!UICONTROL Consolidated tracking]**(nms:trackingStats) FDA 表中整合跟踪数据的管理，从而避免出现重复。(NEO-46409)
* 修复了在逻辑运算符条件中使用 `enableIf` 时工作流查询中出现的逻辑运算符问题。以前的逻辑条件被覆盖。(NEO-45815)  <!--OKKKK-->
* 优化了计费工作流中活动用户档案的生成，从而提高性能。(NEO-47658) <!--OKKKK-->
* 修复了当映像节点 (img) 包含具有个性化字段的 URL 时，HTML 文件导入的问题。(NEO-48396)
* 修复了在&#x200B;**拆分**&#x200B;工作流活动中使用排序参数时出现的 Snowflake（所有部署）问题。(NEO-45899) <!--OKKKK-->
* 修复了对 nmsDeliveryMapping 文件夹具有读取访问权限的用户尝试运行活动或工作流时会导致错误的问题。(NEO-48230)
* 修复了投放的 HTML 选项卡的性能问题，该问题可能会在大型 HTML 代码中出现。(NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* 修复了会导致用户无法使用&#x200B;**合并所选行**&#x200B;工作流选项的问题。(NEO-48488)
* 修复了 Snowflake FDA 连接器存在的问题，该问题会导致在扩充期间使用“0 或 1 基数简单联接”选项时删除记录。(NEO-48737)
* 对 log4j 库的其余引用已从 Windows 上的 Campaign 安装中移除。(NEO-44851)
* 修复了在&#x200B;**查询**&#x200B;工作流活动的附加数据中添加&#x200B;**已打开的收件人** (estimatedRecipientOpen) 指标时，可能会导致错误的问题。(NEO-46665)
* 改进了包含多个投放的工作流中的跟踪 URL 管理，从而提高性能。(NEO-50894) <!--OKKKK-->
* 修复了可能导致使用 Xtkfolder 的模式复制失败的问题。(NEO-46787) <!--OKKKK-->
* 修复了可能导致在 NmsSubscription 表中删除“lastModified”自定义列的问题。(NEO-48402)


>[!CAUTION]
>
> 必须升级客户端控制台。在[此页面](../start/connect.md#upgrade-ac-console)中了解如何升级您的客户端控制台。
