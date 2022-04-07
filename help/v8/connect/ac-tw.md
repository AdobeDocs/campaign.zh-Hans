---
title: 使用Campaign和Twitter
description: 了解如何将Campaign环境与Twitter集成
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 0f15112f0eec1d7cba26523adc1e88fc5d26997c
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 4%

---

# 使用Campaign和Twitter{#tw-ac-ovv}

的 **管理社交网络（社交营销）** 模块允许您通过Twitter与客户进行交互。 使用此功能可以：

* 发送消息 — 使用Adobe Campaign Social Marketing在Twitter上发布消息。 您还可以向所有关注者发送私信。

* 收集新联系人 — Adobe Campaign Social Marketing还可轻松获取新联系人：联系用户并询问他们是否希望共享其用户档案信息。 如果客户接受，Adobe Campaign会自动恢复数据，以便您进行定位营销活动，并在可能时实施跨渠道策略。

![](../assets/do-not-localize/speech.png)  作为托管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support) 将Campaign与Twitter连接。 的  **管理社交网络（社交营销）** 必须通过专用包在您的环境中安装模块。


要将Adobe Campaign配置为将推文发布到Twitter帐户，请为这些帐户委派对Adobe Campaign的写入权限。 操作步骤：

1. 创建Twitter帐户
1. 创建用于发送校样的测试Twitter帐户
1. 创建Twitter应用程序(每个Twitter帐户一个应用程序)
1. 为 **[!UICONTROL Twitter]** (每个Twitter帐户一项服务)

## 在Twitter上创建测试帐户 {#tw-test-account}

除了Twitter帐户之外，还创建一个可用于发送的专用Twitter帐户 [推文校样](../send/twitter.md#send-tw-proofs). 为此请执行以下操作步骤：

1. 创建新的Twitter帐户。
1. 访问帐户  **设置**.
1. 浏览到 **隐私和安全** 和 **受众和标记** 并检查 **Protect您的推文** 选项。 您的推文和其他帐户信息仅对关注您的人员可见。

![](assets/social_tw_test_page.png)

## 在Twitter上创建应用程序 {#create-an-app-on-twitter}

创建Twitter应用程序，以使Adobe Campaign能够将推文发布到您的Twitter帐户。  为此请执行以下操作步骤：

1. 登录到您的Twitter帐户。
1. 连接到 [Twitter开发人员门户](https://developer.twitter.com/en/apps).
1. 选择 **创建应用程序**.
1. 让Twitter助手指导您完成该过程。

   要允许Adobe Campaign将推文发布到您的帐户，请编辑到 **权限** ，然后选择 **读写** 对于 **访问** 中。 在 **设置** 选项卡，您还需要离开 **回调URL** 字段为空。

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>每个Twitter帐户需要一个应用程序。 因此，您必须创建另一个测试应用程序以将校样发送到您的测试帐户。

## 在Campaign中创建Twitter服务 {#create-tw-service}

要将您的Campaign实例与Twitter帐户关联，请创建 **Twitter** 服务和向Campaign委派写权限。

要输入设置，您必须同时访问Adobe Campaign控制台和Twitter帐户：

1. 打开 **Twitter**，从 [项目和应用程序页面](https://developer.twitter.com/en/portal/projects-and-apps)，选择之前创建的应用程序。 访问 **应用程序权限**.

   ![](assets/social_tw_service.png)

   编辑 **密钥和令牌** 选项卡来访问应用程序详细信息。

1. 在 **Adobe Campaign**，浏览到 **[!UICONTROL Profiles and targets]** ，然后选择 **[!UICONTROL Services and Subscriptions]** 链接
1. 创建新服务。
1. 选择 **[!UICONTROL Twitter]** 类型。

   >[!NOTE]
   >
   >的 **[!UICONTROL Synchronize subscriptions]** 选项：此选项会自动取回您的Twitter关注者列表，以便您能够 [发送直邮](../send/twitter.md#direct-tw-messages). 同步由 [专用技术工作流](#synchro-tw-accounts).

1. 输入服务的标签和内部名称。

   >[!CAUTION]
   >
   >的 **[!UICONTROL Internal name]** 服务的名称必须与您的Twitter帐户完全相同。

   要检查您的设置，您可以：

   * 单击 **[!UICONTROL Save]** 按钮。
   * 在服务的概述中，选择 **Twitter** 您刚刚创建的服务。
   * 浏览 **[!UICONTROL Twitter page]** 选项卡：您的Twitter帐户应会显示。

1. 默认情况下，关注者会保存在 **[!UICONTROL Visitors]** 文件夹。 您可以从 **[!UICONTROL Visitor folder]** 字段。 [了解详情](../send/twitter.md#direct-tw-messages)

1. 从您的Twitter应用程序中，复制 **[!UICONTROL Consumer Key (API Key)]** 和 **[!UICONTROL Consumer Secret (API Secret)]** 字段并粘贴到 **[!UICONTROL Consumer key]** 和 **[!UICONTROL Consumer secret]** 营销活动的字段 **Twitter** 服务。

1. 从您的Twitter应用程序中，复制 **[!UICONTROL Access Token]** 和 **[!UICONTROL Access Token Secret]** 字段并粘贴到 **[!UICONTROL Access token]** 和 **[!UICONTROL Access token secret]** 营销活动的字段 **Twitter** 服务。

1. 在Campaign客户端控制台中，单击 **[!UICONTROL Save]**. 您现在已委派对Adobe Campaign的写入权限。


>[!NOTE]
>
>创建一个 **Twitter** 每个Twitter帐户的服务。 因此，您必须创建另一个测试服务以将校样发送到您的测试帐户。

## 同步您的Twitter帐户 {#synchro-tw-accounts}

Campaign和Twitter之间的同步通过专用的技术工作流进行管理。 这些工作流存储在 **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** 文件夹。

默认情况下，会停止这些操作：在开始使用 **社交营销** 模块。

的 **[!UICONTROL Twitter account synchronization]** 技术工作流在Adobe Campaign中同步Twitter帐户。 此工作流取回了Twitter关注者列表，以便您可以向他们发送私信。 [了解详情](../send/twitter.md#direct-tw-messages)

默认情况下，此工作流于每星期四早上7:30触发。 您可以使用 **[!UICONTROL Execute pending task(s) now]** 选项，以在您实施此集成时随时启动工作流。  您还可以编辑调度程序以更改工作流触发频率。 请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}以了解详情。

>[!CAUTION]
>
>要恢复Twitter订阅者列表，请 **[!UICONTROL Twitter account synchronization]** 必须检查链接到帐户的服务的选项。 [了解详情](#create-tw-service)

关注者存储在特定表中：访客表。 要显示Twitter关注者列表，请浏览 **[!UICONTROL Profiles and Targets > Visitors]**.

对于每个关注者，Adobe Campaign会存储以下信息：

* **[!UICONTROL Origin]**:社交网络的名称(Twitter)
* **[!UICONTROL External ID]**:用户标识符
* **[!UICONTROL User name]**:用户的帐户名称
* **[!UICONTROL Full name]**:用户名称
* **[!UICONTROL Language]**:用户语言
* **[!UICONTROL Number of friends]**:关注者数量
* **[!UICONTROL Time zone]**:用户时区
* **[!UICONTROL Verified]**:此字段指示用户是否具有已验证的Twitter帐户

完成此配置后，您可以将推文发布到Twitter帐户，并向关注者发送私信。 [了解详情](../send/twitter.md)
