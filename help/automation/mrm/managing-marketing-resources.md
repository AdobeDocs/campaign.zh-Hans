---
product: campaign
title: 管理营销资源
description: 了解如何管理营销资源
feature: Campaigns, Resource Management
role: User
exl-id: 4d91fb7d-f846-4644-b83d-5a6a988ae297
source-git-commit: c3f4ad0b56dd45d19eebaa4d2f06551c8fecac1d
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 1%

---

# 管理营销资源{#managing-marketing-resources}

使用Adobe Campaign管理和跟踪活动生命周期中涉及的营销资源。 这些营销资源可以是白皮书、数据文件、徽标或任何其他与活动相关的资产。

对于通过Adobe Campaign管理的每个营销资源，您可以随时跟踪其状态和历史记录，并查看当前版本。

默认情况下，营销资源存储在Campaign资源管理器的&#x200B;**[!UICONTROL MRM > Marketing resources]**&#x200B;文件夹中。

## 添加营销资源 {#adding-a-marketing-resource}

要添加营销资源，请执行以下步骤：

1. 浏览到&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡，然后选择&#x200B;**[!UICONTROL Marketing resouces]**。

1. 单击 **[!UICONTROL Create]** 按钮。
   ![](assets/add-a-mkt-resource.png)
1. 将该文件拖放到“营销资源”窗口中，以将其上传到Campaign服务器。 您还可以使用&#x200B;**[!UICONTROL Upload file to server...]**链接。
   ![](assets/mkt-resource-creation.png)

上传完成后，资源将添加到可用资源列表中。

## 管理营销资源 {#manage-marketing-resources}

上传后，所有Adobe Campaign操作员都可以使用营销资源。 他们可以查看、制作副本以对其进行修改，或更新服务器上的文件。

![](assets/open-a-marketing-resource.png)

使用&#x200B;**[!UICONTROL Edit]**&#x200B;选项卡中的&#x200B;**[!UICONTROL Assigned to]**&#x200B;下拉列表选择负责该资源的运算符。

![](assets/assign-a-mkt-resource.png)

您还可以选择负责资源验证和资源发布的操作员或操作员组。 要访问这些选项，请单击&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;链接。

启动资源验证过程后，将通过电子邮件通知这些操作员。

如果未选择审阅者，则资源&#x200B;**[!UICONTROL cannot be]**&#x200B;需要批准。

使用&#x200B;**[!UICONTROL Audit]**&#x200B;选项卡添加验证读取器并定义资源的可用日期。 在此日期之后，将显示为&#x200B;**[!UICONTROL Late]**&#x200B;状态。

>[!NOTE]
>
>**[!UICONTROL History]**&#x200B;选项卡包含资源的下载和更新日志。 使用&#x200B;**[!UICONTROL Details]**&#x200B;按钮可以查看所选版本。
>
>通过&#x200B;**[!UICONTROL Audit]**&#x200B;选项卡，可监视对资源执行的任何操作：批准、拒绝审批、相关评论或发布。

### 锁定/解锁资源 {#locking-unlocking-a-resource}

创建后，营销资源功能板中提供了资源，操作员可以编辑和修改这些资源。

当操作员开始使用某个资源时，最佳做法是锁定该资源，以防止其他操作员同时修改该资源。 然后保留资源：该资源仍可访问，但无法由其他操作员在服务器上发布或更新。

仅当营销资源未获批准时，才能锁定该资源。

要锁定资源，必须单击资源仪表板中的&#x200B;**[!UICONTROL Lock]**&#x200B;按钮。

![](assets/lock-a-resource.png)


更新资源后，单击资源仪表板中的&#x200B;**[!UICONTROL Lock]**&#x200B;按钮以再次对所有操作员可用。

一条特殊消息会通知尝试访问它的任何操作员：

![](assets/mkt-resource-locked.png)

**[!UICONTROL Tracking]**&#x200B;选项卡指示锁定资源的操作员的姓名。

![](assets/mkt-resource-audit-tab.png)


>[!NOTE]
>
>只有锁定资源的操作员和具有管理员权限的操作员才有权解锁资源。

### 论坛 {#discussion-forums}

对于每个资源，**[!UICONTROL Forum]**&#x200B;选项卡允许参与者共享信息。

![](assets/mkt-resource-forum.png)

在[论坛](discussion-forums.md)部分了解详情。

### 审批流程 {#approval-process}

如果在&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡中指定了预期可用日期，则该日期会显示在资源详细信息中。 达到此日期后，您可以使用资源仪表板中的&#x200B;**[!UICONTROL Submit for approval]**&#x200B;按钮执行审批流程。 然后，资源状态更改为&#x200B;**[!UICONTROL Approval in progress]**。

要批准资源，请单击其仪表板上的&#x200B;**[!UICONTROL Approve the resource]**&#x200B;按钮。

![](assets/mkt-resouce-approve.png)

授权操作员随后可以接受或拒绝批准。 此操作可通过以下方式执行：通过发送的电子邮件（单击通知消息中的链接），或通过客户端控制台（单击&#x200B;**[!UICONTROL Approve]** ）按钮。

您可以在批准窗口中输入备注。

![](assets/mkt-resource-approval-confirmation.png)

浏览到&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡以检查审批。

>[!NOTE]
>
>除了为每个营销资源指定的审阅者之外，具有管理员权限的操作员和资源管理器也被授权审批营销资源。

### Publish资源 {#publishing-a-resource}

获得批准后，必须发布营销资源。 发布过程必须按照公司要求具体实施。 这意味着可在外联网或任何其他服务器上发布资源，可向外部服务提供商发送特定信息等。

要发布资源，请单击营销资源功能板编辑区域中的&#x200B;**[!UICONTROL Publish]**&#x200B;按钮。

![](assets/mkt-resource-publish.png)

您还可以通过工作流自动发布资源。

发布资源意味着使其可用（例如，供其他任务使用）。 发布方式因资源的性质而异：对于传单，发布可能意味着将文件发送到打印机，对于Web代理，发布可能意味着将文件发布到网站等。

为了发布Adobe Campaign，您需要创建一个足够的工作流并将其链接到资源。 为此，请打开资源的&#x200B;**[!UICONTROL Advanced settings...]**&#x200B;框，然后在&#x200B;**[!UICONTROL Post-processing]**&#x200B;字段中选择所需的工作流。

![](assets/mkt-resource-post-processing-wf.png)

工作流将执行：

* 当审核者单击&#x200B;**[!UICONTROL Publish resource]**&#x200B;链接时（或者，如果未定义审核者，则为负责资源的人员）。
* 如果资源是通过营销资源创建任务管理的，则只要在任务中勾选&#x200B;**[!UICONTROL Publish the marketing resource]**&#x200B;框，该资源就会在任务设置为&#x200B;**[!UICONTROL Finished]**&#x200B;时执行。 [了解详情](creating-and-managing-tasks.md#marketing-resource-creation-task))

如果未立即启动工作流（如果实例停止了工作流），则资源的状态将更改为&#x200B;**[!UICONTROL Pending publication]**。 工作流启动后，资源的状态将更改为&#x200B;**[!UICONTROL Published]**。 此状态不考虑发布过程中可能出现的错误。 检查工作流的状态，确保工作流已正确执行。

## 将资源链接到营销策划 {#linking-a-resource-to-a-campaign}

### 引用营销资源 {#referencing-a-marketing-resource}

营销资源可以与营销活动相关联，前提是已在[营销活动模板](../campaigns/marketing-campaign-templates.md)中选择此功能。

浏览到Campaign仪表板中的&#x200B;**[!UICONTROL Edit > Documents > Resources]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Add]**&#x200B;以选择相关资源。

![](assets/link-a-mkt-resource-to-a-campaign.png)

您可以按状态、性质或类型过滤资源，或应用个性化过滤器。

使用&#x200B;**[!UICONTROL Details]**&#x200B;按钮编辑和预览资源。

### 将营销资源添加到投放大纲 {#adding-a-marketing-resource-to-a-delivery-outline}

营销资源可以通过投放大纲与投放相关联。

在[本节](../campaigns/marketing-campaign-deliveries.md)中了解有关投放概要的更多信息。

为此，请右键单击投放概要，然后选择&#x200B;**新建>资源**。

![](assets/mkt-resource-add-in-del-outline.png)

输入资源的名称，然后从&#x200B;**营销资源**&#x200B;下拉列表中选择该资源。

![](assets/mkt-resource-select-in-del-outline.png)


## 库存管理 {#stock-management}

您可以将营销资源与一个或多个库存相关联，以便管理供应并在库存不足时在控制面板上显示警告。


要将营销资源与股票相关联，请执行以下步骤：

1. 编辑股票或创建新股票。 在[本节](../campaigns/providers-stocks-and-budgets.md#stock-management)中了解有关股票的更多信息。

1. 添加库存行，然后选择相应的营销资源。

   ![](assets/mkt-resource-in-a-stock-line.png)

   选择所选资源后，您可以通过位于该资源右侧的&#x200B;**[!UICONTROL Edit the link]**&#x200B;图标来编辑该资源。

1. 指定初始库存和警报库存，然后保存。

股票在营销资源&#x200B;**股票**&#x200B;选项卡中指明。
