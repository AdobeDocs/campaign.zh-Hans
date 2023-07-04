---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 441310dc1cdcb96296c0cbe5bf3fb7cd1502709f
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 57%

---

# 最新版本{#latest-release}

Adobe Campaign 会定期更新。这种定期更新旨在让您掌握最新、最充分的信息，保持环境的安全，并改进您对我们产品的体验。Adobe强烈建议所有客户升级到最新版本。

作为托管云服务用户，您的实例会由 Adobe 通过每个新版本升级。Adobe将与您联系并升级您的环境。 Campaign客户端控制台 **必须升级到相同版本** 作为Campaign服务器。 在[此页面](../start/connect.md#upgrade-ac-console)中了解如何升级您的客户端控制台。

此外，作为客户，请确保您使用的是 [兼容性矩阵](compatibility-matrix.md).

## 8.5 版 {#release-8-5}

_2023年6月30日_

**新增功能**

<table> 
<thead>
<tr> 
<th> <strong>增强的推送通知服务</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign v8.5正在推出我们最新的推送通知服务，该服务基于现代尖端技术构建的强大框架提供支持。 此服务旨在解锁更高级别的可扩展性，确保您的通知能够以无缝的效率接触到更多受众。 通过我们增强的基础架构和优化的流程，您可以期待更高的规模和可靠性，使您能够以前所未有的方式吸引移动应用程序用户并与之建立联系。 此功能仅适用于选定的客户组（限量发布）。</p>
<p>有关更多信息，请参阅<a href="../send/push-data-collection.md">详细文档</a>。</p>

</td> 
</tr> 
</tbody> 
</table>

**兼容性更新**

* 现已弃用32位版本的客户端控制台。 从 8.6 开始，将仅支持 64 位客户端控制台。客户端控制台可无缝升级到64位版本。 有关如何升级操作系统的详细信息，请参阅此[技术说明](../../technotes/upgrades/console.md)。
* 您现在可以将Campaign v8实例连接到Azure synapse外部数据库。 此连接通过新的外部帐户管理。了解详情，请参阅 [Campaign兼容性矩阵](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda).

**改进**

* 通过实施一系列优化，短信吞吐量得到了显着提升，从而提升了短信通信的速度和效率。
* 您现在可以利用Adobe Experience Platform目标连接来同步配置文件属性，例如Adobe Experience Platform和Campaign v8数据库之间的选择退出数据。
* 投放准备已优化。
* 除了现有的用户/密码身份验证方法之外，还为SFTP外部帐户添加了一个新的基于密钥的身份验证选项。 用户现在可以使用私钥安全地进行身份验证，从而增强安全性并为SFTP访问提供替代身份验证机制。 在[此章节](../config/external-accounts.md)中了解更多信息。

**安全性增强**

* 从Campaign v8.5开始，改进了Campaign v8的身份验证过程。 技术操作员必须使用AdobeIdentity Management System (IMS)连接到Campaign。 了解如何在中迁移现有技术帐户 [此技术说明](../../technotes/upgrades/ims-migration.md).
* 您无法再从Campaign客户端控制台创建运算符。 相应更新了用户界面。 您现在必须使用Adobe Admin Console。 [了解详情](../start/gs-permissions.md)。
* 更新了多个第三方工具以优化安全性。

**修补程序**

* 修复了可能导致投放的HTML内容中的特殊字符在若干浏览器中编码不正确的问题。 (NEO-60081)
* 修复了可能导致无法在Campaign v8企业(FFDA)部署中保存报表的问题。 (NEO-56836)
* 修复了通过更新数据工作流活动将数据插入或更新到自定义FFDA架构中时发生的问题。 (NEO-54708)
* 修复了阻止数据库清理工作流删除FFDA上nms：address表中的地址的问题。 (NEO-54460)
* 修复了计费工作流可能因“编译内存耗尽”错误而失败的问题。 (NEO-51137)
* 修复了可能阻止GPG解密在数据加载（文件）工作流活动中正常工作的问题。 (NEO-50257)
* 修复了会导致 `JSPContext.sqlExecWithOneParam` 功能无法正常运行的问题。(NEO-50066)
* 修复了在个性化字段中使用不可打印字符时导致投放失败的问题。 (NEO-48588)
* 修复了在插入Adobe Target动态图像时可能导致投放错误的问题。 (NEO-62689)
* 修复了在投放中使用条件内容时阻止浏览器添加额外空格的问题。 (NEO-62132)
* 修复了在电子邮件内容编辑器中单击图像时导致弹出窗口打开的问题。 (NEO-60752)
* 修复了在编辑投放内容时可能导致错误并阻止滚动的问题。 (NEO-61364)
* Adobe Analytics connector现在会导出具有正确渠道类型的量度。 以前，它始终设置为“电子邮件”渠道。 (NEO-26340)


## 8.4.5 版 {#release-8-4-5}

_2023 年 4 月 3 日_

**修补程序**

* 修复了在将多个审批工作流程设置到同一计划时可能导致出现重复密钥约束错误的问题。(NEO-48968)
* 修复了 NEO-54474 (8.4.4) 引入的回归问题，该问题导致在数字内容编辑器 (DCE) 中上传图像时，“正文”标签的样式属性发生更改。(NEO-57697)
* 修复了当临时表具有定义为长整型而不是 uuid 的主键值时，使用 CRM 连接器导出数据会出现错误的问题。(NEO-54153)
* 修复了 8.4.1 中引入的回归问题，该问题可能导致打包导出、HTTP 联合数据访问和报告中出现错误。(NEO-57731)
* 修复了 8.3.8 中引入的回归问题，该问题可能导致无法正确为具有负 ID 的投放更新投放状态。(NEO-54675)
* 修复了使用 Big Query 连接器导入数据时布尔值字段的问题 (NEO-49181)


## 8.4.4 版 {#release-8-4-4}

_2023 年 3 月 8 日_

**安全性增强**

* 为了提高安全性，已将 Tomca 版本从 8.5.81 更新到 8.5.85。(NEO-50530)

**修补程序**

* 修复了可能导致无法在数字内容编辑器 (DCE) 的&#x200B;**编辑**&#x200B;选项卡中滚动的问题。(NEO-54474)
* 修复了复制期间可能导致 Web 服务器崩溃的问题。(NEO-53670)


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


