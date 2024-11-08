---
title: 创建您的第一个投放
description: 创建您的第一个投放
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 55b752713a29c035680dd39e42422b1743e15269
workflow-type: tm+mt
source-wordcount: '1525'
ht-degree: 3%

---

# 创建您的第一个投放 {#create-a-msg}

在本页面中，您将了解如何创建一次性投放。 您可以创建其他类型的投放以解决您的用例。 在[此页面](gs-message.md)中进一步了解不同类型的投放以及如何创建它们。

创建一次性投放的关键步骤包括：

1. **创建新投放**。 [了解更多信息](#create-the-delivery)

1. **定义投放内容**。 [了解更多信息](#content-of-the-delivery)

1. **选择目标群体**。 [了解更多信息](#target-population)

然后，您可以使用Adobe Campaign准备、测试、发送和监控消息。

>[!NOTE]
>
>本节中介绍的步骤假定所有目标收件人及其用户档案都存储在数据库中，外部投放除外。 请参阅[选择外部收件人](#selecting-external-recipients)。

## 创建投放 {#create-the-delivery}

要创建投放，请执行以下步骤：

1. 浏览到投放列表并单击&#x200B;**[!UICONTROL Create]**。
1. 选择投放渠道。 要实现此目的，请从下拉列表中选择相应的投放模板。

   ![](../send/assets/select-the-new-template.png)

   为您安装的每个渠道提供了一个内置模板：电子邮件、电话、移动渠道（推送/短信）、直邮、X(Twitter)等。 列表中可用的渠道取决于您的许可协议。

   您可以创建新的投放模板，以预配置特定参数以满足您的需求。  [了解详情](../send/create-templates.md)。

1. 在&#x200B;**[!UICONTROL Label]**&#x200B;字段中输入投放名称。

   （可选）您还可以为投放分配投放代码。 投放的名称及其代码在投放列表中可见，但不会向收件人公开。

1. （可选）在&#x200B;**[!UICONTROL Description]**&#x200B;字段中添加描述。
1. （可选）在相关字段中选择投放性质。 此信息对于投放跟踪很有用：您可以在投放列表中根据此标准进行筛选，或使用此选择标准构建查询。
1. 单击&#x200B;**[!UICONTROL Continue]**&#x200B;以显示消息内容窗口。

## 定义投放内容 {#content-of-the-delivery}

投放内容已准备好进行配置。 投放内容定义特定于每个渠道。 有关更多信息，请参阅专述章节：

* [定义电子邮件的内容](../send/email.md)
* [定义短信内容](../send/sms/sms-content.md)
* [定义直邮内容](../send/direct-mail.md)
* [定义推送通知内容](../send/push.md)


## 定义目标受众 {#target-population}

对于每个投放，您可以定义几种类型的目标受众：

* **主要受众**：接收消息的用户档案。 [了解详情](#select-the-main-target)
* **验证目标**：接收验证邮件的用户档案。 利用校样这种特定的消息，可在将消息发送到主目标之前对消息进行测试。[了解详情](#select-the-proof-target)

此外，在营销活动上下文中，您可以添加：

* **种子地址**：不在投放目标中但接收投放的收件人。 [了解详情](../audiences/test-profiles.md)
* **对照组**：未接收投放的群体，用于跟踪行为和营销活动影响。 [了解详情](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group)。

### 选择投放的主要收件人 {#select-the-main-target}

在大多数情况下，主目标会从Adobe Campaign数据库（默认模式）中提取。 但是，收件人也可以存储在[外部文件](#selecting-external-recipients)中。

要选择投放的收件人，请执行以下步骤：

1. 在投放编辑器中，选择&#x200B;**[!UICONTROL To]**。
1. 如果收件人存储在数据库中，请选择第一个选项。

   ![](../send/sms/assets/audience_to.png){zoomable="yes"}

1. 在&#x200B;**[!UICONTROL Target mapping]**&#x200B;下拉列表中选择[目标映射](../audiences/target-mappings.md)。
1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮以定义限制筛选器。

   ![](assets/target-type.png){width="60%" align="left" zoomable="yes"}

   选择筛选器类型并单击&#x200B;**[!UICONTROL Next]**&#x200B;以定义条件。 您可以从&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡中显示筛选的收件人。 根据目标的类型，**[!UICONTROL Refine target]**&#x200B;按钮允许您组合多个定位条件。

   可以使用以下目标类型：

   * **[!UICONTROL Filtering conditions]**：使用此选项定义查询并显示结果。 在[本节](../../automation/workflow/query.md)中了解如何设计查询。
   * **[!UICONTROL A list of recipients]**：使用此选项来定位配置文件列表。 在[本节](../audiences/create-audiences.md)中了解更多有关列表的信息。
   * **[!UICONTROL A recipient]**：使用此选项选择数据库中的特定配置文件。
   * **[!UICONTROL Recipients included in a folder]**：使用此选项以特定文件夹中包含的所有配置文件为目标。
   * **[!UICONTROL Recipients of a delivery]**：使用此选项从投放的收件人生成目标。 然后，您必须在列表中选择投放：

     ![](assets/target-recipient-delivery.png)

   * **[!UICONTROL Delivery recipients belonging to a folder]**：使用此选项从特定文件夹中包含的收件人投放生成目标。

     ![](assets/target-delivery-folder.png)

     您可以从下拉列表中选择，以筛选收件人的行为：

     ![](assets/target-filter-behavior.png)

     >[!NOTE]
     >
     >**[!UICONTROL Include sub-folders]**&#x200B;选项还允许您定位所选节点下位于树结构中的文件夹中所包含的投放。

   * **[!UICONTROL Subscribers of an information service]** ：通过此选项，可选择新闻稿，收件人必须订阅新闻稿才能成为所创建投放的目标。

     ![](assets/target-service.png)

   * **[!UICONTROL User filters]**：通过此选项可访问预配置的筛选器，以将其用作数据库中用户档案的筛选条件。 预配置的筛选器显示在[此部分](../audiences/create-filters.md#default-filters)中。
   * 通过&#x200B;**[!UICONTROL Exclude recipients from this segment]**&#x200B;选项，可定向不符合所规定目标条件的收件人。 要使用此选项，请选择相应的框，然后按照之前的定义应用定位以排除生成的配置文件。

1. 在&#x200B;**[!UICONTROL Label]**&#x200B;字段中输入此目标的名称。 默认情况下，标签是第一个定位标准的标签。 在组合筛选条件时，建议使用显式名称。
1. 单击&#x200B;**[!UICONTROL Finish]**&#x200B;以验证定位选项。

   定义的目标标准在主目标配置选项卡的中心部分中进行了摘要。 单击条件可查看其内容（配置和预览）。 要删除某个条件，请单击其标签后面的十字线。

   ![](assets/target-remove-criterion.png)

### 选择外部收件人 {#selecting-external-recipients}

您可以向未存储在数据库中、但存储在外部文件中的用户档案发送消息。 例如，要将投放发送给从文本文件导入的收件人，请执行以下步骤：

1. 单击&#x200B;**[!UICONTROL To]**&#x200B;链接以选择投放的收件人。
1. 选择&#x200B;**[!UICONTROL Defined in an external file]**&#x200B;选项。
1. 选择包含收件人的文件。
1. 导入收件人时，单击&#x200B;**[!UICONTROL File format definition...]**&#x200B;链接以选择和配置外部文件。

   有关数据导入的详细信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/en/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs#step-2---source-file-selection){target="_blank"}。

1. 单击&#x200B;**[!UICONTROL Finish]**&#x200B;并将您的投放配置为标准投放。

>[!CAUTION]
>
>定义发送给外部收件人的电子邮件投放的内容时，不要包含指向镜像页面的链接：此投放模式无法生成该链接。

### 排除设置 {#define-exclusion-settings}

定义投放](#target-population)的[受众时，**[!UICONTROL Exclusions]**&#x200B;选项卡用于限制消息数量。 建议使用默认参数，但您可以根据需要调整设置。 但是，这些选项只应由专家用户更改，以避免任何误用和错误。

>[!CAUTION]
>
>作为专家级用户，对于特定用例，您可以更改这些设置，但Adobe建议保留默认配置。

您可以排除已达到一定数量的连续错误或其质量等级低于此窗口中指定的阈值的地址。 您还可以选择是否授权未返回数据的非限定地址。

要修改默认配置，请单击&#x200B;**[!UICONTROL Edit...]**&#x200B;链接。

![](assets/target-exclusion-settings.png)

+++ 查看可用选项

* **[!UICONTROL Exclude duplicate addresses during delivery]**：此选项默认处于活动状态，在传递期间会删除重复的电子邮件地址。 所应用的策略可能会因如何使用Adobe Campaign以及数据库中的数据类型而有所不同。 可以为每个投放模板配置选项的值。
* 列入阻止列表 **[!UICONTROL Exclude recipients who no longer want to be contacted]** ，即电子邮件地址处于状态（“选择退出”）的收件人。 为了遵守电子营销的职业道德，必须继续选择此选项。
* **[!UICONTROL Exclude quarantined recipients]**：利用此选项可从目标中排除任何包含已隔离地址的用户档案。 我们强烈建议保持选中此选项。 在[本节](../send/quarantines.md)中了解有关隔离管理的更多信息。
* **[!UICONTROL Limit delivery]**&#x200B;到给定的消息数。 使用此选项可输入要发送的最大消息数。 如果目标受众超出指示的消息数，则会随机选择消息并将其应用于目标。 若要发送所有邮件，请将此值保留为“0”。
* **[!UICONTROL Keep duplicate records (same identifier)]**：此选项允许向满足多个定位条件的收件人发送多个投放。
+++


### 选择验证消息的收件人 {#select-the-proof-target}

对于电子邮件投放，您可以发送校样以验证消息内容。 通过发送校样，可检查选择退出链接、镜像页面和任何其他链接、验证消息、验证是否显示图像、检测可能存在的错误等。 您可能还希望检查您的设计和在不同设备上的渲染。

利用校样这种特定的消息，可在将消息发送给主受众之前对消息进行测试。 校样的收件人负责批准消息：呈现、内容、个性化设置、配置。

有关校样收件人和发送的更多信息，请参阅[此章节](../send/preview-and-proof.md#send-proofs)。


#### 教程视频 {#seeds-and-proofs-video}

在本视频中，您将了解如何向现有电子邮件添加种子和验证，以及如何发送该电子邮件。

>[!VIDEO](https://video.tv.adobe.com/v/333404?quality=12)

[此处](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=zh-Hans)提供了其他Campaign Classic操作方法视频。

## 准备并验证投放 {#validate-the-delivery}

创建和配置投放后，您必须先验证该投放，然后再将其发送到主目标。

操作步骤：

1. **分析投放**：此步骤允许您准备要投放的消息。 [了解详情](../send/delivery-analysis.md)。

1. **发送校样**：此步骤允许您控制内容、URL、个性化等。 [了解详情](../send/preview-and-proof.md)。

>[!IMPORTANT]
>
>每次修改消息内容后，必须执行以上&#x200B;**的两个步骤**。


## 配置和发送投放 {#configuring-and-sending-the-delivery}

访问投放参数以配置更多设置并定义消息发送方式。 您可以定义投放优先级、设置发送波次、配置重试设置并测试投放发送。 完成此配置后，您可以确认发送。 然后，将立即发送消息，或根据投放计划发送消息。

在[此页面](../send/configure-and-send.md)中了解如何配置您的投放设置。
