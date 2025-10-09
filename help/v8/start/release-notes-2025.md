---
title: Campaign v8（控制台）2025 发行说明
description: 2025 Campaign v8版本的功能和改进列表
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 3bc247ba81de3de56c26bdf8fa9b8aa5ea91fb2a
workflow-type: tm+mt
source-wordcount: '3051'
ht-degree: 36%

---

# 2025 年发行说明 {#2025-rn}

此页面列出了 **2025 Campaign v8 版本**&#x200B;中的新增功能、改进和修复。有关最新版本，请参阅[此页面](release-notes.md)。

对于任何新实施或升级到现有环境，请安装[最新版本](release-notes.md)。

>[!BEGINSHADEBOX]

**本页面内容**

* [版本 8.6.5](#release-8-6-5)
* [版本 8.6.4](#release-8-6-4)
* [版本 8.7.4](#release-8-7-4)
* [版本 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## 版本 8.8.1 {#release-8-8-1}

_2025年7月9日_

### 新增功能 {#features-8-8-1}

以前为少数客户发布的以下功能现在可用于所有Campaign FDA环境：

* **新SMS发送连接器** - SMS发送连接器已进行现代化和改进，以启用收发器模式SMPP连接、启用永久性SMPP连接并确保更好的兼容性。 新的短信外部帐户现在可用于所有新的短信实施。现有实施仍受支持，但建议迁移到此新的现代化扩展连接器。[了解更多信息](../send/sms/sms.md)

  >[!NOTE]
  >
  >此功能&#x200B;**不**&#x200B;可用于[Campaign FFDA部署](../architecture/enterprise-deployment.md)。

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html?lang=zh-Hans)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html?lang=zh-Hans){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html?lang=zh-Hans){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html?lang=zh-Hans#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=zh-Hans#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=zh-Hans#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=zh-Hans#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html?lang=zh-Hans){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html?lang=zh-Hans#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=zh-Hans#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

以前以Limited Availability发布，现在以下功能可按需使用&#x200B;**&#x200B;**：

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=zh-Hans){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/zh-hans/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **Rest API** — 您现在可以使用Rest API为Adobe Campaign创建集成，并通过将Adobe Campaign与您使用的技术面板连接来构建您自己的生态系统。 事务性消息传递REST API也可用于SMS渠道。 当负载中同时存在电子邮件和移动电话时，您可以使用“wishedChannel”字段来指定渠道。如果未提供，则默认使用电子邮件，除非 wishedChannel 明确请求 SMS。基于事件的事务型API也可用于电子邮件。 [了解更多信息](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >此功能&#x200B;**不**&#x200B;可用于[Campaign FFDA部署](../architecture/enterprise-deployment.md)。

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/zh-hans/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/zh-hans/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

除了上述功能外，此版本还附带了一组可在Campaign Web用户界面中使用的功能：

* [创建多语言投放](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html?lang=zh-Hans#multilingual-delivery){target="_blank"}
* [投放警报](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html?lang=zh-Hans){target="_blank"}
* [登陆页面改进](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html?lang=zh-Hans){target="_blank"}
* [动态报告](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=zh-Hans){target="_blank"}（按需）
* [集中品牌](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=zh-Hans){target="_blank"}（按需，新实施）

请参阅Campaign Web UI [发行说明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hans){target="_blank"}

### 一般改进 {#improvements-8-8-1}

* Microsoft结构现在支持作为具有Adobe Campaign联合数据访问(FDA)的外部数据库。 [了解更多信息](../config/external-accounts.md#transfer-data-external-accounts)
* 现在，Campaign v8支持在Android 15和iOS 18上使用“推送通知”。 [了解更多信息](../start/compatibility-matrix.md#MobileSDK)
* 除了用于安全虚拟专用网络隧道的内部部署数据库外，现在还支持云数据库。 [了解更多信息](../config/enhanced-security.md#vpn-databases)
* 在SMS 2.0连接器的“传入流量”部分中添加了一组新的“提供程序ID”字段。 [了解更多信息](../send/sms/smpp-external-account.md#incoming-traffic)
* 通过“mailto”List-Unsubscribe方法取消订阅的收件人不再被隔离。 列入阻止列表它们或者取消订阅与投放关联的服务，或者发送到（用户档案的“不再联系”部分）（如果未定义投放服务）。 [了解更多信息](../send/quarantines.md)
* Adobe Campaign客户端控制台中现在提供了收件箱呈现报告的修订版本。
* 已将`setup-client.exe`文件替换为`ac-client.msi`文件，为管理员提供了无需用户干预即可执行批量升级的更简单方法。

### 修复 {#fixes-8-8-1}

* 修复了由于SMS 2.0中的有效期无效而未收到自动回复的问题。这可确保在迁移后正确传递消息。 (NEO-88088)
* 解决了SMS 2.0中`inSms`表中的某些字段未正确更新的问题，从而确保SMS功能的数据插入准确无误。 (NEO-87906)
<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
* Provided a silent installation mechanism for the client console to facilitate mass upgrades without user intervention. This resolves challenges with manual installations. (NEO-69772)
-->
* 修复了由于SQL查询中缺少列引用或不正确而导致数据库清理工作流失败的问题。 这可确保正确清除日志和访客数据。 (NEO-86813)
* 解决了投放日志中缺少事件日期的问题。 此修复确保事件日期填充的准确性，这对于计划的触发器和工作流至关重要。 (NEO-86708)
* 修复了SMS 2.0中的SMS投放日志插入问题，从而确保`nmsBroadLogMid`表中的正确日志记录。 (NEO-86556)
* 解决了直邮模板中外部投放模式的文件提取问题，确保兼容性和功能。 (NEO-86520)
* 解决了涉及跨多个MID实例拆分路由的投放处理问题，确保准确的投放状态更新和吞吐量。 (NEO-86500)
* 修复了从Campaign Standard迁移到Campaign v8后动态报告中缺少跟踪数据的问题，确保准确报告投放跟踪日志。 (NEO-86419)
* 解决了触发工作流执行两次导致重复键违规问题的工作流。 此修复确保正确处理和执行事件。 (NEO-86154)
* 修复了Redshift OOTB SQL函数部署后的兼容性问题，确保在工作流中正确执行诸如`GetDate()`之类的函数。 (NEO-85834)
* 解决了附加URL后图像消失的电子邮件构建中的渲染问题。 此修复可确保在收件箱预览中正确显示图像。 (NEO-85716)
* 更正了WebUI中弯引号的呈现方式，以确保在电子邮件投放中准确显示字符。 (NEO-85687)
* 修复了镜像页面链接功能，从而确保镜像页面中的语言变体之间能够正确导航。 (NEO-85625)
* 解决了Web应用程序日期选取器中的日期格式问题，确保与日文日期格式(`yyyy-mm-dd`)兼容。 (NEO-85234)
* 修复了中间源中替代工艺路线设置的后处理工作流问题，确保正确执行工作流。 (NEO-85111)
* 提高了使用批次时的Android投放吞吐量，确保投放部分根据计划以正确顺序进行处理。 (NEO-84324)
* 修复了由于`to_varchar`函数中出现null处理错误而导致的投放准备失败，从而确保顺利启动营销活动。 (NEO-84108)
* 已解决因过时的`libcurl`和`libssh2`版本导致的SFTP连接问题，确保与Azure托管的SFTP服务器兼容。 (NEO-84038)
* 修复了涉及密钥对身份验证错误的Snowflake FDA连接器问题，确保成功连接数据库。 (NEO-84024)
* 解决了类型规则功能问题，确保在推送投放中正确应用压力规则。 (NEO-84010)
* 解决了升级后由不匹配的日期和时间戳比较导致的BigQuery查询错误，确保与筛选条件兼容。 (NEO-83826)
* 解决了在恢复因个性化错误而暂停的投放时，投放活动失败的问题。 此修复可确保投放工作流更加顺畅，并防止出现与暂停活动相关的错误。 (NEO-83809)
* 修复了使用“目标记录加载查询”选项时FFDA中的问题。 添加了对“order by”和“where”子句的支持。 (NEO-83793)
* 解决了由null值写入broadLogRcp表中不可为空的列导致的循环投放故障。 此修复提高了投放的可靠性，并防止了在实时营销活动期间发生错误。 (NEO-83729)
* 解决了在投放准备期间复制种子地址，导致消息计数不一致的问题。 此修复确保准确定位并防止重复错误。 (NEO-83703)
* 修复了在有效期之后发送生产投放的一个关键问题，该问题可能会导致法律问题。 现在，投放将严格遵守其定义的有效期。 (NEO-83350)
* 解决了将大数据卷加载到Teradata表中时遇到的空间问题。 此修复程序可优化数据处理并解决生产环境中的间歇性错误。 (NEO-83252)
* 解决了与SendMetricsToNewRelic错误相关的技术工作流失败，该错误会导致RT事件处理延迟。 此修复可确保更顺利地执行工作流并防止出现事件积压。 (NEO-83143)
* 修复了由FFDA交互实例中ID到UUID的转换问题导致的数据库清理工作流故障。 此更新确保正确的清理操作并减少系统负载。 (NEO-83138)
* 解决了由种子成员内部名称长度限制导致的投放失败。 此修复允许更长的内部名称，而不影响投放个性化。 (NEO-83044)
* 修复了投放因随机错误而卡在个性化待处理中的问题。 此更新可确保更顺畅的个性化流程和可靠的投放执行。 (NEO-82781)
* 解决了由于API错误和速度缓慢而无法在控制台中审查优惠建议的问题。 此修复提高了UI响应速度，并确保了正确的选件功能。 (NEO-82742)
* 解决了使用自定义投放对象时Adobe Campaign控制台中的间歇性崩溃问题。 此修复程序可确保使用自定义工作流时的稳定性和可靠性。 (NEO-82675)
* 修复了从v7迁移到v8后报告的处理缓慢和工作流故障。 此更新优化了活动工作流并确保及时执行。 (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* 修复了MTA子进程卡住、阻止推送和WhatsApp投放的关键问题。 此更新确保通信工作流更顺畅，并防止投放瓶颈。 (NEO-82351)
* 解决了GCP表中的字符串字段在更新Teradata期间导致错误的数据迁移问题。 此修复不需要解决方法，提高了工作流效率。 (NEO-82260)
* 更新了数据库清理逻辑，以考虑FFDA实例中的主数据库，从而防止不必要的清除不存在的表的尝试。 此修复程序可优化清理操作。 (NEO-81879)
* 解决了通过将子工作流与枚举字段结合使用导致的控制台崩溃问题。 此修复程序可确保使用扩充的工作流时的稳定性。 (NEO-81864)
* 修复了在投放复制后目标映射中的子关联字段被错误修改，从而导致工作流失败的问题。 此更新可确保一致的子关联值。 (NEO-81809)
* 在Adobe Campaign Classic v8的文件传输活动中添加了对通配符字符的支持，使用户能够在工作流中上传具有动态名称（例如，`abc_*`）的文件。 (NEO-81758)
* 引入了一个选项，用于在Adobe Campaign Classic v8的iOS推送通知中启用`content-available`标志。 此增强功能允许移动设备应用程序将通知存储在收件箱中，并支持后台更新，从而解决由APNS限制导致的投放放弃问题。 (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* 在Adobe Campaign Classic v8中为BigQuery连接添加了超时配置选项。 此增强功能允许用户调整查询的超时时段，解决由于默认超时限制导致的查询失败问题。 (NEO-81222)
* 修复了迁移v8后，通过拆分和备用路由外部帐户发送的投放的镜像页面URL失败的间歇性问题。 基础投放部分现已正确复制到`mirrorPageInfo`。 (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* 修复了客户端控制台中的“访问新Web UI”按钮，以指向生产实例的正确URL (`https://experience.adobe.com`)。 这解决了生产环境中无效URL的问题。 (NEO-80673)
* 修复了拆分活动中同时使用排序和大小（以区段的百分比表示）导致SQL错误的问题。 该功能现在可以正确运行。 (NEO-80432)
* 已使用`CCurlAzureBlobStorage::UploadStream`解决工作流中的崩溃问题。 在Azure Blob存储上传期间，工作流现在执行时没有分段错误。 (NEO-79598)
* 解决了在生产环境中无法从客户端控制台查看镜像页面的问题。 镜像页面链接现在在电子邮件视图和控制台视图中均可正常工作。 (NEO-78946)
* 修复了投放日志问题：尽管消息投放成功，但一些日志被错误地标记为“投放已取消”。 与联系日期和事件日期差异相关的根本原因已得到解决。 (NEO-78933)
* 已更新`com.google.code.gson:gson`库以提高安全性。 (NEO-78299)
* 解决了FDA连接日志(`nmsconnectionlogs`)中导致工作流失败的重复键约束错误。 已调整插入逻辑以防止出现重复的ID。 (NEO-78050)
* 修复了隔离的电子邮件地址在地址表中被错误地标记为移动地址，从而导致投放分析错误的问题。 投放对象之间的协调逻辑已更正。 (NEO-76986)
* 解决了在将control groups与Oracle数据库结合使用时出现的投放准备失败问题。 已更正SQL查询生成，以确保与Oracle数据库兼容。 (NEO-76947)
* 解决了新月份过渡期间由于同时创建文件夹导致的投放故障。 已调整投放文件夹创建逻辑，以防止重复键违规。 (NEO-76824)
* 修复了Teradata外部帐户中时区转换不一致的问题。 显示的时间戳现在与配置的时区设置正确对齐。 (NEO-76716)
* 改进了数据库清理工作流，以高效地处理大型数据集。 使用行ID和绑定变量的新方法已实现以优化删除性能。 (NEO-76439)
* 解决了使用“其他”渠道的外部投放未生成输出文件的问题。 投放属性现在正确包含所生成文件的文件路径。 (NEO-75962)
* 修复了`ffdaReplicateStagingData`工作流中因大数据更新导致的错误。 已优化超时设置和表大小管理，以防止工作流失败。 (NEO-75643)
* 解决了预览直邮输出文件导致功能板变为空白的问题。 现在，在文件预览后，仪表板可正确显示。 (NEO-75359)
* 增强了推送通知的跟踪指示器，以包含点击次数和打开次数。 指示器（如`@recipientClick`、`@personClick`和`@totalRecipientClick`）现在会考虑移动设备通知点击次数。 (NEO-75240)
* 修复了具有外部取消挂起状态的投放的清理工作流中的错误。 已更正数据库记录检索逻辑。 (NEO-74833)
* 解决了俄罗斯（UTC+3:00莫斯科）中`nlserver`输出时间不正确的时区差异问题。 时间同步逻辑已更新。 (NEO-74754)
* 修复了`defaultMidSourcingDlvStat`工作流中由于MSSQL数据库的SQL语法不正确而导致的错误。 已调整查询生成逻辑以实现兼容性。 (NEO-74156)
* 解决了Web进程中的多次崩溃问题。 (NEO-73174)
* 修复了条件中存在撇号时BigQuery查询失败的问题。 查询处理逻辑已更新，可正确解释特殊字符。 (NEO-72547)
* 解决了具有排除过滤器的分类规则无法正确工作的问题。 修复了为投放准备生成SQL查询的问题。 (NEO-72292)
* 解决了退回管理中事件日期和联系日期之间的差异。 时区处理逻辑已得到改进。 (NEO-72277)
* 增强了对直邮投放中错误转换的UTF-8字符的处理。 现在可正确处理隐藏字符以防止投放失败。 (NEO-72148)
* 修复了入站SMS活动中过滤器导致保存问题的错误。 现在可正确保存工作流而不会生成错误。 (NEO-70427)
* 更正了在优惠空间中针对分组资格标准生成的SQL查询。 已添加SQL条件中缺少的括号以确保正确筛选。 (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* 修复了BigQuery数据加载工作流中由HTTP内容或传输编码问题导致的间歇性错误。 连接处理逻辑已得到改进。 (NEO-66989)

## 版本 8.6.5 {#release-8-6-5}

_2025 年 4 月 25 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**限量发布版** (LA)。

### 新增功能 {#features-8-6-5}

**新短信发送连接器** - 短信发送连接器经过现代化改造和改进，可启用收发器模式 SMPP 连接、启用持久 SMPP 连接，并确保从 Adobe Campaign Standard 过渡的环境具有更好的兼容性。新的短信外部帐户现在可用于所有新的短信实施。现有实施仍受支持，但建议迁移到此新的现代化扩展连接器。[了解更多信息](../send/sms/sms.md)。

### 一般改进 {#improvements-8-6-5}

* 在企业 (FFDA) 部署中，应用程序的全局性能已得到改进，包括投放校样发送和数据库清理。

* 为提高应用程序之间所有通信的安全性，现在外部 API 调用支持 mTLS。

* 邮件传输代理 (MTA) - 修复了孤立 MTA 子项停留在 **[!UICONTROL Start pending]** 状态的问题。

### 修复 {#fixes-8-6-5}

此版本中还修复了以下问题：

NEO-67620、NEO-71534、NEO-80245、NEO-81105、NEO-81758、NEO-81908、NEO-82351、NEO-82742、NEO-83044、NEO-83138、NEO-83350、NEO-83729、NEO-83793、NEO-83809、NEO-84038、NEO-84108、NEO-85269、NEO-86121、NEO-86556、NEO-86739

## 版本 8.7.4 {#release-8-7-4}

_2025 年 4 月 10 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#features-8-7-4}

* **SMS REST API 支持** - 事务性消息传递 REST API 现可用于短信渠道。当负载中同时存在电子邮件和移动电话时，您可以使用“wishedChannel”字段来指定渠道。如果未提供，则默认使用电子邮件，除非 wishedChannel 明确要求使用短信。

* **多语言投放** - 从 4 月版的 Campaign Web 用户界面开始，您将能够以不同语言发送多个电子邮件投放，并访问相关的动态报告。此功能仅在 4 月底于 Adobe Campaign Web 用户界面中推出，并且需要服务器更新至 Campaign v8.7.4。

### 修复 {#fixes-8-7-4}

此版本中修复了以下问题：

NEO-80245、NEO-83559

## 版本 8.7.3 {#release-8-7-3}

_2025 年 2 月 14 日_

>[!AVAILABILITY]
>
>此版本为&#x200B;**有限发布版** (LA)。仅供&#x200B;**从 Adobe Campaign Standard 迁移到 Adobe Campaign v8** 的客户使用，并且不能部署在任何其他环境上。
>
>作为正在过渡到 Campaign v8 的 Campaign Standard 用户，请在 [Campaign v8 Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/acs-migration){target="_blank"}中了解有关此过渡的更多信息。

### 新增功能 {#features-8-7-3}

* **事务性消息的动态报告** - 您现在可以在动态报告用户界面中监控事务性消息。通过这些报告，营销人员能够实时查看事务性消息的所有报告量度和维度，并实时分析通过模板发送的投放。[了解更多信息](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=zh-Hans){target="_blank"}

* **事务性消息传递 REST API** - 现在可以对电子邮件使用基于事件的事务性 API。[了解更多信息](../dev/api/get-started-apis.md)

### 修复 {#fixes-8-7-3}

此版本中修复了以下问题：

NEO-79373、NEO-81908、NEO-83081

## 版本 8.6.4 {#release-8-6-4}

_2025 年 1 月 15 日_

### 一般改进 {#improvements-8-6-4}

* 在[企业 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)环境中的投放分析期间，Campaign 应用程序的稳定性得到了改进。
* 此版本附带改进和增强的 FFDA 架构机制，包括密钥管理、暂存和数据复制。
* 已为[企业 (FFDA) 部署](../../v8/architecture/enterprise-deployment.md)引入新的技术工作流。这些工作流通过将并行复制请求集中到相应的表中，来复制投放和相关数据。这些工作流以 `Replicate nms` 开头。[了解更多信息](../architecture/replication.md)
* 工作流属性中现在有新的 **Enable watchdog supervisor to keep workflow running permanently** 选项。启用此选项后，工作流会在发生错误后自动重新启动。如果工作流仍然出错，将默认每 30 秒重新启动一次。要调整此间隔，您可以创建一个新的 `XtkWorkflow_WatchdogRestartTimerTimeout` 选项并设置整数数据类型以指定新延迟。此选项只应在技术工作流中启用。[了解更多信息](../../automation/workflow/workflow-properties.md#execution)

### 安全性改进 {#security-8-6-4}

通过 **[!UICONTROL Adobe Experience Cloud]** 外部帐户与 Adobe 解决方案和应用程序的连接已更新，以加强安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 兼容性更新 {#comp-8-6-4}

添加了以下 FDA 连接器。请参见[此页面](compatibility-matrix.md#FederatedDataAccessFDA)。

* 现在支持将 Databricks 用作 Adobe Campaign 联合数据访问 (FDA) 的外部数据库。

* 现已提供新的 Amazon Redshift FDA ODBC 连接器。它提供了改进的连接性、更轻松的维护以及增强的兼容性。此新版本提供了以下改进：

   * 新的连接器基于 ODBC 接口，该接口兼容我们最新的 FDA 连接器。这可确保实现长期支持。
   * 它还引入了一种使用 s3 存储桶的新数据加载机制，显著提高了性能。

  仍可使用旧版连接器。如果您想要试用新版，请联系您的 Adobe 代表。

### 修复 {#fixes-8-6-4}

此版本中修复了以下问题：

NEO-48232、NEO-67814、NEO-71388、NEO-74855、NEO-75643、NEO-75962、NEO-76132、NEO-76958、NEO-76986、NEO-77162、NEO-77452、NEO-78946、NEO-79373、NEO-80243、NEO-80314、NEO-81127、NEO-81209、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512、NEO-81520、NEO-81566、NEO-81704、NEO-81908、NEO-82195、NEO-82591、NEO-82592、NEO-82640、NEO-82665、NEO-82781、NEO-82920、NEO-83081、NEO-83096、NEO-83137、NEO-83143。

