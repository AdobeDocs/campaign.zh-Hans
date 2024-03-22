---
title: 使用Campaign和X(Twitter)
description: 了解如何将Campaign环境与X(以前称为Twitter)集成
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 3%

---

# 使用Campaign和X(Twitter) {#tw-ac-ovv}

此 **管理社交网络（社交营销）** 模块允许您通过X(以前称为Twitter)与客户交互。 使用此功能可以：

* 在X上发布消息并发送DM — 使用Adobe Campaign Social Marketing发布消息。您还可以向所有关注者发送私信。

* 收集新联系人 — Adobe Campaign Social Marketing还可让您轻松获取新联系人：联系用户并询问他们是否要共享其个人资料信息。 如果他们接受，Adobe Campaign会自动恢复数据，以便您执行定向活动，并在可能的情况下实施跨渠道策略。


>[!NOTE]
>
>作为托管Cloud Service用户， [联系人Adobe](../start/campaign-faq.md#support) 连接Campaign与X。  **管理社交网络（社交营销）** 必须在您的环境中通过专用软件包安装加载项，并且必须配置Twitter外部帐户。


要将Adobe Campaign配置为将推文发布到您的X帐户，请为这些帐户委派对Adobe Campaign的写入权限。 为此，您必须：

1. 创建X帐户并注册开发人员帐户。 [了解详情](#dev-account)
1. （可选）创建一个测试X帐户来发送校样。 [了解详情](#tw-test-account)
1. 创建X应用程序（每个X帐户一个应用程序）。 [了解详情](#create-an-app-on-twitter)
1. 为创建新服务 **[!UICONTROL Twitter]** （每个X帐户一个服务）。 [了解详情](#create-tw-service)
1. 将您的X帐户与Campaign同步。 [了解详情](#synchro-tw-accounts)

## X开发人员帐户 {#dev-account}

要开始使用此集成，您必须注册 [X开发人员帐户](https://developer.twitter.com){target="_blank"}.

Campaign使用1.1版本的X API。 要使用它，您需要通过开发人员门户申请提升的访问权限。 详细了解X提升的访问权限 [本页内容](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## 在X上创建应用程序 {#create-an-app-on-twitter}

获得提升的访问权限批准后，创建一个X应用程序以使Adobe Campaign能够在您的X帐户上创建帖子。 为此请执行以下操作步骤：

1. 登录到您的X帐户。
1. 连接到 [X开发人员门户](https://developer.twitter.com/en/apps){target="_blank"}.
1. 选择 **创建应用程序**.
1. 让X助手引导您完成该过程。
1. 要允许Adobe Campaign在您的帐户上创建帖子，请编辑到 **应用程序权限** 从应用程序的用户身份验证设置部分。 选择 **读取、写入和直接消息**.

   ![](assets/tw-permissions.png)

1. 在 **应用程序类型** 部分，选择 **Web应用程序、自动应用程序或机器人**. 您可以离开 **回调URL** 字段为空，并保存您的配置。

   ![](assets/tw-app-type.png)

1. 返回应用程序仪表板，选择您的应用程序，然后浏览到 **密钥和令牌** 选项卡。 下 **访问令牌和密码**，如果 **读取、写入和直接消息** 权限未提及，您必须重新生成应用程序的令牌和密码。 请注意，创建时必须保存所有密钥和令牌。 您需要这些配置文件来配置您的CampaignTwitter服务。

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>每个X帐户需要一个应用程序。 因此，您必须创建另一个测试应用程序以将验证发送到测试帐户。
>

## 在Campaign中创建Twitter服务 {#create-tw-service}

要将Campaign实例与X帐户关联，请创建 **twitter** 为Campaign提供服务和委派写入权限。

>[!CAUTION]
>
>创建一个 **twitter** 每个X帐户的服务。 因此，您必须创建另一个测试服务以将验证发送到 [测试帐户](#tw-test-account).
>
>每个 **twitter** 服务还必须由MID实例上的Adobe创建。 请联系您的Adobe代表以配置环境。
>

要输入设置，您必须同时访问Adobe Campaign客户端控制台和X应用程序权限。

1. 在 **Adobe Campaign**，浏览到 **[!UICONTROL Profiles and targets]** 选项卡，然后选择 **[!UICONTROL Services and Subscriptions]** 链接
1. 创建新服务。
1. 选择 **[!UICONTROL Twitter]** 类型。
1. 输入服务的标签和内部名称。

   >[!CAUTION]
   >
   >此 **[!UICONTROL Internal name]** 服务的名称必须与您的X帐户完全相同。
   >

1. 缺省情况下，跟随者保存在 **[!UICONTROL Visitors]** 文件夹。 您可以从中选择其他位置 **[!UICONTROL Visitor folder]** 字段。 [了解详情](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >此 **[!UICONTROL Synchronize subscriptions]** 默认启用选项：此选项自动恢复X关注者列表，以便 [向他们发送私信](../send/twitter.md#direct-tw-messages). 同步由执行 [专门的技术工作流](#synchro-tw-accounts).

1. 在X应用程序中，复制 **API密钥** 和 **[API密钥密钥]** 字段并将它们粘贴到 **[!UICONTROL Consumer key]** 和 **[!UICONTROL Consumer secret]** 活动字段 **twitter** 服务。

1. 在X应用程序中，复制 **访问令牌** 和 **访问令牌密码** 字段并将它们粘贴到 **[!UICONTROL Access token]** 和 **[!UICONTROL Access token secret]** 活动字段 **twitter** 服务。

1. 在Campaign客户端控制台中，单击 **[!UICONTROL Save]**. 您现在已向Adobe Campaign委派了写入权限。

要检查您的设置，您可以：

* 编辑 **twitter** 您刚刚创建的服务。
* 浏览 **[!UICONTROL Twitter page]** 选项卡：应显示您的Twitter帐户。
  ![](assets/tw-page.png)

## 同步您的X帐户 {#synchro-tw-accounts}

Campaign和X之间的同步通过专门的技术工作流进行管理。 这些工作流存储在中 **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** 文件夹。

默认情况下，这些调用将停止：当您开始使用时，必须手动启动它们 **社交媒体营销** 模块。

此 **[!UICONTROL Synchronization of Twitter accounts]** 技术工作流在Adobe Campaign中同步X帐户。 此工作流可恢复X关注者的列表，以便您可以向他们发送私信。 [了解详情](../send/twitter.md#direct-tw-messages)

默认情况下，此工作流于每星期四早上7:30触发。 您可以使用 **[!UICONTROL Execute pending task(s) now]** 选项，用于在实施此集成时随时启动工作流。  您还可以编辑调度程序以更改工作流触发频率。 请参阅[此页面](../../automation/workflow/scheduler.md)以了解详情。

>[!CAUTION]
>
>要恢复X个订户的列表， **[!UICONTROL Twitter account synchronization]** 对于链接到帐户的服务，必须选中选项。 [了解详情](#create-tw-service)

跟随者存储在特定表中：访客表。 要显示X跟随者列表，请浏览至 **[!UICONTROL Profiles and Targets > Visitors]**.

对于每个关注者，Adobe Campaign都会存储以下信息：

* **[!UICONTROL Origin]**：Twitter
* **[!UICONTROL External ID]**：用户标识符
* **[!UICONTROL Username]**：用户的帐户名称
* **[!UICONTROL Full name]**：用户的名称
* **[!UICONTROL Number of friends]**：关注者数
* **[!UICONTROL Checked]**：此字段指示用户是否具有已验证的Twitter帐户

完成此配置后，您可以在X帐户上创建帖子，并向关注者发送私信。 [了解详情](../send/twitter.md)

## 在X上创建测试帐户 {#tw-test-account}

除了X帐户，请创建一个用于发送的专用X帐户 [tweet验证](../send/twitter.md#send-tw-proofs). 为此请执行以下操作步骤：

1. 创建新的X帐户。
1. 访问帐户  **设置**.
1. 浏览至 **隐私和安全** 和 **受众和标记** 并查看 **Protect您的帖子** 选项。 您的帖子和其他帐户信息仅对关注您的用户可见。

![](assets/do-not-localize/social_tw_test_page.png)

如上所述，配置您的X应用程序和Campaign服务以使其与此测试帐户配合使用。
