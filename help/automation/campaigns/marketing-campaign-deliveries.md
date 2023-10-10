---
product: campaign
title: 营销活动投放
description: 了解有关营销活动投放的更多信息
feature: Campaigns, Resource Management, Cross Channel Orchestration
role: User
exl-id: 1d9638cb-0fc9-4d04-a9c5-bcab8f4ebe95
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# 营销活动投放 {#marketing-campaign-deliveries}

在营销策划中编排跨渠道投放：通过个性化的电子邮件、短信、推送通知和应用程序内消息，简化与Adobe Campaign的通信。 您可以使用视频、表情符号或GIF等富媒体，并直接集成它们。

可通过活动功能板、活动工作流或直接通过投放概述创建投放。 从营销活动创建投放后，这些投放将链接到此营销活动，并在营销活动级别合并。

## 创建投放 {#create-deliveries}

您可以通过两种方式将投放添加到营销活动：

* 从 **[!UICONTROL Add a delivery]** 活动仪表板中的链接。

![](assets/campaign_op_add_delivery.png)

保存后，投放即会添加到活动仪表板。

* 从活动工作流中，在 **[!UICONTROL Targeting and workflows]** 选项卡，通过添加投放。

  ![](assets/campaign-wf-delivery.png)

  启动工作流后，投放即会添加到活动仪表板。

了解如何设置和执行投放审批流程 [本页内容](marketing-campaign-approval.md).

## 开始投放 {#start-a-delivery}

获得所有批准后，可以发送投放。 投放执行过程取决于渠道。

* 有关电子邮件或移动渠道投放，请参阅 [本节](#start-an-online-delivery)

* 对于直邮投放，请参阅 [本节](#start-an-offline-delivery)

### 开始电子邮件或移动投放 {#start-an-online-delivery}

在批准所有审批请求后，投放状态将更改为 **[!UICONTROL Pending confirmation]** 并且可以启动。 可以开始投放的审阅人会收到投放已准备就绪可供开始的通知。

![](assets/confirm-delivery.png)

该信息也会显示在促销活动信息板上。 此 **[!UICONTROL Confirm delivery]** 链接可让您开始投放。

![](assets/confirm-delivery-from-dashboard.png)

确认投放仅限于管理员，以及投放或营销活动属性中明确提及的操作员或操作员组。 如果未设计运算符，则管理员和活动所有者可以批准。

![](assets/select-delivery-reviewers.png)

但是，您还可以允许活动所有者确认发送，即使已在投放或活动属性中定义特定审阅人也是如此。 为此，作为管理员，创建 **NmsCampaign_Activate_OwnerConfirmation** 选项并将其设置为 **1**. 这些选项是从 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]** Campaign资源管理器的文件夹。


### 开始直邮投放 {#start-an-offline-delivery}

获得所有批准后，投放状态将更改为 **[!UICONTROL Pending extraction]**. 提取文件是通过专用的 [技术工作流](../workflow/technical-workflows.md) 在默认配置中，当直邮投放挂起提取时，会自动启动该流程。 当流程正在进行时，它将显示在仪表板中，并可通过其链接进行编辑。

成功执行提取工作流后，必须批准提取文件（前提是在投放设置中选择了提取文件批准）。 [了解详情](marketing-campaign-approval.md#approving-an-extraction-file)。

请按照以下步骤验证内容并将文件发送给提供商：

1. 提取文件获得批准后，即可生成路由器通知电子邮件的证明。 此电子邮件基于投放模板构建。 它必须被批准。

   此步骤仅在 **[!UICONTROL Enable the sending and validation of proofs (Direct mail)]** 选项在中已启用 **[!UICONTROL Approvals]** 选项卡。

   ![](assets/enable-proof-validation.png)

1. 单击 **[!UICONTROL Send a proof]** 按钮以创建验证。

   必须预先定义验证目标。

   您可以创建所需数量的验证。 这些资源可通过 **[!UICONTROL Direct mail...]** 投放详细信息的链接。

1. 投放状态更改为 **[!UICONTROL To submit]**. 单击 **[!UICONTROL Submit proofs]** 按钮以开始审批流程。

1. 投放状态更改为 **[!UICONTROL Proof to validate]** 和按钮允许您接受或拒绝审批。

   您可以接受或拒绝此批准，或返回提取步骤。

1. 验证获批后，提取文件将发送到路由器并完成投放。

### 预算和成本计算 {#compute-costs-and-stocks}

文件提取将启动两个流程：预算计算和库存计算。 更新预算条目。

* 此 **[!UICONTROL Budget]** 选项卡允许您管理营销活动的预算。 成本条目的总数显示在 **[!UICONTROL Calculated cost]** 营销活动主选项卡及其所属项目的字段。 这些金额还反映在营销活动预算中。

  ![](assets/campaign-budget-tab.png)

  最终将根据路由器提供的信息计算实际成本。 只有实际发送的消息才会被计费。

* 库存定义于 **[!UICONTROL Administration > Campaign management > Stocks]** 树节点。

  ![](assets/campaign-stocks.png)

  中的成本结构 **[!UICONTROL Administration > Campaign management > Service providers]** 节点。

  ![](assets/campaign-service-providers.png)

  库存行在库存区中可见。 要定义初始坯件，请打开坯件线。 每次进行交货时，库存都会减少。 您可以定义警报级别和通知。


  >[!NOTE]
  >
  >了解有关预算的更多信息 [在此部分中](providers--stocks-and-budgets.md).
