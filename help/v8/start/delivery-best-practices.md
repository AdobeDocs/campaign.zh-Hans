---
title: 投放最佳实践
description: 了解使用Adobe Campaign设计和发送投放时的最佳实践
feature: Email, Push, SMS, Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: cb6094eb-0010-4c62-9589-3b52fd60c2c2
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '2936'
ht-degree: 3%

---

# 投放最佳实践 {#delivery-best-practices}

阅读以下Campaign投放功能的最佳实践。

## 优化投放 {#optimize-delivery}

在开始创建投放之前，您可以采取多种操作来保护和优化上游发送流程。 以下部分概述了用于优化Adobe Campaign配置的最佳实践和建议过程。

### 平台性能

以下几个因素可能会直接影响服务器性能并拖慢Campaign平台的运行速度：

* [个性化](../send/personalize.md)元素的数量和类型：电子邮件中的个性化会从数据库中提取每个收件人的数据。 对于许多个性化元素，准备投放所需的数据量会更高。 这会降低平台的运行速度。 在[本节](../send/personalize.md#perso-guardrails)中了解有关个性化护栏的更多信息。

* 服务器负载：当营销服务器同时处理多个不同的任务时，可能会降低性能。 营销服务器需要协调所有投放的所有传入和传出数据，以确保数据正确且及时。
要避免这种情况，请与团队的其他成员协调投放计划，以确保最佳性能。

* 工作流执行：监测工作流对于避免平台性能问题至关重要。 遵循本文档[&#128279;](../../automation/workflow/workflow-best-practices.md#execution-and-performance)中列出的准则。

* 使用[性能监控](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring){target="_blank"}功能连接到[Campaign控制面板功能](https://experienceleague.adobe.com/en/docs/control-panel/using/discover-control-panel/key-features){target="_blank"}以监控您的平台。

#### 隔离管理 {#quarantine-management}

保持良好的隔离管理流程符合您的最大利益。

开始在新平台上发送电子邮件时，您可以使用不完全限定的地址列表。 如果发送到无效地址或honeypot地址（邮箱仅用于欺骗垃圾邮件发送者），这将开始降低平台的声誉。 良好的隔离管理流程有助于：保持地址质量、避免Internet访问提供商的阻止列表并减少错误率、加快交付速度和吞吐量。


在[Adobe可投放性最佳实践指南](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform){target="_blank"}中了解如何启动新平台。

[此部分](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations){target="_blank"}中列出了技术建议。


+++ **阅读一些最佳实践**

* 如果存在无效地址列表，Adobe建议通过&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** > **[!UICONTROL Non deliverables and addresses]**，将其导入隔离表。

* 在投放分析过程中，默认情况下会排除其地址被隔离的收件人：这些收件人未定位。 这会加快投放速度，因为错误率对投放速度有显着的影响。 例如，当收件箱已满或地址不存在时，可以隔离电子邮件地址。
Adobe Campaign会根据返回的错误类型管理错误地址。 [了解有关隔离的更多信息](../send/quarantines.md)

* 如果无效地址的比率过高，某些互联网访问提供商会自动将电子邮件视为垃圾邮件。 因此，隔离可让您避免被这些提供商添加到阻止列表。

+++



### 双重选择加入机制 {#double-opt-in}

为避免向无效地址发送消息、限制不当通信并提高发件人信誉，Adobe建议对订阅后确认实施双重选择加入机制。 这有助于确保收件人有意订阅。

## 使用模板 {#use-templates}

通过为最常见的活动类型提供现成的方案，交付模板可以提高效率。 借助模板，营销人员可以在更短的时间内部署具有最小自定义的新营销活动。 [了解有关投放模板的更多信息](../send/create-templates.md)。

### 子域和品牌化 {#subdomains-and-branding}

在Adobe Campaign中管理多个品牌时，Adobe建议为每个品牌拥有一个子域。 例如，银行可以具有与其每个区域机构对应的多个子域。 如果银行拥有bluebank.com域，则其子域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每个子域拥有一个投放模板，让您能够始终为每个品牌使用正确的预配置参数，从而避免错误并节省您的时间。 在[促销活动控制面板文档](https://experienceleague.adobe.com/en/docs/control-panel/using/subdomains-and-certificates/subdomains-branding){target="_blank"}中了解有关子域品牌的更多信息。

### 配置地址 {#configure-addresses}

请确保应用以下准则：

* 必须提供发件人地址，才能发送电子邮件。 有些ISP（Internet服务提供商）在接受消息之前会检查发件人地址的有效性。
* 格式错误的地址可能导致接收服务器拒绝该地址。 您必须确保提供了正确的地址。
* 地址必须明确识别发件人。 域必须归发件人所有并向其注册。
* Adobe建议创建对应于为投放和回复指定的地址的电子邮件帐户。 请与您的邮件系统管理员联系。

+++ **在Campaign UI中配置地址的步骤**

要在Campaign界面中配置地址，请执行以下步骤：

1. 在[投放模板](../send/create-templates.md)中，单击&#x200B;**[!UICONTROL From]**&#x200B;链接。 在&#x200B;**[!UICONTROL Email header parameters]**&#x200B;窗口中，输入设置。

1. 在&#x200B;**[!UICONTROL Sender address]**&#x200B;字段中，确保地址域与您委派给Adobe的子域相同。 您可以更改“@”之前的部分，但不能更改域地址。

1. 在&#x200B;**[!UICONTROL From]**&#x200B;字段中，使用易于收件人识别的名称（如您的品牌名称）来提高投放的打开率。 要进一步改善收件人的体验，您可以添加人员的姓名，例如“Emma from Megastore”。

1. 在&#x200B;**[!UICONTROL Reply address text]**&#x200B;字段中，默认情况下使用发件人的地址进行回复。 但是，Adobe建议使用现有的真实地址，例如您品牌的客户关怀地址。 在这种情况下，如果收件人发送回复，客户关怀团队将能够处理。

### 设置对照组 {#set-up-control-group}

发送投放后，您可以将排除的收件人的行为与接收投放的收件人的行为进行比较。 然后，您可以衡量营销活动的效率。 了解有关控制组的详细信息[本节](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group)。

### 使用类型应用过滤器或控制规则 {#create-typologies}

分类包含在发送任何消息之前，在分析阶段应用的检查规则。

在模板属性的&#x200B;**[!UICONTROL Typology]**&#x200B;选项卡中，您可以根据需要选择自定义分类。

例如，为了更好地控制出站流量，您可以通过定义每个子域的一个关联并为每个关联创建一个类型来定义可以使用的IP地址。 相关性在实例的配置文件中定义。 联系Adobe Campaign管理员。

有关类型的详细信息，请参阅[此部分](../../automation/campaign-opt/campaign-typologies.md)。

## 优化您的内容 {#optimize-content}

### 生成个性化内容 {#perso-content}

要个性化您的消息，您可以使用存储在数据库中的收件人数据，或通过跟踪、登陆页面、订阅等收集的数据。 [本节](../send/personalize.md)中介绍了Personalization的基础知识。

+++ **阅读一些最佳实践**

* 检查您的个性化设置 — 确保您的消息内容经过正确设计，以避免任何可能与个性化相关的错误。 Adobe Campaign个性化标记始终具有以下形式： `<%=table.field%>`。 在个性化块中错误使用参数可能是个问题。 例如，JavaScript中的变量应按以下方式使用：

  &grave;&grave;
  <%
  var brand = "xxx"
  %>
  &grave;&grave;

  有关个性化块的更多信息，请参阅[此章节](../send/personalization-blocks.md)。

* 准备个性化数据 — 您可以在工作流中准备个性化数据，以改进投放准备分析。 如果个性化数据来自通过联合数据访问(FDA)的外部表，则应当特别使用此字段。 该选项在此[部分](../send/personalization-data.md#optimize-personalization)中有说明
+++

### 构建优化内容 {#build-optimized-content}

在构建电子邮件时，请应用电子邮件内容的一般最佳实践。

+++ **阅读一些最佳实践**

* 保持设计简单

* 请牢记移动用户

* 避免完全基于图像的电子邮件

* 使用电子邮件安全字体

* 编码特殊字符

+++


### 主题行  {#subject-line-check}

处理电子邮件[主题行](../send/personalization-fields.md#personalization-fields-uc)以提高打开率。


+++ **阅读一些最佳实践**


* 避免使用过长的主题。 最多使用50个字符

* 避免使用可被视为垃圾邮件的重复单词，如“free”或“offer”

* 避免使用大写字母

* 请勿使用“！”、“£”、“€”、“$”等特殊字符

+++

### 镜像页面 {#mirror-page-check}

始终包含镜像页面链接。 首选位置是电子邮件的顶部。 在[此页面](../send/mirror-page.md)中了解有关镜像页面的更多信息

### 退订链接 {#unsub-link-check}

退订链接是必需的。 它必须可见且有效，并且表单必须有效。 默认情况下，在分析消息时，内置&#x200B;**[!UICONTROL Unsubscription link approval]** [分类规则](../../automation/campaign-opt/control-rules.md)会检查是否包含选择退出链接，如果缺少该链接，则会生成警告。

了解如何在此部分[&#128279;](../send/personalization-blocks.md)中插入选择退出链接。

+++ **应用此最佳实践**

由于始终可能存在人为错误，因此请在每次发送前检查选择退出链接是否正常工作。 例如，在发送校样时，请确保链接有效，表单处于联机状态，并且`No longer contact this recipient `字段已更改为`Yes`。

+++

### 电子邮件大小 {#email-size-check}

为避免性能或可投放性问题，建议的最大电子邮件大小约为&#x200B;**35KB**。 要检查邮件大小，请浏览&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡并选择测试配置文件。 生成后，消息大小将显示在右上角。


+++ **阅读一些最佳实践**

* 删除多余或未使用的样式

* 将部分电子邮件内容移至登陆页面

* 缩小代码

确保在最终发送之前测试任何更改。

+++


### 短信长度 {#sms-length-check}

默认情况下，短信的字符数应符合GSM（全球移动通信系统）标准。 使用 GSM 编码的短信消息长度上限为 160 个字符，而对于分段发送的消息，每段短信的长度上限为 153 个字符。


+++ **阅读一些最佳实践**

* 要将短信消息中的所有字符都保持不变，例如不要更改正确名称，请不要启用音译。

* 但是，如果短信消息包含许多GSM标准无法识别的字符，请启用音译以限制发送消息的成本。 在本节[&#128279;](../send/sms/smpp-external-account.md#smpp-transliteration)中了解更多。

* 您可以应用短信音译，这包括当GSM标准无法识别短信的一个字符时，用另一个字符替换该字符。 请注意，将个性化字段插入短信消息内容，可能会引入GSM编码无法识别的字符。 作为Campaign管理员，您可以通过选中相应&#x200B;**[!UICONTROL External account]**&#x200B;的SMPP渠道设置选项卡中的相应框来启用字符音译。 [了解详情](../send/sms/smpp-external-account.md#smpp-transliteration)

+++

### 避免使用附件

附件仍然是恶意软件泛滥最常见的媒介之一，尤其是当它们大量发送时。 包括一个指向文档的安全链接，而不是附加文档。 这可以确保额外的安全层以防止无意中的重新分发，并大大减少由于消息大小或安全原因在入站电子邮件网关上拒绝消息的可能性。

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).-->

## 管理图像 {#manage-images}

以下是一些针对电子邮件营销活动优化图像的特定准则。

### 防止图像阻塞 {#image-blocking}

默认情况下，某些电子邮件客户端会阻止图像，用户可能会更改其设置以阻止图像以供在数据使用时保存。  因此，如果不下载图像，则整个消息可能会丢失。

+++ 要避免此问题，您可以应用这些最佳实践

* 避免完全基于图像的电子邮件。 使您的内容与图像和文本保持平衡。

* 如果文本必须包含在图像中，请使用替换文本和标题文本以确保消息正确传递。 设置替代/标题文本的样式以改进其外观。

* 避免使用背景图像，因为某些电子邮件客户端不支持这些图像。
+++

### 使图像具有响应性 {#responsive-images}

尝试使图像具有响应性且可调整大小，以使它们在所有上下文和设备中都可见。 请注意，这可能会产生成本影响，因为构建所需的时间较长。

### 使用绝对图像引用 {#absolute-images}

要从外部访问，必须在外部可访问的服务器上存在电子邮件中使用的图像以及与营销活动关联的公共资源。

* 通过投放助手，您可以导入包含图像的HTML页面，或直接使用HTML编辑器通过&#x200B;**[!UICONTROL Image]**&#x200B;图标插入图像。

* 如果未显示图像，请检查图像在服务器上是否可用。 为此，请浏览到投放的&#x200B;**Source**&#x200B;选项卡。 在Web浏览器中查找图像并复制粘贴每个图像的URL。 如果未显示图像，请联系您的IT管理员或提供投放内容的第三方供应商。

### 预览和测试消息 {#preview-msg}

Adobe建议预览您的消息以检查其个性化设置以及收件人如何看到您的投放。

在投放助手中，**[!UICONTROL Preview]**&#x200B;子选项卡允许您查看收件人的每个内容的呈现。 将内容的个性化字段和条件元素替换为所选用户档案的相应信息。 [了解详情](../send/preview-and-proof.md)。


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## 定义正确的受众 {#define-the-right-audience}

目标群体是关键：仔细构建列表，在常用的电子邮件客户端和移动设备上测试电子邮件，并确保电子邮件列表是最新的（不含未知或过时的地址）。 您还可以发送校样来帮助设置完整的验证周期。 在[此章节](../audiences/gs-audiences.md)中详细了解受众。

### 定位正确的受众 {#target-the-right-audience}

准备好内容后，您需要仔细定义接收消息的人员。

为了成功交付，您需要将最相关的个性化内容发送给正确的收件人。 Adobe Campaign使您能够构建最准确的目标：您可以根据收件人的年龄、本地化、购买内容、是否在上一次投放中单击链接等选择收件人。 通过Adobe Campaign，您还可以定义测试用户档案、控制组和种子地址，以确保您的目标正确。

### 目标映射 {#target-mappings}

在Campaign中，默认情况下，投放模板以&#x200B;**收件人**&#x200B;为目标。 Adobe Campaign为您的投放提供了其他目标映射，您可以根据需要更改这些映射。 例如，您可以向通过社交网络收集用户档案的访客或订阅了信息服务的访客投放。

此部分[&#128279;](../audiences/target-mappings.md)中提供了这些映射。

### 外部收件人 {#external-recipients}

您可以向存储在外部文件中而不是数据库中保存的收件人投放。 在本节[&#128279;](create-message.md#select-external-recipients-selecting-external-recipients)中了解更多。

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### 测试收件人 {#test-recipients-seed-addresses}

要测试您的投放，请在发送到主目标之前使用验证。

确保选择适当的校样收件人，因为他们验证消息的表单和内容。 在此部分[&#128279;](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target)中介绍了定义校样收件人的步骤。


### 删除重复地址 {#deduplicate-addresses}

请务必避免电子邮件地址重复，因为这可能会对目标产生影响：

* 分割目标时，同一消息可能会发送多次。

* 如果收件人在收到消息后取消订阅，则其重复的用户档案仍会收到未来的消息。

对地址进行重复数据删除可保护您的发送信誉并确保良好的隔离管理。

**相关主题：**

* [重复数据删除活动](../../automation/workflow/deduplication.md)。
* [用例：使用重复数据删除活动的合并功能](../../automation/workflow/deduplication-merge.md)。


## 发送前执行所有检查 {#perform-all-checks}

消息准备就绪后，请确保其内容在所有设备上均正确显示，并且不包含任何错误，例如错误的个性化或断开的链接。 在发送消息之前，还要确保参数和配置与投放一致。

本节[&#128279;](../send/preview-and-proof.md)中介绍了验证投放的步骤。

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### 验证消息 {#proof-messages}

通过发送校样，可检查选择退出链接、镜像页面和任何其他链接、验证消息、验证是否显示图像、检测可能存在的错误等。您可能还希望检查设计和在不同设备上的呈现效果。

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### 确保您的消息已投放 {#make-sure-your-message-is-delivered}

最后一步就是尽可能提高您的机会，并利用Adobe Campaign的强大功能确保您的邮件确实会发送给相关收件人。

#### 进行验证过程

您可以定义涉及Adobe Campaign操作员和组的完整验证流程，以验证目标和消息内容。 这将确保全面监测和控制营销活动的各个流程：定位、内容、预算、提取和发送证明。 根据用户的权限，用户将收到通知、接收校样并能够验证或拒绝消息。 在本节[&#128279;](../../automation/campaigns/marketing-campaign-approval.md)中了解更多。

#### 使用批次

您可以逐步增加使用批次发送的数量。 这将避免您的邮件被标记为垃圾邮件或您想要限制每天的邮件数。 利用批次，您可以将投放分为多个批次，而不是同时发送大量消息。 在本节[&#128279;](../send/configure-and-send.md#sending-using-multiple-waves)中了解更多。

#### 排定消息优先级

您可以通过指明优先级来设置投放的发送顺序。 为实现此操作，请执行以下步骤：

1. 编辑投放属性，然后选择&#x200B;**[!UICONTROL Delivery]**&#x200B;选项卡。

1. 按从&#x200B;**[!UICONTROL Very low]**&#x200B;到&#x200B;**[!UICONTROL Very high]**&#x200B;的比例定义投放的优先级。

>[!NOTE]
>
>无法定义从投放中发送消息的顺序。

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### 使用分类

您可以使用分类规则根据特定条件排除部分目标。 这可确保在遵守公司通信政策的同时，发送最符合客户需求及期望的邮件。 例如，您可以筛选新闻稿目标中的未成年收件人。 在此示例[&#128279;](../../automation/campaign-opt/filtering-rules.md)中了解更多。


## 跟踪和监视 {#track-and-monitor}

您已单击&#x200B;**发送**&#x200B;按钮？ 让我们看看会发生什么。 发送投放后，借助Adobe Campaign，您可以跟踪已发送的消息，并了解收件人对投放的反应。 这将帮助您改进未来发送并优化下一个营销活动。

## 监测投放 {#monitoring-deliveries}

要控制活动，您必须确保消息确实已发送给收件人。

在Campaign投放仪表板中，您可以检查已处理的消息和投放审核日志。 您还可以控制投放日志中消息的状态。

[请参阅Campaign Classic v7文档以了解有关投放监视的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}


## 跟踪行为 {#track-behaviour}

为了更好地了解收件人的行为，您可以跟踪他们对投放的反应：接收、打开、单击链接、取消订阅等。 在Campaign中，此信息显示在投放所定向收件人的&#x200B;**跟踪**&#x200B;选项卡和投放的“跟踪”选项卡中。

默认启用消息跟踪。 要配置URL，请选择投放助手下方的显示URL选项。 对于消息的每个URL，您可以选择是否激活跟踪。


[请参阅Campaign Classic v7文档以了解有关跟踪功能的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html#sending-messages){target="_blank"}
