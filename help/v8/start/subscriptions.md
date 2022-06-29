---
title: 在Campaign中管理订阅和退订
description: 了解如何在Campaign v8中管理订阅和退订
feature: Subscriptions
role: Data Engineer
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: c6a234f6c43531be032354d134e4745ad77cbcc7
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 10%

---

# 管理订阅和退订{#optin-optout}

使用Adobe Campaign创建并监控新闻稿等信息服务，并管理这些服务的订阅/退订。 可以并行定义多项服务，例如：针对某些产品类别、主题或网站区域的专业通讯、订阅各种类型的警报消息和实时通知。 请参阅管理订阅。

![](../assets/do-not-localize/book.png) 了解如何创建信息服务、发送新闻稿以及管理选择加入和选择退出 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target=&quot;_blank&quot;}

要将配置文件订阅（选择加入）到服务，可用选项包括：

* 手动将服务添加到收件人用户档案：为此，从 **[!UICONTROL Subscriptions]** 选项卡，单击 **[!UICONTROL Add]** 选择相关信息服务。

   ![](assets/subscribe-to-a-service.png)

   ![](../assets/do-not-localize/book.png)请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab) {target=&quot;_blank&quot;} 以了解详情。

* 自动为一组收件人订阅服务。 收件人列表可以来自筛选操作、组、文件夹、导入或直接手动选择。 要订阅这些收件人，请选择用户档案并右键单击。 选择 **[!UICONTROL Actions > Subscribe selection to a service...]**。

   ![](assets/subscribe-selection.png)

   选择相关服务，然后启动操作。

   ![](assets/subscribe-confirm.png)

   ![](../assets/do-not-localize/book.png)请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab) {target=&quot;_blank&quot;} 以了解详情。


* 导入收件人并自动订阅信息服务。 要执行此操作，请在导入向导的最后一步中选择相关服务。

   ![](../assets/do-not-localize/book.png)请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients) {target=&quot;_blank&quot;} 以了解详情。

* 使用Web窗体，以便收件人订阅服务。

   ![](assets/opt-in-webapp.png)

   Campaign附带一个用于管理选择加入的默认Web窗体。 您可以对其进行个性化设置并映射用户档案数据。

   ![](assets/web-app.png)

   ![](../assets/do-not-localize/book.png)请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in) {target=&quot;_blank&quot;} 以了解详情。


* 创建定位工作流并使用 **[!UICONTROL Subscription service]** 活动。

   ![](assets/wf-subscription.png)

   ![](../assets/do-not-localize/book.png)请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter) {target=&quot;_blank&quot;} 以了解详情。

要取消订阅（选择退订）服务中的用户档案，可用选项包括：

**手动退订**

* 个性化退订链接或Web窗体
* 手动删除信息服务
* 从特定订阅服务手动删除收件人

**自动退订**

* 指定信息服务的持续时间限制：有效期届满后，收件人将自动取消订阅。 此时段在服务属性的编辑选项卡中指定。 以天表示。
* 为群体设置退订工作流。

![](../assets/do-not-localize/book.png)请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service) {target=&quot;_blank&quot;} 以了解详情。


>[!CAUTION]
>
>在 [企业(FFDA)部署](../architecture/enterprise-deployment.md)、订阅和退订 **异步** 进程。 选择加入和选择退出请求每小时进行处理。 [了解详情](../architecture/new-apis.md#sub-apis)

您还可以让投放收件人将邮件转发给朋友。 为此，请将相关链接插入到投放中。 然后，您可以跟踪此共享过程以及相关页面的访问次数。

![](../assets/do-not-localize/book.png) 有关此功能的更多信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend){target=&quot;_blank&quot;}
