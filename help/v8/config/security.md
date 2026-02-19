---
title: Campaign安全最佳实践
description: 推荐的Campaign安全配置指南
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: 956b2bf5bb8b08654c039b190c020d80ebea223d
workflow-type: tm+mt
source-wordcount: '2896'
ht-degree: 50%

---

# Campaign安全最佳实践 {#ac-security}

Adobe非常重视您的数字体验的安全性。 安全实践深深地植入到我们的内部软件开发与运行流程和工具中，我们的跨职能团队严格遵循这些惯例，以预防、检测事件并快速做出响应。

此外，我们与合作伙伴、领先的研究人员、安全研究机构和其他行业组织开展的协作也有助于我们及时了解最新的威胁和漏洞，并且我们经常将先进的安全技术融入我们提供的产品和服务中。

>[!NOTE]
>
>**Campaign v8托管云服务：**&#x200B;基础架构（网络、服务器、TLS、修补）由Adobe管理。 本页面重点介绍您控制的租户和应用程序级配置：访问管理、身份验证、实例设置、数据保护、编码和操作实践。


## 安全核对清单 {#security-checklist}

使用此核对清单将您的配置与推荐的安全默认值保持一致：

* [访问管理](#access-management)：创建安全组，分配适当的权限，限制管理员使用，每个用户一个操作员，定期查看
* [身份验证和会话](#authentication-and-session)：使用Adobe IMS、强身份策略、会话超时
* 列入允许列表 [实例和网络安全](#instance-and-network-security)： IP、URL权限、通过控制面板的GPG密钥
* [数据和PII保护](#data-and-pii-protection)： HTTPS、PII视图限制、限制密码、保护敏感页面
* [编码准则](#coding-guidelines)：没有硬编码密钥、验证输入、参数化SQL、字幕
* [数据限制](#data-restriction)：限制对外部帐户中密码和密码字段的访问
* [操作和合规性](#operational-and-compliance)：定期与此基线比较，使用审核跟踪

### 在哪里可以找到本指南 {#public-guidance}

Adobe Campaign目前不提供机器可读格式的推荐安全配置指南。 您可以使用以下文档将当前设置与推荐的安全默认值进行比较：

* **此页面** - [Campaign安全最佳实践](#ac-security)（核对清单和详细章节）
* **[Campaign设置（常见问题解答）](../start/campaign-faq-comprehensive.md#settings)** — 将设置与推荐的安全默认值进行比较
* **[增强的安全附加组件](enhanced-security.md)** — 安全CMK集成和安全VPN隧道
* **[权限入门](../start/gs-permissions.md)** — 访问和产品配置文件
* **[限制PII视图](../dev/restrict-pi-view.md)** — 限制对敏感字段的访问
* **[实施指南](../start/implement.md)** — 开始前的安全和隐私

## 隐私

要正确处理隐私和管理个人数据，请在适用于您运营地区的法规范围内开展工作。Adobe Campaign的功能可帮助您遵守[此页面](../start/privacy.md)中列出的法规

### Adobe Experience Cloud 隐私 {#experience-cloud-privacy}

Adobe Campaign 是 Adobe Experience Cloud 解决方案的一部分。Campaign 中处理隐私的方式遵循如下 Experience Cloud 一般原则：

* **使用 Adobe Experience Cloud 时收集哪些信息**

  作为使用 Adobe Experience Cloud 解决方案的公司，您可以选择要收集哪些信息并将其发送到您的 Adobe Experience Cloud 帐户。可能收集的信息类型示例包括 Web 浏览活动、IP 地址、移动设备的位置信息、活动成功率、购买或放入购物车的商品等。

  >[!NOTE]
  >
  >至于所有 Adobe 产品，Campaign 会收集有关应用程序和网站用户的信息。有关此内容的更多信息，请参阅 [Adobe 隐私策略](https://www.adobe.com/cn/privacy/policy.html)。

* **如何使用 Adobe Experience Cloud 收集信息**

   * Adobe Experience Cloud 解决方案使用 cookie 及网络信标（也称为标记或像素）之类的类似技术使您能够收集信息。有关 Adobe Campaign 的 cookie 和跟踪功能的更多信息，请参阅[此部分](#tracking-capabilities)。
   * 您还可以在移动应用程序中使用 Adobe Experience Cloud 技术。有关使用Campaign发送移动投放的详细信息，请参阅[短信渠道](../send/sms/sms-channel.md)和移动应用渠道。

* **用户对您使用 Adobe Experience Cloud 的隐私选择**

  Adobe 要求您提供客户隐私政策，其中描述：

   * 关于 Adobe Experience Cloud 的隐私条例
   * 用户如何可为收集或使用与 Adobe Experience Cloud 有关的信息设置首选项

  >[!NOTE]
  >
  >至于所有 Adobe 产品，Campaign 用户可以选择不共享通过应用程序和网站收集到的关于它们的信息。有关此内容的更多信息，请参阅 [Adobe Experience Cloud 使用信息常见问题解答](https://www.adobe.com/cn/privacy/experience-cloud-usage-info-faq.html)。

有关A dobe Experience Cloud 隐私的更多详细信息，请参阅[此页面](https://www.adobe.com/cn/privacy/marketing-cloud.html)。

## 个人数据和角色 {#personal-data}

在管理隐私时，必须明确应当谨慎处理哪些数据以及由谁处理。
* **个人数据**&#x200B;是指可以直接或间接识别生命个体的信息。
* **敏感个人数据**&#x200B;是与个人的种族、政治观点、宗教信仰、犯罪背景、遗传信息、健康数据、性取向、生物识别信息以及贸易联盟会员资格相关的信息。

将Campaign与其他Experience Cloud解决方案集成时，如果受众可以从一个系统传输到另一个系统，例如[Adobe Analytics](../connect/ac-aa.md)、[Experience Cloud Audiences](../start/shared-audiences.md)、Campaign Standard或通过[CRM Connector](../../automation/workflow/crm-connector.md)与其他解决方案集成，则需要格外注意个人数据保护。

[主要法规](#privacy-regulations)是指管理数据的不同实体，如下所示：

* **数据控制者**&#x200B;是确定收集、使用和共享个人数据的方式和目的权威。

* **数据处理者**&#x200B;是按照数据控制者的指示收集、使用或共享个人数据的任何个人或一方。

* **数据主体**&#x200B;是指对其个人数据进行收集、使用或共享，并可通过参考该个人数据来直接或间接进行识别的任何生命个体。

因此，作为收集和共享个人数据的公司，您是数据控制者，您的客户是数据主体，Adobe Campaign 在按照您的指示处理其个人数据时充当数据处理者。请注意，作为数据控制者，您责任处理与数据主体的关系，例如管理[隐私请求](#privacy-requests)。

### 用例方案 {#use-case-scenario}

为了说明不同用户画像如何互动，以下提供了一个高级 GDPR 客户体验用例的示例。

在本例中，某航空公司是 Adobe Campaign 客户。该公司是&#x200B;**数据控制者**，而航空公司的所有客户都是&#x200B;**数据主体**。此特定案例中的 Laura 是航空公司的一名客户。

以下是此示例中使用的不同用户画像：

* **Laura** 是&#x200B;**数据主体**。她是接收来自航空公司的消息的收件人。Laura 可能是飞行常客，但在某个时刻可能会决定，她不希望航空公司提供任何个性化的广告或营销消息。她将要求航空公司（根据其流程）删除她的飞行常客编号。

* **Anne** 是航空公司的&#x200B;**数据控制者**。她收到Laura的请求，检索为识别数据主体而请求的有用ID，并在Adobe Campaign中提交请求。

* **Adobe Campaign** 是&#x200B;**数据处理者**。

![](assets/privacy-gdpr-flow.png)

以下是此用例的一般流程：

1. **数据主体** (Laura) 通过电子邮件、客户关怀或网站向&#x200B;**数据控制者**&#x200B;发送 GDPR 请求。

1. **数据控制者** (Anne) 通过界面或使用 API 将 GDPR 请求推送给 Campaign。

1. 一旦&#x200B;**数据处理者** (Adobe Campaign) 收到该信息，就会对 GDPR 请求采取操作，并向&#x200B;**数据控制者** (Anne) 发送响应或确认。

1. 然后，**数据控制者** (Anne) 审查该信息，并将其发回至&#x200B;**数据主体** (Laura)。

## 数据采集 {#data-acquisition}

通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并监控收件人的同意至关重要。

* 始终让收件人同意接收通信。为此，请尽快保持遵守选择退出请求并通过双重选择加入流程来验证同意。有关此内容的更多信息，请参阅[使用双重选择加入创建订阅表单](https://experienceleague.adobe.com/en/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}。
* 请勿导入欺诈性列表，并使用种子地址确认您的客户端文件未被用于欺诈用途。有关此内容的更多信息，请参阅[关于种子地址](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank}。
* 通过同意和权限管理，您可以跟踪收件人的偏好，以及管理组织内谁可以访问哪些数据。有关更多信息，请参阅[此章节](#consent)。
* 促进和管理收件人的隐私请求。有关更多信息，请参阅[此章节](#privacy-requests)。

## 隐私管理 {#privacy-management}

隐私管理是指可帮助您遵守隐私法规（GDPR、CCPA等）的所有流程和工具。

Adobe Campaign 为您提供专门用于隐私管理的各种功能集：
* 同意管理、数据保留和用户角色。请参阅[此小节](#consent)。
* 隐私请求（访问权和被遗忘权）。请参阅[此小节](#privacy-requests)。
* 选择退出个人信息销售（特定于CCPA）

[此部分](https://helpx.adobe.com/cn/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)介绍了 Campaign 的主要隐私功能以及所涉及用户画像的示例。

### 同意、保留和角色 {#consent}

Adobe Campaign 最初提供对隐私至关重要的重要功能：

* **同意管理**：通过订阅管理流程，您可以管理收件人的偏好并跟踪哪些收件人已选择加入哪种类型的订阅。有关此内容的更多信息，请参阅[关于订阅](../../automation/workflow/subscription-services.md)。
* **数据保留**：所有内置标准日志表都具有预设的保留期，通常将其数据存储限制为 6 个月或更短时间。可以使用工作流设置其他保留期。有关此内容更多信息，请联系 Adobe 顾问或技术管理员。
* **权限管理**：Adobe Campaign 使您能够通过不同的预建或自定义角色来管理分配给各种 Campaign 操作员的权限。这允许您管理公司内可以访问、修改或导出不同类型数据的人员。有关此内容的更多信息，请参阅[关于访问管理](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}。

### 隐私请求 {#privacy-requests}

Adobe Campaign 提供其他功能来促使您作为数据控制者为特定隐私请求做好准备：

* **访问权**&#x200B;是数据主体从数据控制者处就与其有关的个人数据是否正在进行处理、处理位置和处理原因获得确认的权限。

* **被遗忘权**（删除请求）允许数据主体通过数据控制者擦除其个人数据。

**访问**&#x200B;和&#x200B;**删除**&#x200B;请求将显示在[此部分](../start/privacy.md)中。

[此部分](../start/privacy.md)中详细描述了创建这些请求的实施步骤。

## 跟踪功能 {#tracking-capabilities}

### Cookie {#cookies}

凭借其跟踪功能，Adobe Campaign 可让您使用三种类型的 Cookie 跟踪投放对象的浏览情况：会话 Cookie 和两种永久 Cookie。

* **会话** Cookie：**nlid** Cookie 包含发送到联系人的电子邮件的标识符 (**broadlogId**)，以及消息模板的标识符 (**deliveryId**)。联系人单击由 Adobe Campaign 发送的电子邮件中包含的 URL 后即可添加标识符，让您能够跟踪他们在网络上的行为。关闭浏览器时，将自动擦除会话 Cookie。联系人可以将浏览器配置为拒绝 Cookie。

* 两种&#x200B;**永久** Cookie：
   * **UUID**（通用唯一标识符）Cookie 在 Adobe Experience Cloud 解决方案之间共享。它仅会被设置一次并直到生成新值时才从客户端浏览器中消失。通过使用这种 Cookie，您可以识别访问网站时与 Experience Cloud 解决方案发生交互的用户。它可以通过登陆页（将未知客户活动关联到收件人）或投放进行存放。这种 Cookie 的说明可在[此页面](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html#ec-cookies)中找到。
   * **nllastdelid** Cookie（在 Campaign Classic 20.3 中引入）是永久 Cookie，包含用户在其中单击了链接的上一次投放的 **deliveryId**。当缺失会话 Cookie 时，会使用此 Cookie 来标识将使用的跟踪表。

《通用数据保护条例》(GDPR) 等法规规定，公司在安装任何 Cookie 之前必须获得网站用户的同意。

* 应避免使用弹出窗口，因为浏览器通常会拦截此类窗口。

### 消息跟踪 {#message-tracking}

Adobe Campaign 允许您跟踪已发送的电子邮件和投放对象的行为：打开、点击链接、取消订阅等。有关此内容的详细信息，请参阅[关于邮件](../start/gs-message.md)。

为此，请在您的消息中添加跟踪链接，以便在投放仪表板的Tracking选项卡中衡量您的投放产生的影响以及投放对象的行为。 跟踪数据会在跟踪指标报告中得到说明。 若要了解有关跟踪的更多信息，请参阅[此页面](../send/tracking.md)。

### Web 跟踪 {#web-tracking}

>[!AVAILABILITY]
>
>Web跟踪在Campaign v8中不可用。 在[此页面](../start/v7-to-v8.md#gs-unavailable-features)中了解有关不可用功能的详细信息。

## 数据和PII保护 {#data-and-pii-protection}

隐私配置和强化是安全优化的关键元素。 请遵循以下最佳实践：

* **对所有端点使用HTTPS** — 确保Campaign使用的所有端点（跟踪、镜像页面、Web应用程序、API）都通过HTTPS提供服务。
* **限制PII视图** — 使用[PII视图限制](../dev/restrict-pi-view.md)，以便只有授权操作员才能在架构和屏幕中查看敏感字段（例如电子邮件、电话）。
* **限制对加密密码的访问** — 限制对外部帐户和其他架构中密码和密码字段的访问，以便只有管理员或最小操作员才能查看它们。 请参阅下面的[数据限制](#data-restriction)。
* **保护敏感页面** — 限制对显示或收集PII的镜像页面、Web应用程序和登陆页面的访问；使用操作员和文件夹权限，并在相关情况下使用字幕和同意。

>[!NOTE]
>
>作为托管云服务用户，Adobe将帮助您在环境中实施这些配置。

## 访问管理 {#access-management}

访问管理是安全加固的重要组成部分。 以下是主要最佳实践：

* **创建足够的安全组** — 定义与角色匹配的操作员组，并仅分配每个角色所需的权限。
* **检查每个操作员是否具有适当的访问权限** — 应用最小权限原则；避免默认授予ADMINISTRATION或其他广泛权限。
* **避免使用管理员操作员，避免在管理员组中拥有过多操作员** — 不要共享内置的管理员帐户；为每个物理用户创建一个操作员，以便进行责任追究和审核。
* **每个物理用户一个操作员** — 不共享帐户。 为每个人创建一个Campaign操作员(Adobe ID)，以便审核跟踪和日志可归属。
* **将命名权限的高权限限制** — 将&#x200B;**管理**、**程序执行** (createProcess)和&#x200B;**SQL**&#x200B;授予给少数受信任的操作员；文档拥有这些操作员的身份及其原因。
* **定期查看访问权限** — 定期查看Operator、Operator组和文件夹权限；在角色更改或人员离开时移除或减少访问权限。
* **一致地使用产品配置文件** — 首选在Admin Console中将用户分配给产品配置文件（操作员组）；保持命名一致（例如`campaign - <instance> - <group>`）。 请参阅[权限入门](../start/gs-permissions.md)。
* **控制面板访问权限** — 在Campaign v8中，名称包含“管理员”的产品配置文件或命名权限可授予对Campaign控制面板的访问权限。 避免在配置文件或组名称中使用“管理员”，除非这些用户应具有控制面板访问权限。

可在[此部分](../start/gs-permissions.md)中详细了解权限。

## 身份验证和会话 {#authentication-and-session}

* **使用Adobe IMS** — 所有用户都应使用其Adobe ID (IMS)登录；日常操作员不必依赖旧版登录/密码。
* **依赖强身份和密码策略** — 使用Admin Console或您的身份提供程序来执行MFA和密码策略；确保仅将授权用户分配给Campaign产品配置文件。
* **配置会话超时** — 在可以配置的地方（例如客户端控制台），设置合理的会话超时并在离开工作站时锁定屏幕。

## 实例和网络安全 {#instance-and-network-security}

作为Campaign v8产品管理员，请使用[Campaign控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans){target="_blank"}管理实例级安全性：

* **IP 允许列表 列入允许列表** — 管理IP以访问实例；限制到已知网络（例如，办公室、VPN），并尽可能避免范围过于广泛。
* **URL权限** — 将URL权限限制为实例需要调用的域（API、跟踪、外部服务），以降低服务器端请求滥用的风险。
* **GPG密钥** — 如果您在文件传输或其他使用案例中使用加密，请通过控制面板管理GPG密钥，并根据您的安全策略轮换它们。

## 编码准则 {#coding-guidelines}

在Adobe Campaign（工作流、Javascript、JSSP等）中进行开发时，请始终遵循以下准则：

* **脚本编写** — 尝试避免原始SQL；请使用参数化函数而不是字符串连接。 通过仅将所需的SQL函数添加到允许列表来避免SQL注入。
* **保护数据模型** — 使用已命名权限限制操作员操作并添加系统筛选器(sysFilter)。
* **在Web应用程序中添加验证码** — 将验证码添加到公共登陆页和订阅页。
* **请勿硬编码密码** — 请勿硬编码工作流、JavaScript或JSSP中的密码、API密钥或令牌；请使用外部帐户或安全配置。
* **验证和整理输入** — 验证和整理Web应用程序和工作流参数中的用户输入，以降低注入和XSS风险。
* **对SQL使用允许列表** — 当需要SQL或脚本执行时，请对允许的SQL函数使用该允许列表，并避免通过字符串连接从用户输入生成查询。

请参阅[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}以了解详情。


## 个性化

向内容添加个性化链接时，请始终避免在URL的主机名部分进行任何个性化设置，以避免潜在的安全缺口。 绝不应该在所有URL属性&lt;`a href="">`或`<img src="">`中使用以下示例：

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 数据限制 {#data-restriction}

您必须确保低权限验证用户无法访问加密的密码。 要执行此操作，主要有两种方法：限制仅访问密码字段或访问整个实体。

此限制允许您删除密码字段，但允许所有用户从界面访问外部帐户。 请参阅[此页面](../dev/restrict-pi-view.md)以了解详情。

1. 前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**。

1. 创建新&#x200B;**[!UICONTROL Extension of a schema]**。

1. 选择&#x200B;**[!UICONTROL External Account]** (extAccount)。

1. 在最后一个屏幕中，可以编辑新的srcSchema以限制对所有密码字段的访问：

   您可以通过以下方式替换主元素(`<element name="extAccount" ... >`)：

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   因此，您的扩展srcSchema可能如下所示：

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >您可以将`$(loginId) = 0 or $(login) = 'admin'`替换为`hasNamedRight('admin')`，以使所有具有管理员权限的用户都能看到这些密码。

## 运营和合规性 {#operational-and-compliance}

* **与安全基线比较** — 定期将操作员组、命名权限和文件夹权限与此页面中的推荐进行比较（如果适用，还可比较[增强的安全加载项](enhanced-security.md)），以便与推荐的安全默认值保持一致。
* **使用审核记录** — 依赖于Campaign的审核记录以进行重要更改（例如工作流、投放、密钥配置）；根据合规性和保留策略的要求保留和审查日志。
