---
product: campaign
title: 营销活动投放
description: 了解有关营销活动投放的更多信息
feature: Campaigns, Resource Management, Cross Channel Orchestration
exl-id: 1d9638cb-0fc9-4d04-a9c5-bcab8f4ebe95
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# 营销活动投放 {#marketing-campaign-deliveries}

在活动中编排跨渠道投放：通过个性化电子邮件、短信、推送通知和应用程序内消息简化与Adobe Campaign的通信。 您可以使用富媒体(如视频、表情符号或GIF)并直接集成它们。

投放可通过营销活动仪表板、营销活动工作流创建，或直接通过投放概述创建。 从营销活动创建投放后，投放将链接到此营销活动，并在营销活动级别进行整合。

## 创建投放 {#create-deliveries}

您可以通过两种方式向营销活动添加投放：

* 从 **[!UICONTROL Add a delivery]** 链接。

![](assets/campaign_op_add_delivery.png)

保存后，投放会添加到营销活动仪表板。

* 在营销活动工作流中， **[!UICONTROL Targeting and workflows]** 选项卡，方法是添加投放。

   ![](assets/campaign-wf-delivery.png)

   工作流启动后，投放会添加到营销活动仪表板。

了解如何设置和执行投放审批流程 [本页](marketing-campaign-approval.md).

## 开始投放 {#start-a-delivery}

在授予所有批准后，即可发送投放。 投放执行过程取决于渠道。

* 有关电子邮件或移动渠道投放，请参阅 [此部分](#start-an-online-delivery)

* 有关直邮投放，请参阅 [此部分](#start-an-offline-delivery)

### 开始电子邮件或移动投放 {#start-an-online-delivery}

在授予所有批准请求后，投放状态将更改为 **[!UICONTROL Pending confirmation]** 和。 可以开始投放的审阅人会收到投放准备就绪的通知。

![](assets/confirm-delivery.png)

该信息也会显示在营销活动仪表板上。 的 **[!UICONTROL Confirm delivery]** 链接允许您开始投放。

![](assets/confirm-delivery-from-dashboard.png)

确认投放仅限于管理员，以及投放属性或营销活动属性中明确提及的操作员或操作员组。 如果未设计操作员，则管理员和营销活动所有者可以批准。

![](assets/select-delivery-reviewers.png)

但是，您也可以允许营销活动所有者确认发送，即使在投放属性或营销活动属性中定义了特定的审阅者也是如此。 为此，请以管理员身份创建 **NmsCampaign_Activate_OwnerConfirmation** 选项，并将其设置为 **1**. 选项通过 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]** 节点。


### 启动直邮投放 {#start-an-offline-delivery}

在授予所有批准后，投放状态将更改为 **[!UICONTROL Pending extraction]**. 提取文件通过专用 [技术工作流](../workflow/technical-workflows.md) 在默认配置中，当直邮投放处于待提取状态时，将自动启动直邮投放。 进程进行中时，该进程会显示在功能板中，并可通过其链接进行编辑。

成功执行提取工作流后，必须批准提取文件（前提是已在投放设置中选择提取文件的批准）。 [了解详情](marketing-campaign-approval.md#approving-an-extraction-file)。

请按照以下步骤验证内容并将文件发送给提供商：

1. 提取文件获得批准后，即可生成路由器通知电子邮件的校样。 此电子邮件基于投放模板构建。 必须获得批准。

   此步骤仅在 **[!UICONTROL Enable the sending and validation of proofs (Direct mail)]** 选项 **[!UICONTROL Approvals]** 选项卡。

   ![](assets/enable-proof-validation.png)

1. 单击 **[!UICONTROL Send a proof]** 按钮以创建校样。

   校样目标必须事先定义。

   您可以创建所需数量的校样。 可通过 **[!UICONTROL Direct mail...]** 投放详细信息的链接。

1. 投放状态将更改为 **[!UICONTROL To submit]**. 单击 **[!UICONTROL Submit proofs]** 按钮以启动批准流程。

1. 投放状态将更改为 **[!UICONTROL Proof to validate]** 而按钮则允许您接受或拒绝批准。

   您可以接受或拒绝此批准，或返回提取步骤。

1. 校样获得批准后，提取文件将发送到路由器并完成传送。

### 预算和成本计算 {#compute-costs-and-stocks}

文件提取会启动两个进程：预算计算和库存计算。 预算条目会更新。

* 的 **[!UICONTROL Budget]** 选项卡，用于管理营销活动的预算。 成本分录的合计显示在 **[!UICONTROL Calculated cost]** 营销活动主选项卡及其所属项目的字段。 金额也反映在促销活动预算中。

   ![](assets/campaign-budget-tab.png)

   实际成本最终将根据路由器提供的信息计算。 只有实际发送的消息才会开票。

* 股票于 **[!UICONTROL Administration > Campaign management > Stocks]** 树的节点。

   ![](assets/campaign-stocks.png)

   成本结构 **[!UICONTROL Administration > Campaign management > Service providers]** 节点。

   ![](assets/campaign-service-providers.png)

   库存行在库存部分中可见。 要定义初始库存，请打开库存行。 每次交货时，库存都会减少。 您可以定义警报级别和通知。


   >[!NOTE]
   >
   >了解有关预算的更多信息 [在此部分中](providers--stocks-and-budgets.md).
