---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 100%

---

# 最新版本{#latest-release}

此页面列出了&#x200B;**最新 Campaign v8 版本**&#x200B;中的新功能、改进和修复。

## 8.1.20 版 {#release-8-1-20}

_2021 年 9 月 7 日_

**安全性增强**

* 修复了一个安全问题，以加强针对目录穿越攻击的保护。(NEO-28547)

**改进**

* 在 Flash 生命周期结束后，已从所有相关的 Campaign 功能和组件中移除 Flash，并替换为 HTML5。**量规**&#x200B;类型的图表已被删除。(NEO-30330) [阅读更多](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=zh-Hans)
* 在 Windows 上安装客户端控制台时，安装程序现在会检查是否存在父注册表节点，如果缺少该节点，则会创建一个。这样可防止在启动控制台时出现潜在问题。(NEO-34854)
* 跟踪签名功能已得到改进，以防止与第三方工具（电子邮件客户端、互联网浏览器等）处理特殊字符的方式有关的错误。URL 参数现已进行编码。

**其他变更**

* 之前已弃用的 Microsoft CRM 连接器（Office 365 和内部部署）已从界面中移除。[阅读更多](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=zh-Hans#configure-acc-for-microsoft)
* 迁移到 Tomcat 8 后，已更新 IIS 设置脚本，以修复 IIS 集成问题。(NEO-31019)
* 新增了护栏，以仅允许[计费技术工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=zh-Hans#billing-report)在营销实例上运行。
* 在工作流过渡的 **View population** 窗口的 data 和 schema 选项卡中，数据源识别已得到改进。
* 缺少的数据库索引已添加至以下模式，以防止数据库更新问题：xtk:rights、nms:dlvExclusion、nms:seedMember、nms:trackingUrl

**修补程序**

* 修复了在将优惠链接到投放时，导致&#x200B;**热门点击**&#x200B;报表无法工作的问题。(NEO-26295)
* 修复了 **Sub-worklow** 活动在执行时未生成输出表的问题。(NEO-36242)
* 修复了将&#x200B;**描述性分析**&#x200B;报表导出为 PDF 时出现的各种问题。(NEO-25847)
* 修复了在使用外部邮件投放时可能导致投放失败的问题。(NEO-37435)
* 修复了使用 Web API 连接到 Microsoft CRM 时的错误。由于功能未受到影响，因此错误消息已被移除。
* 修复了将中间服务器设置为跟踪服务器和营销服务器之间的中继时出现的跟踪日志删除重复项问题。(NEO-36285)
* 修复了导致无法将 Vault 用作特定代码存储的回归问题。
* 修复了当传入的过渡来自 FDA 数据源时，导致无法在&#x200B;**扩充**&#x200B;工作流活动中使用变量的问题。
* 修复了 FFDA 中无法正确复制操作员组和权限的问题。
* 修复了可能导致通过投放发送错误的退订链接的问题。
* 修复了复制管理中影响升级后的持续时间的问题。
* 修复了可能阻止显示&#x200B;**单击热点**&#x200B;的问题。
* 修复了可能导致电子邮件中 URL 损坏的问题。

## 8.1.14 版 {#release-8-1-14}

_2021 年 7 月 23 日_

**新增功能**

<table>
<thead>
<tr>
<th><strong>全新工作流活动：更改数据源</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>全新的<b>更改数据源</b>工作流活动允许您更改工作流工作表的数据源。这提高了跨不同数据源（FDA、FFDA 和本地数据库）管理数据的灵活性。</p>
<p>在 Adobe Campaign 工作流中，使用工作（或临时）表管理数据。工作流执行时，工作表会在工作流活动之间共享数据。默认情况下，工作表会在与我们查询的数据源相同的数据库中创建。</p>
<p>使用 Campaign v8 时，主用户档案表直接存储在云数据库中。因此，查询用户档案表也会在云数据库上创建一个工作表。在某些情况下，有必要将工作表移动到其他数据源以执行特定操作。</p>
<p>有关详细信息，请参阅<a href="../config/workflows.md#change-data-source-activity">有详细说明的文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE 渠道可用性</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p><a href="../send/line.md">LINE 渠道</a>现在可在 Campaign v8 中使用，包括与<a href="../send/transactional.md">事务性消息传递</a>模块结合使用时的以下增强功能：
<ul> 
<li><p>修复了可能导致无法在 LINE 投放中定位访客的问题。 
</p></li>
<li><p>修复了在从执行实例提取访客到营销实例时可能导致错误的问题。
</p></li>
<li><p>修复了实时事件处理过程中的问题。</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**其他改进**

* 修复了可能导致无法针对特定投放显示&#x200B;**热门点击**&#x200B;报表的问题。
* 修复了&#x200B;**重复数据删除**&#x200B;工作流活动中可能导致重复计数不准确的问题。
* 修复了在使用具有“ID 不为空”筛选条件的工作流查询时，可能会导致在过渡群体中显示空项目的问题。
* 修复了导致无法在新目标映射中创建更多字段的问题。
