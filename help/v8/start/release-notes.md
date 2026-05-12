---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
TQID: https://experienceleague.adobe.com/Zdo52RLQFbxlRNgE54yLDn3yAMmmOqxKyRhnCJa0Xwg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ffeb9430b382b598af412555b1b0a6ff42bc68d0
workflow-type: tm+mt
source-wordcount: 1747
ht-degree: 6%

---

# 最新版本 {#latest-release}

此页面列出了 Campaign v8（控制台）**最新版本**&#x200B;中的新增功能、改进和修复。 要详细了解 Campaign 版本和升级，请参阅[此页面](upgrades.md)。 其他版本列于本文档的先前版本部分。

## 8.9.2版 {#release-8-9-2}

>[!CAUTION]
>
> 必须升级客户端控制台。 在[此页面](../start/connect.md#upgrade-ac-console)中了解如何升级您的客户端控制台。

_2026年5月3日_

### 安全性改进 {#security-8-9-2}

* 为了保持最佳的安全性、稳定性和合规性，所有实例都已升级到Debian 13和PostgreSQL 17。

### 修复 {#fixes-8-9-2}

>[!NOTE]
>
> 下面列出的修复程序已在后续的8.9.2内部版本中逐步推出。 导航到&#x200B;**[!UICONTROL Help > About...]** [菜单](upgrades.md#version)以检查您是否拥有最新的8.9.2 (11d1c68)内部版本。 有关更多信息，请与Adobe代表联系。

* 修复了由于数据类型转换问题而导致事务性事件中的事件日期设置不正确，从而导致动态报告中的日期不正确的问题。 (NEO-93923)
* 修复了标题和正文字段为空时，Android和iOS静默推送通知在投放准备期间失败的问题。 (NEO-93739)
* 修复了由于协调密钥不正确而导致无法为Android应用程序注册令牌捕获语言字段的问题。 (NEO-93100)
* 修复了在使用压力规则应用自定义分类规则时投放准备失败的问题。 (NEO-94457)
* 修复了客户端控制台可能遇到HTTP请求处理失败的问题。 (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* 默认情况下，现在禁用FDA监控，以防止连接日志插入错误。 (NEO-94841)
* 修复了用于优惠兑换的交互SOAP调用可能失败，并出现命名空间解析错误的问题。 (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* 修复了长度为1的字符串字段可能导致PostgreSQL 17上的工作流临时表出现SQL错误的问题。 (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* 修复了客户端控制台和Web UI中的&#x200B;**显示镜像页面**&#x200B;选项可能返回“错误镜像页面”错误的问题。 (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* 修复了在FFDA部署中安装多变量包后，现成&#x200B;**跟踪**&#x200B;技术工作流可能失败的问题。 (NEO-94972)
* 修复了投放准备在投放模板使用引用当前投放的权重公式时无法向目标添加任何收件人的问题。 (NEO-94892)
<!-- hotfix -->
* 修复了在升级后，使用两个连续1-N链接中的连接进行工作流增强可能会失败并出现SQL错误的问题。 (NEO-94893)

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* 修复了电子邮件管道中可能导致随时间推移过度内存消耗的问题。 (NEO-95088)
* 修复了在使用种子或验证地址时，冲突的电子邮件类型规则可能错误地从投放目标中排除非重复收件人的问题。 (NEO-95026)
* 修复了在升级后，现成的&#x200B;**优惠通知**&#x200B;技术工作流可能失败的问题。 (NEO-95064)
* 多变量包安装过程已得到改进，以防止在版本升级期间跟踪工作流失败。 (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* 修复了可能导致服务器反复崩溃并导致实例中断的问题。 (NEO-95304)
* 修复了跟踪和镜像页面链接可能无法加载投放的问题。 (NEO-95239)
* 修复了在登录到受IMS单点登录保护的Campaign Web应用程序时可能导致重定向循环的问题。 (NEO-95188)
* 修复了在保存投放后，投放提取文件中缺少投放创建日期的问题。 (NEO-95010)
* 修复了批量生成的子工作流可能停留在&#x200B;**正在编辑**&#x200B;状态，从而减少事务性工作流容量的问题。 (NEO-95131)
* 修复了&#x200B;**读取列表**&#x200B;活动可能会使用工作流生成的列表结构覆盖预定义列表模板，从而导致下游工作流失败的问题。 (NEO-95103)
* 修复了推送通知反馈处理可能会导致服务器在处理大量投放时崩溃的问题。 (NEO-95150)
* 修复了在架构资源管理器中打开`xtk:workflow`架构上的&#x200B;**Data**&#x200B;选项卡可能会触发错误消息的问题。 (NEO-94923)
<!-- hotfixes -->
* 修复了&#x200B;**扩充**&#x200B;活动无法再从上游&#x200B;**子工作流**&#x200B;活动中检索输出属性，从而导致工作流失败的问题。 (NEO-95151)
* 修复了跟踪数据摄取问题，该问题可能会阻止投放状态更新并阻止下游消息处理。 (NEO-94666)
* 修复了与优惠建议相关的某些客户端控制台操作可能触发对Snowflake数据库的长时间运行查询，从而导致锁定和速度缓慢的问题。 (NEO-92936)
* 修复了无法在Snowflake外部帐户上配置用于存储加密密钥的自定义选项的问题。 (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

## 8.9.1版 {#release-8-9-1}

_2026 年 1 月 27 日_

>[!CAUTION]
>
> 必须升级客户端控制台。 在[此页面](../start/connect.md#upgrade-ac-console)中了解如何升级您的客户端控制台。

### 新增功能 {#new-8-9-1}

**新SMS发送连接器**&#x200B;现在可供所有客户使用(GA)。 请参阅[详细文档](../send/sms/sms.md)。

此版本附带了一组可在Campaign Web用户界面中使用的功能：

* [多语言投放功能（GA）](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [事务性消息中的用户档案扩充(GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Adobe Experience Manager实时副本和语言副本](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [内容实验 — A/B测试](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [持续传递活动](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [营销活动审批管理](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

请参阅Campaign Web UI [发行说明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hans){target="_blank"}

### 安全性改进 {#security-8-9-1}

* Snowflake外部帐户现在支持OAuth2身份验证，为联合数据访问连接提供现代且安全的身份验证方法。 (NEO-87013) [了解更多](../config/external-accounts.md#snowflake-external-accounts)
* Databricks外部帐户现在支持通过服务主体（非交互式客户端凭据流）进行OAuth2身份验证，为联合数据访问连接提供安全的身份验证方法。 交互式OAuth2身份验证将在未来版本中提供。 (NEO-87422) [了解更多](../config/external-accounts.md#databricks-external-accounts)
* 通过限制对授权目录的操作、防止未经授权的访问和潜在的远程代码执行，修复了工作流文件访问漏洞。 (NEO-88460)
* 向工作流JavaScript代码活动添加了FTP URL列入允许列表控制，将出站FTP连接限制为仅访问授权的地址。 (NEO-89083)

### 其他变更 {#changes-8-9-1}

* 通过在高内存条件下实施自动工作流节流，以及针对非关键进程的智能工作流重新启动功能和内存护栏，改进了容器内存管理。 (NEO-89041)
* 在Campaign工作流中添加了对非对称加密和解密功能的支持。 (NEO-80257)
* 增强了FFDA部署中大型数据上传的复制代理性能和内存恢复能力。 (NEO-88430)
* **[!UICONTROL SQL code]**&#x200B;和&#x200B;**[!UICONTROL SQL Data Management]**&#x200B;工作流活动已得到改进，以更好地保护PostgreSQL数据库，并在从Campaign执行自定义SQL时保持工作流平稳运行。 有关更多信息和最佳实践，请参阅[SQL数据管理](../../automation/workflow/sql-data-management.md#important-notes)和[SQL代码](../../automation/workflow/sql-code-and-javascript-code.md#important-notes)。 (NEO-86540)


### 修复 {#fixes-8-9-1}

* 修复了在sysFilter更改后无法更新数据库结构的问题。 (NEO-93306)
* 修复了迁移后动态报表数据缺失的问题。 (NEO-92962)
* 修复了投放状态未正确更新的问题。 (NEO-92908)
* 修复了与数据库FDA使用目录限制相关的问题。 (NEO-92900)
* 修复了可能导致Outlook Windows桌面版中出现HTML布局错误的问题。 (NEO-92611)
* 修复了升级后在中间实例上复制投放主键的数据完整性问题。 (NEO-92424)
* 修复了在投放的“跟踪和图像”对话框中无法禁用链接的问题。 (NEO-92381)
* 修复了nms.subscription.RecipientSubscribe()函数不适用于批量订阅的问题。 (NEO-92308)
* 修复了在升级后由于缺少投放部分而导致投放失败的问题。 (NEO-92278)
* 修复了跟踪工作流中重复状态错误和SQL语法错误导致跟踪指标无法更新的问题。 (NEO-92239)
* 修复了在使用dbEnum字段时通过工作流创建的列表中缺少枚举字段标签或这些标签显示不正确的问题。 (NEO-91158)
* 修复了RT发布/取消发布对话框未关闭并冻结的问题。 (NEO-91038)
* 修复了收件人出现“Taken taken by the Service Provider”（服务提供商已考虑）状态的问题。 (NEO-90927)
* 修复了选择退出链接缺少（取消）订阅源的问题。 (NEO-90714)
* 修复了添加优惠券失败投放准备的问题。 (NEO-90547)
* 修复了“Audit”（审核）选项卡中未准确显示“Insert Reject Count”（插入拒绝计数）的问题。 (NEO-90318)
* 修复了可能导致应用程序拒绝服务的安全问题。 (NEO-89984)
* 修复了下载的热点击报表的PDF损坏的问题。 (NEO-89954)
* 解决了升级后发生的SSL错误，该错误会导致读取错误时出现意外EOF。 (NEO-89108)
* 修复了在升级后无法在数据架构中查询数据的问题。 (NEO-88663)
* 修复了在PostgreSQL 15中连接“char”字段时发生的错误。 (NEO-88028)
* 修复了在保存或复制模板时投放模板变量的顺序发生更改的问题。 (NEO-87845)
* 修复了创建新的数据库架构导致Web界面崩溃的问题。 (NEO-87816)
* 修复了重复数据删除活动中使用补充集的问题。 (NEO-87711)
* 修复了没有X11依赖关系的安装包请求。 (NEO-87471)
* 修复了无法在动态报告中使用区段代码的问题。 (NEO-87276)
* 修复了工作流在更新数据活动中卡住的问题。 (NEO-87252)
* 修复了BigQuery使用错误时区的问题。 (NEO-86622)
* 修复了在评估“mcSynch_mcExec1/jsReplicateUrl”脚本时发生的JavaScript错误。 (NEO-86553)
* 修复了由于标识符计算方法不正确而导致在eventHisto表中出现重复事件的问题。 (NEO-86544)
* 修复了复制时未为iOS推送显示高级选项卡的问题。 (NEO-86231)
* 修复了复制引用表工作流在复制nms:delivery架构时失败的问题。 (NEO-85884)
* 修复了在发送投放时，错误日志中显示与MXIP地址对应的Null域错误的问题。 (NEO-85238)
* 修复了在对选项进行更改后技术投放模板未刷新的问题。 (NEO-84149)
* 修复了现成计费工作流中的错误。 (NEO-83624)
* 修复了仅根据目标记录的主键排除重复项的问题。 (NEO-82910)
* 修复了Campaign Web UI报表中的差异，在这些报表中，跟踪统计信息显示的值与控制台的值不同。 (NEO-82339)
* 修复了即使不应在更新数据活动中更新记录，上次修改日期也发生更改的问题。 (NEO-82002)
* 修复了在列表中添加新属性导致工作流读取列表失败的问题。 (NEO-80258)
* 修复了跟踪指标报表对非重复打开显示不正确值的问题。 (NEO-79466)