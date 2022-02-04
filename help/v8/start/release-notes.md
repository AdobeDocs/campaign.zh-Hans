---
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: b7db9597aa6b4ca4fb2e1e13f8b7b718f4840031
workflow-type: tm+mt
source-wordcount: '1714'
ht-degree: 92%

---

# 最新版本{#latest-release}

此页面列出了&#x200B;**最新 Campaign v8 版本**&#x200B;中的新功能、改进和修复。

## 8.2.10 版 {#release-8-2-10}

_2022年2月2日_

**修补程序**

* 修复了在达到分类规则中定义的最大消息数时，导致投放准备失败的问题。
* 修复了配置Adobe Analytics连接器期间电子邮件地址包含“s”字符的问题。
* 修复了在升级后期可能导致deliveryMapping表丢失自定义投放映射中的数据的问题。
* 修复了当电子邮件地址包含单引号字符(&#39;)时，收件人可能会多次收到同一投放的同一消息的问题。 此字符现在已转义。 (NEO-41198)
* 修复了使用种子或替换地址发送校样时的ID生成问题。 (NEO-42637)
* 修复了可能阻止使用地址方法替换来发送校样的问题。 (NEO-40417)
* 修复了阻止安装LINE包的问题。 (NEO-42503)

## 8.2.8 版 {#release-8-2-8}

_2021 年 10 月 28 日_

<table>
<thead>
<tr>
<th><strong>入站互动</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>实时互动管理现适用于入站渠道。使用 Campaign 入站互动模块，在客户访问您的网站或联系您的呼叫中心时，向客户展示最佳优惠。这项功能是 Campaign v8 自带的一个选项，需要在您的实例上进行具体配置。请联系您的 Adobe 代表以获得入站互动模块的权限。</p>
<p>有关更多信息，请参阅<a href="../send/interaction-architecture.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>活动优化</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>活动优化模块现已可用。使用此模块，您可以控制、筛选和监测投放发送情况。为了避免活动之间发生冲突，Adobe Campaign 可以应用特定的限制规则来测试各种活动组合。这可确保所发送的邮件符合客户的需求与期望以及公司的通信政策。</p>
<p>有关更多信息，请参阅相关的 <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=zh-Hans">Campaign Classic v7 文档</a>。</p>
</td> 
</tr> 
</tbody> 
</table>
<table> 
<thead>
<tr> 
<th> <strong>Unicity Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service 是新的 Cloud Database Manager 组件。它可帮助用户维护和监测 Cloud Database 表内唯一键值约束的完整性。这样，您就可以降低插入重复键值的风险。
<p>由于 Cloud Database 不强制执行唯一性约束，因此 Unicity Service 在应用程序级别引入了<b>一套新护栏</b>，以减少使用 Adobe Campaign 管理数据时插入重复项的风险。</p> 
<p>Unicity Service 会启动一个名为 <b>ffdaUnicity</b> 的内置工作流程，以监测唯一性约束并在检测到重复项时发出警报。</p></td> </tr> 
</tbody> 
</table>

**改进**

* Snowflake 连接器在性能方面得到了改进。
* 为监测和测试目的，**[!UICONTROL Replicate Staging data]** 工作流的审核日志现在包括已发送到 FFDA（完全联合数据访问）数据库的记录数。
* 借助 SQL 代码活动，您现在可以选择将 SQL 脚本存储在哪个数据库中：默认数据源或选定的使用中的 FDA 外部帐户。
* 现在提供一组预定义的仓库，可用于并行运行各种查询，如分段、ETL 或峰值。[了解更多信息](../config/workflows.md)

**其他变更**

* **[!UICONTROL Encrypted identifier]** 字段已添加至访客模式 (`nms:visitor`)。会计算该字段并将其用于 Web 应用程序。
* 修复了当某些 IP 相关性存在于部分而非全部中间源容器时，导致投放分析失败的问题。现在，IP 相关性都存储在数据库中，因此任何容器都可以访问所有其他容器中存在的相关性。(NEO-37564)
* 您现在可以导入包含多个模式和导航树节点的包。

**修补程序**

* 当用户在数据模式中删除表定义元素的 `<autoStg>` 属性，或将其值从 `true` 更改为 `false` 后，并没有删除相关的暂存表。此问题已修复。
* 修复了使用专用表单创建记录时，由于使用 FFDA 数据源进行 ID 管理而导致错误的问题。
* 修复了当优惠由工作流中的扩充活动管理时，可能会导致无法将优惠插入投放的问题。
* 修复了可能会导致包导入速度降低的问题。
* 修复了可能导致无法使用种子地址发送电子邮件投放的问题。
* 修复了可能导致无法在优惠建议表中保存建议的问题。
* 修复了导致网络超时被错误记录为脚本中断而非网络错误的问题。在 JavaScript 活动中包含的 HTTP 请求中，会发生此问题。
* 修复了导致无法将优惠复制到 Snowflake 上的实时优惠环境的问题。
* 修复了未扩展内置模式的“autoStg”属性被忽略的问题。
* 修复了导致用户在预览用户档案时无法选择 **[!UICONTROL Country/Region]** 链接的问题。
* 修复了导致自定义报表中的日期选取器引发脚本错误的问题。(NEO-36345)
* 修复了在配置文件不正确的情况下重新生成配置时导致系统崩溃的问题。
* 修复了导致无法成功升级营销和控制实例的问题。
* 修复了可能导致营销实例上的计费工作流崩溃的问题。
* 修复了可能导致 FFDA Snowflake 现成表格中出现重复键值的问题。(NEO-38583)
* 修复了在连续编辑两个删除重复项活动时可能导致工作流临时模式丢失的问题。(NEO-34063)
* 修复了在尝试提取时间组件时，运行 Amazon Redshift HoursDiff 和 MinutesDiff 函数时返回错误结果的问题。(NEO-31673)
* 修复了由于代理配置问题而导致用户可能无法登录到控制台的问题。(NEO-38388)
* 修复了导致&#x200B;**清除文件夹**&#x200B;功能无法正常运行的问题。(NEO-37459)
* 修复了可能导致您无法预览附加到工作流的移动投放的问题。
* 修复了当数据库中的列表以负值 ID 标识时，可能会导致&#x200B;**读取列表**&#x200B;工作流活动无法运行的问题。(NEO-39607)

## 8.1.20 版 {#release-8-1-20}

_2021 年 9 月 7 日_

**安全性增强**

* 修复了一个安全问题，以加强针对目录穿越攻击的保护。(NEO-28547)

**改进**

* Flash 生命周期结束后，已从所有相关的 Campaign 功能和组件中删除，并替换为 HTML5。已删除&#x200B;**量规**&#x200B;类型的图表。(NEO-30330) [阅读更多](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=zh-Hans)
* 现在，在 Windows 上安装客户端控制台时，安装程序会检查是否存在父注册表节点，如果缺少该节点，则会创建一个。这可防止在启动控制台时出现潜在问题。(NEO-34854)
* 跟踪签名功能已得到改进，以防止与第三方工具（电子邮件客户端、互联网浏览器等）链接的方式出现错误处理特殊字符。URL 参数现已经过编码。

**其他变更**

* 之前弃用的 Microsoft CRM 连接器（Office 365 和内部部署）已从界面中删除。[阅读更多](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=zh-Hans#configure-acc-for-microsoft)
* 迁移到 Tomcat 8 后，更新了 IIS 设置脚本以修复 IIS 集成问题。(NEO-31019)
* 添加了护栏，以仅允许[计费技术工作流](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=zh-Hans#billing-report)在营销实例上运行。
* 在工作流过渡的 **View population** 窗口的“data”和“schema”选项卡中，数据源标识已得到改进。
* 以下架构中添加了缺少的数据库索引以防止出现数据库更新问题：xtk:rights、nms:dlvExclusion、nms:seedMember、nms:trackingUrl

**修补程序**

* 修复了在将优惠链接到投放时，导致&#x200B;**热门点击**&#x200B;报表无法工作的问题。(NEO-26295)
* 修复了&#x200B;**子工作流**&#x200B;活动在执行时未生成输出表的问题。(NEO-36242)
* 修复了将&#x200B;**描述性分析**&#x200B;报表导出为 PDF 时出现的各种问题。(NEO-25847)
* 修复了在使用外部邮件投放时可能导致投放失败的问题。(NEO-37435)
* 修复了使用 Web API 连接到 Microsoft CRM 时出现的错误。由于功能未受到影响，因此错误消息已删除。
* 修复了将中间服务器设置为跟踪服务器和营销服务器之间的中继时的跟踪日志重复数据删除问题。(NEO-36285)
* 修复了导致无法将保管库用作特定代码库的回归问题。
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
