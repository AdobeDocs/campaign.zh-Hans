---
title: 创建您的第一个投放
description: 创建您的第一个投放
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 53fab31c21fdfe2f90c4793ccd025af1d5c0e061
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 98%

---

# 创建您的第一个投放 {#create-a-msg}

在本页面中，了解如何创建一次性投放。 您可以创建其他类型的投放以构建用例。 要进一步了解不同类型的投放以及如何创建投放，请参阅[此页面](gs-message.md)。

创建一次性投放时的关键步骤包括：

1. **创建新投放**。[了解更多信息](#create-the-delivery)

1. **定义投放内容**。[了解更多信息](#content-of-the-delivery)

1. **选择目标群体**。[了解更多信息](#target-population)

然后，您可以使用 Adobe Campaign 准备、测试、发送和监控消息。

>[!NOTE]
>
>本部分中介绍的步骤的假定前提是，所有目标收件人及其用户档案都存储在数据库中，外部投放除外。请参阅[选择外部收件人](#selecting-external-recipients)。

## 创建投放 {#create-the-delivery}

要创建投放，请执行以下步骤：

1. 导航到投放列表并单击 **[!UICONTROL Create]**。
1. 选择投放渠道。要实现此操作，请从下拉列表中选择相应的投放模板。

   ![](../send/assets/select-the-new-template.png)

   您安装的每个渠道均可使用内置模板：电子邮件、电话、移动渠道（推送/短信）、直邮、X (Twitter) 等。列表中的渠道取决于您的许可协议。

   您可以创建新的投放模板，预配置特定参数以满足您的需求。 [了解详情](../send/create-templates.md)。

1. 在 **[!UICONTROL Label]** 字段中输入投放名称。

   （可选）您还可以为投放分配投放代码。投放的名称及其代码在投放列表中可见，但不会向收件人公开。

1. （可选）在 **[!UICONTROL Description]** 字段中添加描述。
1. （可选）在相关字段中选择投放性质。此信息对于投放跟踪很有用：您可以在投放列表中根据此标准进行筛选，或使用此选择标准生成查询。
1. 单击 **[!UICONTROL Continue]** 以显示消息内容窗口。

## 定义投放内容 {#content-of-the-delivery}

投放内容已准备好进行配置。投放内容定义特定于每个渠道。有关更多信息，请参阅专门的部分：

* [定义电子邮件的内容](../send/email.md)
* [定义短信的内容](../send/sms/sms-content.md)
* [定义直邮的内容](../send/direct-mail.md)
* [定义推送通知的内容](../send/push.md)


## 定义目标受众 {#target-population}

对于每个投放，您可以定义多种类型的目标受众：

* **主要受众**：接收消息的用户档案。[了解详情](#select-the-main-target)
* **验证目标**：接收校样消息的用户档案。利用校样这种特定的消息，可在将消息发送到主目标之前对消息进行测试。[了解详情](#select-the-proof-target)

此外，在营销活动上下文中，您可以添加：

* **种子地址**：不在投放目标中但接收投放的收件人。[了解详情](../audiences/test-profiles.md)
* **对照组**：不接收投放的群体，用于跟踪行为和营销活动影响。[了解详情](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group)。

### 选择投放的主要收件人 {#select-the-main-target}

在大多数情况下，会从 Adobe Campaign 数据库中提取主要目标（默认模式）。但是，也可以在[外部文件](#selecting-external-recipients)中存储收件人。

要选择投放的收件人，请执行以下步骤：

1. 在投放编辑器中，选择 **[!UICONTROL To]**。
1. 如果收件人存储在数据库中，请选择第一个选项。

   ![](../send/sms/assets/audience_to.png){zoomable="yes"}

1. 在 **[!UICONTROL Target mapping]** 下拉列表中选择 [目标映射](../audiences/target-mappings.md)。
1. 单击 **[!UICONTROL Add]** 按钮以定义限制筛选条件。

   ![](assets/target-type.png){width="60%" align="left" zoomable="yes"}

   选择筛选类型并单击 **[!UICONTROL Next]** 以定义条件。您可以从 **[!UICONTROL Preview]** 选项卡中查看筛选的收件人。根据目标的类型，通过 **[!UICONTROL Refine target]** 按钮可以组合多个目标选择条件。

   可使用以下目标类型：

   * **[!UICONTROL Filtering conditions]**：使用此选项定义查询并显示结果。要了解如何设计查询，请参阅[此部分](../../automation/workflow/query.md)。
   * **[!UICONTROL A list of recipients]**：使用此选项来选择目标用户档案列表。要进一步了解列表，请参阅[此部分](../audiences/create-audiences.md)。
   * **[!UICONTROL A recipient]**：使用此选项以选择数据库中的特定用户档案。
   * **[!UICONTROL Recipients included in a folder]**：使用此选项以将特定文件夹中包含的所有用户档案选择为目标。
   * **[!UICONTROL Recipients of a delivery]**：使用此选项以从投放的收件人中生成目标。然后，您必须在列表中选择投放：

     ![](assets/target-recipient-delivery.png)

   * **[!UICONTROL Delivery recipients belonging to a folder]**：使用此选项可从特定文件夹中的收件人投放生成目标。

     ![](assets/target-delivery-folder.png)

     您可以从下拉列表中进行选择，以筛选收件人的行为：

     ![](assets/target-filter-behavior.png)

     >[!NOTE]
     >
     >通过 **[!UICONTROL Include sub-folders]** 选项，还可以定位所选节点下树结构中文件夹包含的投放。

   * **[!UICONTROL Subscribers of an information service]**：通过此选项，可选择新闻稿，收件人必须订阅新闻稿才能成为所创建投放的目标。

     ![](assets/target-service.png)

   * **[!UICONTROL User filters]**：通过此选项可访问预配置的筛选条件，以将其用作数据库中筛选用户档案的标准。要查看预配置的筛选条件，请参阅[此部分](../audiences/create-filters.md#default-filters)。
   * 通过 **[!UICONTROL Exclude recipients from this segment]** 选项，可将不符合定义目标条件的收件人选择为目标。要使用此选项，请选择相应的框，然后按照之前所述应用目标选择，以排除生成的用户档案。

1. 在 **[!UICONTROL Label]** 字段中输入此目标的名称。 默认情况下，标签是第一个目标选择标准的标签。在组合筛选条件时，建议使用显式名称。
1. 单击 **[!UICONTROL Finish]** 以验证目标选择选项。

   在“主要目标配置”选项卡的中心部分中概述了定义的目标选择标准。单击标准可查看其内容（配置和预览）。要删除某个标准，请单击其标签后面的十字线。

   ![](assets/target-remove-criterion.png)

### 选择外部收件人 {#selecting-external-recipients}

您可以向未存储在数据库、但存储在外部文件中的用户档案发送消息。例如，要将投放发送给从文本文件导入的收件人，请执行以下步骤：

1. 单击 **[!UICONTROL To]** 链接以选择投放的收件人。
1. 选择 **[!UICONTROL Defined in an external file]** 选项。
1. 选择包含收件人的文件。
1. 导入收件人时，单击 **[!UICONTROL File format definition...]** 链接以选择和配置外部文件。

   有关数据导入的更多信息，请参阅 [Campaign Classic v7 文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs#step-2---source-file-selection){target="_blank"}。

1. 单击 **[!UICONTROL Finish]** 并将您的投放配置为标准投放。

>[!CAUTION]
>
>定义发送给外部收件人的电子邮件投放消息内容时，不要包含指向镜像页面的链接：其此投放模式下无法生成。

### 排除设置 {#define-exclusion-settings}

定义[投放的受众](#target-population)时，可使用 **[!UICONTROL Exclusions]** 选项卡限制消息数量。建议使用默认参数，但您可以根据需要调整设置。但是，这些选项只应由专家用户更改，以避免误用和错误。

>[!CAUTION]
>
>作为专家用户，对于特定用例，您可以更改这些设置，但 Adobe 建议保留默认配置。

您可以排除已达到一定连续错误数或质量评级低于此窗口中指定阈值的地址。您还可以选择是否授权未返回数据的不符合条件的地址。

要修改默认配置，请单击 **[!UICONTROL Edit...]** 链接。

![](assets/target-exclusion-settings.png)

+++ 查看可用选项

* **[!UICONTROL Exclude duplicate addresses during delivery]**：此选项默认处于启用状态，在投放期间会移除重复的电子邮件地址。所应用的策略可能会因使用 Adobe Campaign 的方式以及数据库中的数据类型而有所不同。可以为每个投放模板配置选项的值。
* **[!UICONTROL Exclude recipients who no longer want to be contacted]**，即电子邮件地址处于拒绝列表状态（选择退出）的收件人。为遵守电子营销的职业道德，必须保留选择此选项。
* **[!UICONTROL Exclude quarantined recipients]**：通过此选项可从目标中排除隔离地址的用户档案。我们强烈建议保持选中此选项。要进一步了解隔离管理，请参阅[此部分](../send/quarantines.md)。
* 给定消息数的 **[!UICONTROL Limit delivery]**。使用此选项可输入要发送的最大消息数。如果目标受众超出指定的消息数，则会对目标进行随机选择。要发送所有消息，请将此值保留为“0”。
* **[!UICONTROL Keep duplicate records (same identifier)]**：通过此选项可向满足多个目标选择条件的收件人发送多个投放。
+++


### 选择校样消息的收件人 {#select-the-proof-target}

对于电子邮件投放，您可以发送校样以验证消息内容。通过发送校样，可检查选择退出链接、镜像页面和任何其他链接、验证消息、验证是否显示图像、检测可能存在的错误等。您可能还希望检查设计和在不同设备上的呈现效果。

利用校样这种特定的消息，可在将消息发送给主要受众之前对消息进行测试。校样的收件人负责审阅消息：呈现效果、内容、个性化设置和配置。

有关校样收件人和发送校样的更多信息，请参阅[此部分](../send/preview-and-proof.md#send-proofs)。


#### 教程视频 {#seeds-and-proofs-video}

在本视频中，您将了解如何向现有电子邮件添加种子和校样，以及如何进行发送。

>[!VIDEO](https://video.tv.adobe.com/v/333404?quality=12)

[此处](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=zh-Hans)提供了其他 Campaign Classic 操作方法视频。

## 准备并验证投放 {#validate-the-delivery}

创建和配置投放后，您必须先验证该投放，然后再将其发送给主要目标。

操作步骤：

1. **分析投放**：通过此步骤可准备要投放的消息。[了解详情](../send/delivery-analysis.md)。

1. **发送校样**：通过此步骤可控制内容、URL、个性化等。[了解详情](../send/preview-and-proof.md)。

>[!IMPORTANT]
>
>每次修改消息内容后，**必须**&#x200B;执行以上两个步骤。


## 配置和发送投放 {#configuring-and-sending-the-delivery}

访问投放参数以配置更多设置并定义消息发送方式。您可以定义投放优先级、设置发送波次、配置重试设置并测试投放发送。完成此配置后，您可以确认发送。然后，消息将即时发送，或根据投放计划进行发送。

要了解如何配置投放设置，请参阅[此页面](../send/configure-and-send.md)。
