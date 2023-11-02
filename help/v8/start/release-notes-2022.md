---
title: Campaign v8 2022 发行说明
description: 2022 Campaign v8 版本的功能和改进列表
feature: Release Notes
role: User
level: Beginner
exl-id: 76473fa5-48ba-42cf-8664-0dd197833a86
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 94%

---

# 2022 发行说明{#2022-rn}

此页面列出了 **2022 Campaign v8 版本**&#x200B;中的新功能、改进和修复。

## 8.4.2 版 {#release-8-4-2}

_2022 年 10 月 28 日_

**改进**

* 修复了在使用 Adobe Campaign Enhanced MTA 时，无法正确更新投放指标的问题。(NEO-50462)

## 8.4.1 版 {#release-8-4-1}

_2022 年 9 月 30 日_

**新增功能**

<table> 
<thead>
<tr> 
<th> <strong>Adobe Campaign 与 Adobe Experience Platform 的集成</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>新的目标和源连接器现已可用，您可借助它们在 Adobe Campaign 和 Adobe Experience Platform 之间实现无缝集成：</p>
<ul><li>使用 Adobe Campaign Managed Cloud Service 目标连接器将 Experience Platform 区段发送到 Adobe Campaign 以进行激活，</li>
<li>使用 Adobe Campaign Managed Cloud Service 源连接器将 Adobe Campaign 投放和跟踪日志发送到 Adobe Experience Platform。</li>
</ul>
<p>有关更多信息，请参阅<a href="../connect/ac-aep.md">详细文档</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Twitter 渠道的可用性</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p><a href="../send/twitter.md">Twitter 社交渠道</a>现已可在 Campaign v8 中使用。您可以：</p>
<ul> 
<li><p>在 Twitter 上发送消息：您可以利用 Adobe Campaign 将消息直接发送到自己的 Twitter 帐户。您还可以向所有关注者发送私信。
</p></li>
<li><p>收集新联系人：Adobe Campaign 可自动收集用户档案数据，您可借此来开展定位营销活动，并实施跨渠道的营销策略。
</p></li>
</ul>
<p>在<a href="../connect/ac-tw.md">详细文档</a>中了解如何关联 Campaign 和 Twitter。</p>
<p>在<a href="../connect/ac-tw.md">此页面</a>中了解如何利用 Campaign 发送推文和私信。</p>
</td> 
</tr> 
</tbody> 
</table>

**安全性增强**

为优化安全性，已从 Campaign 生成的 URL 中删除安全令牌：

* 此更改仅适用于“获取 URL”。包括“发布 URL”在内的其他类型操作不会受到影响。
* 如您使用的是自定义代码，则不会再从“获取 URL”安全令牌参数中检索安全令牌。您必须使用以下 JSSP 代码生成新的安全令牌：

  ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

  您还可以使用“登录 API”来获取安全令牌。
* 会话令牌管理没有变化。

**改进**

* 在 Microsoft Internet Explorer 11 的生命周期终止后，控制台中的 HTML 渲染引擎现在使用的是 **Microsoft Edge Chromium**。此外，安装 **Microsoft Edge WebView 2** 现在，任何Client Console安装都需要运行时。
* 工作流的高可用性使工作流的执行得到改善，此提升可使您同时跨不同容器运行工作流，以防止工作流服务丢失，并避免发生与之相关的执行错误。**注意**：此新功能仅以“有限可用”的状态向特定客户群体发布。
* 现在可针对给定的隐私命名空间批量执行隐私请求。这项改进使 GDPR/隐私删除请求的执行时间有所增加。

**兼容性更新**

* Campaign v8 SDK 现在支持在 iOS 16 上使用“推送通知”。

请参阅 [Campaign 兼容性矩阵](compatibility-matrix.md)。

**修补程序**

* 修复了当 FeatureFlag_GZIP_Compression 选项启用时，MID 实例上的投放日志状态更新受到影响的问题。(NEO-49183)
* 修复了即使联系日期已到，仍可能导致投放停留在&#x200B;**待处理**&#x200B;状态的问题。(NEO-48079)
* 修复了工作流中存在的问题，此问题可能导致在使用&#x200B;**数据加载（文件）**&#x200B;活动时，文件无法在服务器上完成更新。该流程的进度停留在 100%，但无法结束。(NEO-47269)
* 修复了在日语环境中升级后出现的问题。(NEO-46640)
* 修复了在 MTA 进程中投放达到具体某个大小时可能会发生的问题。(NEO-46097)
* 修复了跟踪日志无法返回与收件人浏览器相关的数据的问题。 (NEO-46612)
* 修复了在使用外部投放模式发送短信时会导致出现个性化错误的问题。(NEO-46415)
* 修复了可能会在跟踪日志中生成重复项的问题。(NEO-46409)
* 修复了导致 **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) 技术工作流在执行过程中发生错误时也无法停止的问题。(NEO-46280)
* 为防止向种子地址发送验证时速度变慢，现在将种子成员的所有连续复制操作整合到一个复制请求中。(NEO-44844)
* 修复了尝试在任何消息中心存档事件中预览投放时显示错误的问题。(NEO-43620)
* 修复了使用 Campaign **查询**&#x200B;活动和&#x200B;**更改数据源**&#x200B;活动将数据注入 Snowflake 云数据库时的问题：当数据中存在反斜线字符时，该流程会失败。源字符串未转义，并且数据在 Snowflake 中未得到正确处理。(NEO-45549)
* 修复了在使用&#x200B;**查询**&#x200B;活动和筛选表格时出现的问题。当列名称包含“更新”一词时，出现标识符无效的编译错误，并显示以下消息：“行数已更新”。 (NEO-46485)
* 现在，**数据库清理**&#x200B;技术工作流还可处理自定义暂存模式。(NEO-48974)
* 修复了在排除已列入阻止列表的收件人步骤期间，当定位大量收件人时，可能会减慢投放分析速度的问题。(NEO-48019)
* 改进了在 SOAP 调用期间处理无效 XML 字符串时的稳定性。(NEO-48027)
* 修复了在投放使用日历和拆分模式时导致创建不必要的 DeliveryParts 的问题。(NEO-48634)
* 修复了使用基于日历的批次时的性能问题。(NEO-48451)
* 修复了在自定义模式上创建新目标映射后，可能导致投放列表屏幕中出现错误消息的问题。(NEO-49237)
* 修复了在暂存工作流出错且保留期完全过期时，可能导致数据丢失的问题。(NEO-48975)

## 8.3.9 版 {#release-8-3-9}

>[!CAUTION]
>
> 必须升级客户端控制台。在[此页面](../start/connect.md#download-ac-console)中了解如何升级您的客户端控制台。

_2022 年 10 月 7 日_

**改进**

* 修复了当 FeatureFlag_GZIP_Compression 选项启用时，MID 实例上的投放日志状态更新受到影响的问题。(NEO-49183)
* 现在，**数据库清理**&#x200B;技术工作流还可处理自定义暂存模式。(NEO-48974)
* 修复了即使联系日期已到，仍可能导致投放停留在&#x200B;**待处理**&#x200B;状态的问题。(NEO-48079、NEO-48251)
* 改进了在 SOAP 调用期间处理无效 XML 字符串时的稳定性。(NEO-48027)
* 修复了在排除已列入阻止列表的收件人步骤期间，当定位大量收件人时，可能会减慢投放分析速度的问题。(NEO-48019)
* 为防止向种子地址发送验证时速度变慢，现在将种子成员的所有连续复制操作整合到一个复制请求中。(NEO-44844)
* 修复了在使用外部投放模式发送短信时会导致出现个性化错误的问题。(NEO-46415)
* 修复了尝试在任何消息中心存档事件中预览投放时显示错误的问题。(NEO-43620)
* 修复了工作流中存在的问题，此问题可能导致在使用&#x200B;**数据加载（文件）**&#x200B;活动时，文件无法在服务器上完成更新。该流程的进度停留在 100%，但无法结束。(NEO-47269)
* 修复了在投放使用日历和拆分模式时导致创建不必要的 DeliveryParts 的问题。(NEO-48634)
* 修复了使用基于日历的批次时的性能问题。(NEO-48451)
* 修复了在自定义模式上创建新目标映射后，可能导致投放列表屏幕中出现错误消息的问题。(NEO-49237)
* 修复了在 MTA 进程中投放达到具体某个大小时可能会发生的问题。(NEO-46097)
* 修复了跟踪日志无法返回与收件人浏览器相关的数据的问题。 (NEO-46612)
* 修复了在日语环境中升级后出现的问题。(NEO-46640)
* 修复了在使用&#x200B;**查询**&#x200B;活动和筛选表格时出现的问题。当列名称包含“更新”一词时，出现标识符无效的编译错误，并显示以下消息：“行数已更新”。 (NEO-46485)
* 修复了导致 **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) 技术工作流在执行过程中发生错误时也无法停止的问题。(NEO-46280)
* 修复了在暂存工作流出错且保留期完全过期时，可能导致数据丢失的问题。(NEO-48975)
* 修复了使用 Campaign **查询**&#x200B;活动和&#x200B;**更改数据源**&#x200B;活动将数据注入 Snowflake 云数据库时的问题：当数据中存在反斜线字符时，该流程会失败。源字符串未转义，并且数据在 Snowflake 中未得到正确处理。(NEO-45549)

## 8.3.8 版 {#release-8-3-8}

_2022 年 5 月 18 日_

**新增功能**

<table> 
<thead>
<tr> 
<th> <strong>时效性通知</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>在 iOS 15 中，Apple 新增了“即时通知”的概念，当通知具有时效性并且需要实时联系用户时，该概念让应用程序开发人员可以控制对“专注”模式的绕过。</p>
<p>有关更多信息，请参阅<a href="../send/push.md#send-notifications-on-ios">详细文档</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Core Privacy Service 集成</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign v8 现在与 Adobe Privacy Core Service 集成。从 Privacy Core Service 推送到所有 Experience Cloud 解决方案的隐私请求由 Campaign 通过专用工作流自动处理。</p>
<p>有关更多信息，请参阅<a href="privacy.md">详细文档</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table>
<thead>
<tr>
<th><strong>响应管理器</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>通过 Campaign 的响应管理功能，您可以衡量营销活动的成功性和投资回报率，还可以衡量所有渠道中（电子邮件、移动设备、直邮等）的优惠建议。</p>
<p>有关更多信息，请参阅<a href="../start/campaigns.md#response-manager-add-on">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>分布式营销</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>借助 Campaign 的分布式营销营销，您可以在中央实体（总部、营销部门等）和本地实体（销售点、地区代理等）之间实施协作营销活动。通过共享工作区（营销活动包），您可以创建营销活动模板并将其推荐给本地实体。</p>
<p>有关更多信息，请参阅<a href="../start/campaigns.md#distributed-marketing-add-on">详细文档</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

**兼容性更新**

* Campaign v8 SDK 现在支持在 Android 12 和 iOS 15 上使用“推送通知”。
* Campaign v8 现在与 Windows 11 兼容。

请参阅 [Campaign 兼容性矩阵](compatibility-matrix.md)。

**改进**

* Campaign 现在支持适用于 POP3 的 Microsoft Exchange Online OAuth 2.0 身份验证。[了解更多信息](../config/external-accounts.md#bounce-mails-external-account)
* 已对 Microsoft Dynamics Connector Web API 应用了以下重要修复。
* 添加了新的运算符和组模式写入 (operatorWrite) 命名权限，以允许用户插入、更新和删除运算符 (xtk:operator) 和运算符组 (xtk:group) 模式。
  <!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
  <!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* 现在，可以在单个中间源上配置多个 LINE 活动帐户。
* Web 进程的默认连接数从 50 个增加到 150 个。
* Campaign 提供了一组新护栏，以防止在 Snowflake 数据库中插入重复的键。[了解更多信息](../architecture/keys.md)

**修补程序**

* 修复了在同一循环投放中使用种子和对照组时发生的问题。(NEO-41197)
* 修复了 FFDA 上的一个问题。当个性化块包含以下字符之一时，该问题会导致在执行发送进程（最多 256 个）期间属于同一个 deliveryPart 的对所有收件人的电子邮件发送被阻止：`' & < > "`。个性化块现在支持这些字符（例如：firstname=&quot;Brian O&#39;Neil&quot;）。(NEO-43184)
* 修复了在将自定义模式用作目标映射时可能导致跟踪工作流失败的问题。现在，在通过目标映射向导生成 broadLog 模式时，我们会确保指向自定义定位模式的外部链接类型正确无误。(NEO-43506)
* 修复了可能导致非英语语言的 FFDA 部署工作流失败的问题。(NEO-44561)

## 8.2.10 版 {#release-8-2-10}

_2022 年 2 月 2 日_

**修补程序**

* 修复了在达到类型规则中定义的最大消息数时，导致投放准备失败的问题。
* 修复了在配置 Adobe Analytics Connector 期间电子邮件地址包含“s”字符时的问题。
* 修复了升级后可能导致 deliveryMapping 表丢失自定义投放映射数据的问题。
* 修复了电子邮件地址包含单引号字符 (&#39;) 时，可能导致收件人多次收到相同邮件的问题。此字符现已转义。(NEO-41198)
* 修复了使用种子或替换地址发送校样时的 ID 生成问题。(NEO-42637)
* 修复了可能导致无法使用地址替换方法来发送校样的问题。(NEO-40417)
* 修复了导致无法安装 LINE 软件包的问题。(NEO-42503)
