---
product: campaign
title: 管理营销资源
description: 了解如何管理营销资源
exl-id: 4d91fb7d-f846-4644-b83d-5a6a988ae297
source-git-commit: 399c81276d29622a2161c8c90395df1a38954763
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 1%

---

# 管理营销资源{#managing-marketing-resources}

使用Adobe Campaign管理和跟踪营销活动生命周期中涉及的营销资源。 这些营销资源可以是白皮书、数据文件、徽标或与营销活动相关的任何其他资产。

对于通过Adobe Campaign管理的每个营销资源，您可以随时跟踪其状态和历史记录，并查看当前版本。

默认情况下，营销资源存储在 **[!UICONTROL MRM > Marketing resources]** Campaign资源管理器的文件夹。

## 添加营销资源 {#adding-a-marketing-resource}

要添加营销资源，请执行以下步骤：

1. 浏览到 **[!UICONTROL Campaigns]** ，然后选择 **[!UICONTROL Marketing resouces]**.

1. 单击 **[!UICONTROL Create]** 按钮。
   ![](assets/add-a-mkt-resource.png)
1. 将文件拖放到营销资源窗口中，以将其上传到Campaign服务器。 您还可以使用 **[!UICONTROL Upload file to server...]** 链接。
   ![](assets/mkt-resource-creation.png)

上传完成后，资源会添加到可用资源列表。

## 管理营销资源 {#manage-marketing-resources}

上传后，营销资源便可供所有Adobe Campaign运营商使用。 他们可以查看、制作副本以对其进行修改，或更新服务器上的文件。

![](assets/open-a-marketing-resource.png)

使用 **[!UICONTROL Assigned to]** 下拉列表 **[!UICONTROL Edit]** 选项卡来选择负责该资源的操作员。

![](assets/assign-a-mkt-resource.png)

您还可以选择负责资源验证和资源发布的操作员或操作员组。 要访问这些选项，请单击  **[!UICONTROL Advanced parameters]** 链接。

启动资源验证过程后，系统会通过电子邮件通知这些运算符。

如果未选择审核者，则资源 **[!UICONTROL cannot be]** 须经批准。

使用 **[!UICONTROL Audit]** 选项卡，以添加校样读取器并定义资源的可用日期。 在此日期之后，将显示为 **[!UICONTROL Late]** 状态。

>[!NOTE]
>
>的 **[!UICONTROL History]** 选项卡包含资源的下载和更新日志。 的 **[!UICONTROL Details]** 按钮可查看所选版本。
>
>的 **[!UICONTROL Audit]** 选项卡，用于监视对资源执行的任何操作：批准、批准拒绝、相关评论或出版物。

### 锁定/解锁资源 {#locking-unlocking-a-resource}

创建资源后，即可在营销资源功能板中使用资源，操作员可以编辑和修改这些资源。

当操作员开始处理某个资源时，最佳做法是锁定该资源，以防止其他操作员同时修改该资源。 然后，将保留该资源：它仍然可以访问，但无法由其他运算符在服务器上发布或更新。

仅当营销资源未获得批准时，才能将其锁定。

要锁定资源，必须单击 **[!UICONTROL Lock]** 按钮。

![](assets/lock-a-resource.png)


更新资源后，单击 **[!UICONTROL Lock]** 按钮以再次供所有运算符使用。

系统会显示一条特殊消息，通知尝试访问该页面的所有操作员：

![](assets/mkt-resource-locked.png)

的 **[!UICONTROL Tracking]** 选项卡指示锁定资源的运算符的名称。

![](assets/mkt-resource-audit-tab.png)


>[!NOTE]
>
>只有锁定资源的操作员和具有管理员权限的操作员才有权解锁资源。

### 论坛 {#discussion-forums}

对于每个资源， **[!UICONTROL Forum]** 选项卡允许参与者共享信息。

![](assets/mkt-resource-forum.png)

在 [论坛](discussion-forums.md) 中。

### 审批流程 {#approval-process}

如果在 **[!UICONTROL Tracking]** 选项卡。 到达此日期后，您可以使用 **[!UICONTROL Submit for approval]** 按钮。 然后，资源状态将更改为 **[!UICONTROL Approval in progress]**.

要批准资源，请单击 **[!UICONTROL Approve the resource]** 按钮。

![](assets/mkt-resouce-approve.png)

然后，授权的运营商可以接受或拒绝批准。 此操作可以：（通过单击通知消息中的链接）或通过控制台(通过单击 **[!UICONTROL Approve]** )按钮。

您可以在审批窗口中输入评论。

![](assets/mkt-resource-approval-confirmation.png)

浏览到 **[!UICONTROL Tracking]** 选项卡来检查批准。

>[!NOTE]
>
>除了为每个营销资源指定的审核者之外，具有管理员权限的操作员和资源管理器也被授权批准营销资源。

### 发布资源 {#publishing-a-resource}

批准后，必须发布营销资源。 出版过程必须按照公司要求具体实施。 这意味着资源可以在外联网或任何其他服务器上发布，特定信息可以发送到外部服务提供商等。

要发布资源，请单击 **[!UICONTROL Publish]** 按钮。

![](assets/mkt-resource-publish.png)

您还可以通过工作流自动发布资源。

发布资源意味着（例如，由其他任务）使其可供使用。 根据资源的性质，发布内容会有所不同：对于传单，发布可能意味着将文件发送到打印机，对于Web代理，发布可能意味着将其发布到网站等。

要使Adobe Campaign发布，您需要创建一个适当的工作流并将其链接到资源。 为此，请打开 **[!UICONTROL Advanced settings...]** 框中，然后在 **[!UICONTROL Post-processing]** 字段。

![](assets/mkt-resource-post-processing-wf.png)

将执行工作流：

* 当审阅人单击 **[!UICONTROL Publish resource]** 链接（或者，如果未定义审核者，则为资源负责人）。
* 如果资源是通过营销资源创建任务来管理的，则在将该任务设置为 **[!UICONTROL Finished]**，只要 **[!UICONTROL Publish the marketing resource]** 框。 [了解详情](creating-and-managing-tasks.md#marketing-resource-creation-task))

如果工作流未立即启动（例如，如果工作流已停止），则资源的状态将更改为 **[!UICONTROL Pending publication]**. 启动工作流后，资源的状态将更改为 **[!UICONTROL Published]**. 此状态未考虑发布过程中可能出现的错误。 检查工作流的状态，确保工作流已正确执行。

## 将资源链接到营销活动 {#linking-a-resource-to-a-campaign}

### 引用营销资源 {#referencing-a-marketing-resource}

营销资源可以与营销活动关联，前提是在 [活动模板](../campaigns/marketing-campaign-templates.md).

浏览到 **[!UICONTROL Edit > Documents > Resources]** 选项卡，然后单击 **[!UICONTROL Add]** 选择相关资源。

![](assets/link-a-mkt-resource-to-a-campaign.png)

您可以按状态、自然或类型筛选资源，也可以应用个性化筛选器。

使用 **[!UICONTROL Details]** 按钮以编辑和预览资源。

### 向投放大纲添加营销资源 {#adding-a-marketing-resource-to-a-delivery-outline}

营销资源可以通过投放大纲与投放相关联。

了解有关 [此部分](../campaigns/marketing-campaign-deliveries.md).

要执行此操作，请右键单击投放大纲并选择 **新建>资源**.

![](assets/mkt-resource-add-in-del-outline.png)

输入资产的名称，然后从 **营销资源** 下拉列表。

![](assets/mkt-resource-select-in-del-outline.png)


## 库存管理 {#stock-management}

您可以将营销资源与一个或多个库存关联，以便管理您的供应，并在库存不足时在仪表板上显示警告。


要将营销资源与库存关联，请执行以下步骤：

1. 编辑库或创建新库。 了解有关 [此部分](../campaigns/providers--stocks-and-budgets.md#stock-management).

1. 添加库存行，然后选择相应的营销资源。

   ![](assets/mkt-resource-in-a-stock-line.png)

   您可以通过 **[!UICONTROL Edit the link]** 图标（在选择资源右侧）。

1. 指定初始库存和警报库存，然后保存。

库存在营销资源中指示 **股票** 选项卡。
