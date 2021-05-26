---
solution: Campaign v8
product: Adobe Campaign
title: 在Campaign中管理订阅和退订
description: 了解如何在Campaign v8中管理订阅和退订
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# 管理订阅和退订{#optin-optout}

使用Adobe Campaign创建并监控新闻稿等信息服务，并管理这些服务的订阅/退订。 可以并行定义多项服务，例如：针对某些产品类别、主题或网站区域的专业通讯、订阅各种类型的警报消息和实时通知。 请参阅管理订阅。

[!DNL :arrow_upper_right:] 在Campaign Classicv7文档中了解如何创建信息服务、发送新闻稿以及管理选择加入和 [选择退出](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html)

要将配置文件订阅（选择加入）到服务，可用选项包括：

* 手动将服务添加到收件人用户档案：为此，请从其配置文件的&#x200B;**[!UICONTROL Subscriptions]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Add]**&#x200B;并选择相关的信息服务。

   [!DNL :arrow_upper_right:] 在Campaign Classicv7文 [档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)

* 自动为一组收件人订阅服务。 收件人列表可以来自筛选操作、组、文件夹、导入或直接手动选择。 要订阅这些收件人，请选择用户档案并右键单击。 选择&#x200B;**[!UICONTROL Actions > Subscribe selection to a service...]**，选择相关服务，然后开始操作。

   [!DNL :arrow_upper_right:] 在Campaign Classicv7文 [档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)


* 导入收件人并自动订阅信息服务。 要执行此操作，请在导入向导的最后一步中选择相关服务。

   [!DNL :arrow_upper_right:] 在Campaign Classicv7文 [档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients)

* 使用Web窗体，以便收件人订阅服务。

   [!DNL :arrow_upper_right:] 在Campaign Classicv7文 [档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in)


* 创建定位工作流并使用&#x200B;**[!UICONTROL Subscription service]**&#x200B;活动。

   [!DNL :arrow_upper_right:] 在Campaign Classicv7文 [档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter)


要取消订阅（选择退订）服务中的用户档案，可用选项包括：

**手动退订**

* 个性化退订链接或Web窗体
* 手动删除信息服务
* 从特定订阅服务手动删除收件人

**自动退订**

* 指定信息服务的持续时间限制：有效期届满后，收件人将自动取消订阅。 此时段在服务属性的编辑选项卡中指定。 以天表示。
* 为群体设置退订工作流

[!DNL :arrow_upper_right:] 在Campaign Classicv7文 [档中了解详情](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service)


>[!CAUTION]
>
>订阅和取消订阅是&#x200B;**异步**&#x200B;进程。 选择加入和选择退出请求每小时进行处理。 [了解详情](../dev/new-apis.md#sub-apis)

您还可以让投放收件人将邮件转发给朋友。 为此，请将相关链接插入到投放中。 然后，您可以跟踪此共享过程以及相关页面的访问次数。

[!DNL :arrow_upper_right:] 有关此功能的更多信息，请参 [阅Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend)。