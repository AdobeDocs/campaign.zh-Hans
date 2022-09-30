---
title: 使用Campaign和Twitter
description: 了解如何将Campaign环境与Twitter集成
role: User, Admin
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 3%

---

# 使用Campaign和Twitter{#tw-ac-ovv}

的 **管理社交网络（社交营销）** 模块允许您通过Twitter与客户进行交互。 使用此功能可以：

* 发布消息和发送DM — 使用Adobe Campaign Social Marketing在Twitter上发布消息。 您还可以向所有关注者发送私信。

* 收集新联系人 — Adobe Campaign Social Marketing还可轻松获取新联系人：联系用户并询问他们是否希望共享其用户档案信息。 如果客户接受，Adobe Campaign会自动恢复数据，以便您进行定位营销活动，并在可能时实施跨渠道策略。

![](../assets/do-not-localize/speech.png) 作为托管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support) 将Campaign与Twitter连接。 的  **管理社交网络（社交营销）** 必须通过专用包在您的环境中安装加载项，并且必须配置Twitter外部帐户。


要将Adobe Campaign配置为将推文发布到Twitter帐户，请为这些帐户委派对Adobe Campaign的写入权限。 为此，您必须：

1. 创建Twitter帐户并注册开发人员帐户。 [了解详情](#dev-account)
1. （可选）创建用于发送校样的测试Twitter帐户。 [了解详情](#tw-test-account)
1. 创建Twitter应用程序(每个Twitter帐户一个应用程序)。 [了解详情](#create-an-app-on-twitter)
1. 为 **[!UICONTROL Twitter]** (每个Twitter帐户一项服务)。 [了解详情](#create-tw-service)
1. 将您的Twitter帐户与Campaign同步。 [了解详情](#synchro-tw-accounts)

## Twitter开发人员帐户 {#dev-account}

要开始使用此集成，您必须注册 [Twitter开发人员帐户](https://developer.twitter.com){target=&quot;_blank&quot;}。

Campaign使用1.1版本的Twitter API。 要使用它，您需要通过开发人员门户申请提升访问权限。 进一步了解Twitter Impleated Access [本页](https://developer.twitter.com/en/portal/products/elevated){target=&quot;_blank&quot;}。

## 在Twitter上创建应用程序 {#create-an-app-on-twitter}

获得授权访问的批准后，请创建一个Twitter应用程序，以使Adobe Campaign能够将推文发布到您的Twitter帐户。 为此请执行以下操作步骤：

1. 登录到您的Twitter帐户。
1. 连接到 [Twitter开发人员门户](https://developer.twitter.com/en/apps).
1. 选择 **创建应用程序**.
1. 让Twitter助手指导您完成该过程。
1. 要允许Adobe Campaign将推文发布到您的帐户，请编辑到 **应用程序权限** 从应用程序的用户身份验证设置部分。 选择 **读、写和私信**.

   ![](assets/tw-permissions.png)

1. 在 **应用程序类型** 选择 **Web应用程序、自动应用程序或机器人**. 您可以离开 **回调URL** 字段为空，并保存您的配置。

   ![](assets/tw-app-type.png)

1. 返回到应用程序功能板，选择您的应用程序并浏览到 **密钥和令牌** 选项卡。 在 **访问令牌和密钥**，如果 **读、写和私信** 权限未提及，则必须重新生成应用程序的令牌和密钥。 请注意，创建时必须保存所有键和令牌。 您将需要他们配置您的Campaign Twitter服务。

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>每个Twitter帐户需要一个应用程序。 因此，您必须创建另一个测试应用程序以将校样发送到您的测试帐户。

## 在Campaign中创建Twitter服务 {#create-tw-service}

要将您的Campaign实例与Twitter帐户关联，请创建 **Twitter** 服务和向Campaign委派写权限。

>[!CAUTION]
>
>创建一个 **Twitter** 每个Twitter帐户的服务。 因此，您必须创建另一项测试服务，以将校样发送到 [测试帐户](#tw-test-account).
>
>每个 **Twitter** 服务也必须由Adobe在MID实例上创建。 请联系您的Adobe代表以配置您的环境。

要输入设置，您必须同时访问Adobe Campaign控制台和Twitter应用程序权限。

1. 在 **Adobe Campaign**，浏览到 **[!UICONTROL Profiles and targets]** ，然后选择 **[!UICONTROL Services and Subscriptions]** 链接
1. 创建新服务。
1. 选择 **[!UICONTROL Twitter]** 类型。
1. 输入服务的标签和内部名称。

   >[!CAUTION]
   >
   >的 **[!UICONTROL Internal name]** 服务的名称必须与您的Twitter帐户完全相同。

1. 默认情况下，关注者会保存在 **[!UICONTROL Visitors]** 文件夹。 您可以从 **[!UICONTROL Visitor folder]** 字段。 [了解详情](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >的 **[!UICONTROL Synchronize subscriptions]** 选项：此选项会自动取回您的Twitter关注者列表，以便您能够 [发送直邮](../send/twitter.md#direct-tw-messages). 同步由 [专用技术工作流](#synchro-tw-accounts).

1. 从您的Twitter应用程序中，复制 **API密钥** 和 **[API密钥密钥]** 字段并粘贴到 **[!UICONTROL Consumer key]** 和 **[!UICONTROL Consumer secret]** 营销活动的字段 **Twitter** 服务。

1. 从您的Twitter应用程序中，复制 **访问令牌** 和 **访问令牌密钥** 字段并粘贴到 **[!UICONTROL Access token]** 和 **[!UICONTROL Access token secret]** 营销活动的字段 **Twitter** 服务。

1. 在Campaign客户端控制台中，单击 **[!UICONTROL Save]**. 您现在已委派对Adobe Campaign的写入权限。

要检查您的设置，您可以：

* 编辑 **Twitter** 您刚刚创建的服务。
* 浏览 **[!UICONTROL Twitter page]** 选项卡：您的Twitter帐户应会显示。
   ![](assets/tw-page.png)


## 同步您的Twitter帐户 {#synchro-tw-accounts}

Campaign和Twitter之间的同步通过专用的技术工作流进行管理。 这些工作流存储在 **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** 文件夹。

默认情况下，会停止这些操作：在开始使用 **社交营销** 模块。

的 **[!UICONTROL Synchronization of Twitter accounts]** 技术工作流在Adobe Campaign中同步Twitter帐户。 此工作流取回了Twitter关注者列表，以便您可以向他们发送私信。 [了解详情](../send/twitter.md#direct-tw-messages)

默认情况下，此工作流于每星期四早上7:30触发。 您可以使用 **[!UICONTROL Execute pending task(s) now]** 选项，以在您实施此集成时随时启动工作流。  您还可以编辑调度程序以更改工作流触发频率。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}以了解详情。

>[!CAUTION]
>
>要恢复Twitter订阅者列表，请 **[!UICONTROL Twitter account synchronization]** 必须检查链接到帐户的服务的选项。 [了解详情](#create-tw-service)

关注者存储在特定表中：访客表。 要显示Twitter关注者列表，请浏览 **[!UICONTROL Profiles and Targets > Visitors]**.

对于每个关注者，Adobe Campaign会存储以下信息：

* **[!UICONTROL Origin]**: Twitter
* **[!UICONTROL External ID]**:用户标识符
* **[!UICONTROL Username]**:用户的帐户名称
* **[!UICONTROL Full name]**:用户名称
* **[!UICONTROL Number of friends]**:关注者数量
* **[!UICONTROL Checked]**:此字段指示用户是否具有已验证的Twitter帐户

完成此配置后，您可以将推文发布到Twitter帐户，并向关注者发送私信。 [了解详情](../send/twitter.md)

## 在Twitter上创建测试帐户 {#tw-test-account}

除了Twitter帐户之外，还创建一个可用于发送的专用Twitter帐户 [推文校样](../send/twitter.md#send-tw-proofs). 为此请执行以下操作步骤：

1. 创建新的Twitter帐户。
1. 访问帐户  **设置**.
1. 浏览到 **隐私和安全** 和 **受众和标记** 并检查 **Protect您的推文** 选项。 您的推文和其他帐户信息仅对关注您的人员可见。

![](assets/social_tw_test_page.png)

按照上述说明，配置Twitter应用程序和Campaign服务以使用此测试帐户。
