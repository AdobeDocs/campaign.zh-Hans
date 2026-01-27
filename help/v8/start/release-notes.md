---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6693bb8a62c0d126b871dc24a75b76de71b86f8d
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 21%

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

* [多语言传递功能(GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [事务性消息中的用户档案扩充(GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Adobe Experience Manager实时副本和语言副本](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [内容实验 — A/B测试](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html)
* [持续传递活动](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html)
* [营销活动审批管理](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html)

请参阅Campaign Web UI [发行说明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hans){target="_blank"}

### 安全性改进 {#security-8-9-1}

* Snowflake外部帐户现在支持OAuth2身份验证，为联合数据访问连接提供现代且安全的身份验证方法。 (NEO-87013)
* 通过限制对授权目录的操作、防止未经授权的访问和潜在的远程代码执行，修复了工作流文件访问漏洞。 (NEO-88460)
* 向工作流JavaScript代码活动添加了FTP URL列入允许列表控制，将出站FTP连接限制为仅访问授权的地址。 (NEO-89083)

### 其他变更 {#changes-8-9-1}

* 通过在高内存条件下实施自动工作流节流，以及针对非关键进程的智能工作流重新启动功能和内存护栏，改进了容器内存管理。 (NEO-89041)
* 在Campaign工作流中添加了对非对称加密和解密功能的支持。 (NEO-80257)
* 增强了FFDA部署中大型数据上传的复制代理性能和内存恢复能力。 (NEO-88430)


### 修复 {#fixes-8-9-1}

* 修复了按某些列分组时，动态报告显示不正确计数的问题。 (NEO-86898)
* 解决了动态报表与实际促销活动数据之间的数据差异问题。 (NEO-88068)
* 修复了PostgreSQL“char”字段类型导致查询意外结果的连接问题。 (NEO-87769)
* 更正了JavaScript logInfo命令未正确处理某些参数的问题。 (NEO-88263)
* 解决了消息中心实时事件处理中的同步挂起问题。 (NEO-88330)
* 修复了可视编辑器自动重新格式化HTML内容，从而导致布局更改的问题。 (NEO-88409)
* 修复了重复数据删除活动无法正确处理临时架构的问题。 (NEO-88577)
* 修复了在发送校样时阻止生成种子地址的问题。 (NEO-88720)
* 通过优化分区列处理，改进了PostgreSQL查询性能。 (NEO-88771)
* 解决了文件传输活动无法正确处理行连续字符的问题。 (NEO-88812)
* 增强了PostgreSQL查询优化，可在大型数据集中提高性能。 (NEO-88885)
* 修复了阻止打开混合营销活动的“权限被拒绝”错误。 (NEO-88955)
* 扩展了对条形码功能的支持，可处理较长的文本字符串。 (NEO-88958)
* 更正了在将验证与定期投放结合使用时发生的活动日志错误。 (NEO-88976)
* 修复了在某些情况下影响电子邮件发送操作的问题。 (NEO-89019)
* 解决了工作流启动模式意外地从立即更改为正常的问题。 (NEO-89025)
* 修复了在特定条件下运行更新数据活动时发生的错误。 (NEO-89031)
* 更正了更新数据活动丢失自定义架构元数据的问题。 (NEO-89056)
* 修复了投放准备期间发生的验证错误。 (NEO-89063)
* 解决了查询包含1-1链接关系上的过滤器时的无效SQL生成问题。 (NEO-89065)
* 修复了增量查询活动未遵循配置的大小限制的问题。 (NEO-89066)
* 改进了FFDA部署中用于大规模操作的工作流性能。 (NEO-89098)
* 增强了工作流进程的内存管理和稳定性。 (NEO-89105)
* 为Web窗体启用了严格的列验证，以防止数据不一致。 (NEO-89111)
* 解决了导致处理延迟的消息中心同步问题。 (NEO-89138)
* 修复了“刷新可投放性”工作流中阻止正确执行的错误。 (NEO-89160)
* 更正了在工作流中执行JavaScript代码活动时发生的错误。 (NEO-89169)
* 已删除硬编码的Snowflake仓库配置，以允许进行适当的外部帐户设置。 (NEO-89201)
* 修复了在工作流文件传输操作期间发生的403禁止错误。 (NEO-89226)
* 优化了FFDA部署中收件人表的慢查询。 (NEO-89268)
* 修复了增量查询活动忽略已配置计划的问题。 (NEO-89317)
* 解决了在混合环境中打开营销活动时的访问错误。 (NEO-89320)
