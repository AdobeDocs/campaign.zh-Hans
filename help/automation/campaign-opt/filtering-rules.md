---
product: campaign
title: 配置筛选规则
description: 了解如何配置筛选规则
feature: Typology Rules
exl-id: 17507cdf-211f-4fa2-abb9-33d4f6dc47bb
source-git-commit: 1fb93efac4fee4965213f8b42f518f2c10638e20
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---

# 筛选规则{#filtering-rules}

使用过滤规则，根据查询中定义的条件选择要排除的消息。 这些规则链接到定向维度。

筛选规则可以链接到其他类型的规则（控制、压力等） 分类中进行分类，或分组到专用的&#x200B;**筛选**&#x200B;分类中。 [了解详情](#create-and-use-a-filtering-typology)。

## 创建筛选规则 {#create-a-filtering-rule}

例如，您可以筛选新闻稿订阅者，以阻止将通信发送给未成年的收件人。

要定义此过滤器，请应用以下步骤：

1. 浏览到Campaign导出器的&#x200B;**[!UICONTROL Administration > Campaign management > Typology management > Typology rules]**&#x200B;文件夹，然后单击&#x200B;**新建**&#x200B;图标以创建分类规则。
1. 创建适用于所有渠道的&#x200B;**[!UICONTROL Filtering]**&#x200B;分类规则。

   ![](assets/campaign_opt_create_filter_01.png)

1. 从&#x200B;**筛选器**&#x200B;选项卡将默认定向维度更改为&#x200B;**订阅** (**nms：subscription**)。

   ![](assets/campaign_opt_create_filter_02.png)

1. 使用&#x200B;**[!UICONTROL Edit the query from the targeting dimension...]**&#x200B;链接创建筛选器。

   ![](assets/campaign_opt_create_filter_03.png)

1. 筛选收件人年龄并保存筛选条件。

   ![](assets/campaign_opt_create_filter_03b.png)

1. 从&#x200B;**分类**&#x200B;选项卡，将此规则链接到营销活动分类并保存。

   ![](assets/campaign_opt_create_filter_04.png)

在投放中使用此规则时，将自动排除未成年订阅者。 一条特定消息指示何时应用规则：

![](assets/campaign_opt_create_filter_05.png)

## 为筛选规则设置条件 {#condition-a-filtering-rule}

您可以根据链接的投放或投放大纲限制筛选规则的应用程序字段。

为此，请转到分类规则的&#x200B;**[!UICONTROL General]**&#x200B;选项卡，选择要应用的限制类型并创建过滤器。
<!--
![](assets/campaign_opt_create_filter_06.png)
-->


在这种情况下，即使该规则链接到所有投放，它也只应用于与所定义过滤器的条件匹配的投放。

>[!NOTE]
>
>可在工作流的&#x200B;**[!UICONTROL Delivery outline]**&#x200B;活动中使用分类和筛选规则。 [了解详情](../workflow/delivery-outline.md)。

## 创建和使用过滤类型 {#create-and-use-a-filtering-typology}

您可以创建&#x200B;**[!UICONTROL Filtering]**&#x200B;分类：它们仅包含筛选规则。

![](assets/campaign_opt_create_typo_filtering.png)

选择目标后，这些特定分类可以链接到投放：在投放向导中，单击&#x200B;**[!UICONTROL To]**&#x200B;链接，然后单击&#x200B;**[!UICONTROL Exclusions]**&#x200B;选项卡。

![](assets/campaign_opt_apply_typo_filtering.png)

然后，选择要应用于投放的筛选类型。 为此，请单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮并选择要应用的分类。

您还可以通过此选项卡直接链接筛选规则，而无需将它们分组到分类中。 要实现此目的，请使用窗口的下半部分。

![](assets/campaign_opt_select_typo_filtering.png)

>[!NOTE]
>
>只有类型和筛选规则在选择窗口中可用。
>
>这些配置可以在投放模板中定义，以自动应用于使用该模板创建的所有新投放。
>

## 默认可投放性排除规则 {#default-deliverability-exclusion-rules}

默认情况下，有两个筛选规则可用： **[!UICONTROL Exclude addresses]** ( **[!UICONTROL addressExclusions]** )和&#x200B;**[!UICONTROL Exclude domains]** ( **[!UICONTROL domainExclusions]** )。 在电子邮件分析期间，这些规则将收件人电子邮件地址与包含在可投放性实例中管理的加密全局禁止列表中的禁止地址或域名进行比较。 如果存在匹配项，则不会将该消息发送给该收件人。

列入阻止列表这是为了避免由于恶意活动（特别是使用Spamtrap）而添加到。 列入阻止列表例如，如果使用Spamtrap通过某个Web窗体进行订阅，则会自动向该Spamtrap发送确认电子邮件，这会导致您的地址自动添加到中。

>[!NOTE]
>
>全局隐藏列表中包含的地址和域名是隐藏的。 投放分析日志中仅指示排除的收件人的数量。
