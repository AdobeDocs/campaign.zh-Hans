---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 91796cd0d107b65377e8d724a81d1de4f907f7e5
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 18%

---

# 最新版本 {#latest-release}

此页面列出了 Campaign v8（控制台）**最新版本**&#x200B;中的新增功能、改进和修复。要详细了解 Campaign 版本和升级，请参阅[此页面](upgrades.md)。其他版本列于本文档的先前版本部分。

## 版本 8.9.1 {#release-8-9-1}

_2026 年 1 月 27 日_

>[!CAUTION]
>
> 必须升级客户端控制台。在[此页面](../start/connect.md#upgrade-ac-console)中了解如何升级您的客户端控制台。

### 新增功能 {#new-8-9-1}

**新SMS发送连接器**&#x200B;现在可供所有客户使用(GA)。 请参阅[详细文档](../send/sms/sms.md)。

此版本附带了一组可在Campaign Web用户界面中使用的功能：

* [多语言传递功能(GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=zh-Hans){target="_blank"}
* [事务性消息中的用户档案扩充(GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=zh-Hans){target="_blank"}
* [Adobe Experience Manager实时副本和语言副本](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=zh-Hans){target="_blank"}
* [内容实验 — A/B测试](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=zh-Hans){target="_blank"}
* [持续传递活动](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=zh-Hans){target="_blank"}
* [营销活动审批管理](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=zh-Hans){target="_blank"}

请参阅Campaign Web UI [发行说明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hans){target="_blank"}

### 安全性改进 {#security-8-9-1}

* Snowflake外部帐户现在支持OAuth2身份验证，为联合数据访问连接提供现代且安全的身份验证方法。 (NEO-87013)
* Databricks外部帐户现在支持通过服务主体（非交互式客户端凭据流）进行OAuth2身份验证，为联合数据访问连接提供安全的身份验证方法。 交互式OAuth2身份验证将在未来版本中提供。 (NEO-87422) [阅读更多](../config/external-accounts.md#databricks-external-accounts)
* 通过限制对授权目录的操作、防止未经授权的访问和潜在的远程代码执行，修复了工作流文件访问漏洞。 (NEO-88460)
* 向工作流JavaScript代码活动添加了FTP URL列入允许列表控制，将出站FTP连接限制为仅访问授权的地址。 (NEO-89083)

### 其他变更 {#changes-8-9-1}

* 通过在高内存条件下实施自动工作流节流，以及针对非关键进程的智能工作流重新启动功能和内存护栏，改进了容器内存管理。 (NEO-89041)
* 在Campaign工作流中添加了对非对称加密和解密功能的支持。 (NEO-80257)
* 增强了FFDA部署中大型数据上传的复制代理性能和内存恢复能力。 (NEO-88430)


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