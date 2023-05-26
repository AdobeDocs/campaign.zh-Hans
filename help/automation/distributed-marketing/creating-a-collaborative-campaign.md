---
product: campaign
title: 创建协作活动
description: 了解如何创建协作活动
feature: Distributed Marketing
exl-id: edf887fb-c391-405c-b3cf-dc34aed69c53
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 4%

---

# 创建协作活动{#creating-a-collaborative-campaign-intro}



中央实体从中创建协作营销活动 **分布式营销** 活动模板。 请参见[此页面](about-distributed-marketing.md#collaborative-campaign)。

## 创建协作活动 {#creating-a-collaborative-campaign}

要配置协作营销活动，请单击 **[!UICONTROL Campaign management > Campaigns]** 文件夹，然后 **[!UICONTROL New]** 图标。

>[!NOTE]
>
>除了 **[!UICONTROL collaborative campaigns (by campaign)]**，可通过Web界面配置和执行这些营销活动。

协作活动数据库的配置过程与本地活动模板的配置过程类似。 不同类型的协作活动的规格详见下文。

### 按形状 {#by-form}

要创建协作活动（按表单），请 **[!UICONTROL Collaborative campaign (by form)]** 必须选择模板。

![](assets/mkg_dist_mutual_op_form2.png)

在 **[!UICONTROL Edit]** 选项卡，单击 **[!UICONTROL Advanced campaign parameters...]** 链接以访问 **分布式营销** 选项卡。

选择 **按表单** Web界面。 此类界面允许您创建个性化字段，本地实体在订购营销活动时将使用这些字段。 请参阅 [创建本地活动（按表单）](examples.md#creating-a-local-campaign--by-form-).

保存您的营销活动。 您现在可以从以下位置使用它： **Campaign包** 在中查看 **Campaign** 选项卡，通过单击 **[!UICONTROL Create]** 按钮。

此 **[!UICONTROL Campaign Package]** 视图允许您使用本地营销活动模板（现成或重复）以及协作营销活动的引用营销活动，以便为不同的组织实体创建营销活动。

![](assets/mkg_dist_mutual_op_form1b.png)

### 按营销活动 {#by-campaign}

要创建协作营销活动（按营销活动），请 **[!UICONTROL Collaborative campaign (by campaign) (opCollaborativeByCampaign)]** 必须选择模板。

![](assets/mkg_dist_mutual_op_by_op2.png)

订购营销活动时，本地实体可以完成由中心实体定义的标准，并在订购之前评估营销活动。

一次订购 **协作营销活动（按营销活动）** 由中央实体批准，则会为本地实体创建子营销活动。 一旦可供它们使用，本地实体就可以修改：

* 营销活动工作流，
* 类型规则，
* 和个性化字段。

本地实体执行子营销活动。 中央实体执行父营销策划。

中央实体可以查看与关联的所有子营销活动 **协作营销活动（按营销活动）** 从此仪表板(通过 **[!UICONTROL List of associated campaigns]** 链接)。

![](assets/mkg_dist_mutual_op_by_op.png)

### 通过目标审批 {#by-target-approval}

要创建协作活动（通过目标审批），请执行以下操作 **[!UICONTROL Collaborative campaign (by target approval)]** 必须选择模板。

![](assets/mkg_dist_mutual_op_by_valid.png)

>[!NOTE]
>
>在此模式下，中央实体不需要指定本地实体。

活动工作流必须集成 **本地审批** 键入activity。 活动参数如下：

* **[!UICONTROL Action to perform]** : 目标审批通知.
* **[!UICONTROL Distribution context]** : 明确.
* **[!UICONTROL Data distribution]** ：本地实体分发。

**本地实体分发** 必须创建type data distribution。 通过数据分发模板，您可以限制分组值列表中的记录数。 In **[!UICONTROL Resources > Campaign management > Data distribution]**，单击 **[!UICONTROL New]** 图标以新建 **[!UICONTROL Data distribution]**. 有关数据分发的更多信息，

![](assets/mkg_dist_data_distribution.png)

选择 **定位维度** 和 **[!UICONTROL Distribution field]**. 对于 **[!UICONTROL Assignment type]**，选择 **本地实体**.

在 **[!UICONTROL Distribution]** 选项卡，为每个本地实体添加一个字段并指定值。

![](assets/mkg_dist_data_distribution2.png)

您可以添加第二个 **目标审批** 在 **投放** 键入activity以配置相关报表。

在营销活动创建通知消息中，本地实体接收已由中心实体参数预定义的联系人列表。

![](assets/mkg_dist_mutual_op_by_valid1.png)

本地实体可以根据营销活动内容删除某些联系人。

![](assets/mkg_dist_mutual_op_by_valid2.png)

### 简单 {#simple}

要创建简单的协作活动，请 **[!UICONTROL Collaborative campaign (simple)]** 必须选择模板。

## 创建协作活动包 {#creating-a-collaborative-campaign-package}

要使营销活动对本地实体可用，中央实体必须创建营销活动包。

应用以下步骤：

1. 在 **[!UICONTROL Navigation]** 部分 **营销活动** 页面上，单击 **[!UICONTROL Campaign packages]** 链接。
1. 单击 **[!UICONTROL Create]** 按钮。
1. 窗口顶部的部分允许您选择 **[!UICONTROL New collaborative package (mutualizedEmpty)]** 模板。
1. 选择引用营销活动。
1. 指定营销活动包的标签、文件夹和执行计划。

### 日期 {#dates}

开始日期和结束日期定义营销活动包列表中的营销活动可见性时段。

对象 **协作活动**，中央实体必须指定注册和个性化截止日期。

>[!NOTE]
>
>此 **[!UICONTROL Personalization deadline]** 允许中央实体选择一个截止日期，本地实体必须在该日期之前交付了用于配置营销活动的文档（电子表格、图像）。 这不是强制选项。 侧步进此日期将不会影响Campaign实施。

![](assets/s_advuser_mkg_dist_create_mutual_entry.png)

### 受众 {#audience}

创建协作营销活动后，中央实体必须立即指定每个营销活动所涉及的本地实体。

![](assets/s_advuser_mkg_dist_create_mutual_entry2.png)

>[!CAUTION]
>
>**[!UICONTROL Simple, by form and by campaign collaborative campaign kits]** 除非已指定相关的本地实体，否则无法批准。

### 审批模式 {#approval-modes}

对象 **协作活动**，您可以指定订单审批模式。

![](assets/mkg_dist_edit_kit1.png)

在手动模式下，本地实体需要订阅营销活动才能参与。

在自动模式下，本地实体预订阅营销活动。 它可以在不需要中央实体批准的情况下取消促销活动订阅或修改其参数。

![](assets/mkg_dist_edit_kit2.png)

### 通知 {#notifications}

通知的配置与本地实体的通知相同。 请参阅[此小节](creating-a-local-campaign.md#notifications)。

## 订购营销活动 {#ordering-a-campaign}

当将协作营销活动添加到营销活动包列表时，会通知属于由中央实体定义的受众的本地实体(即 **协作活动（按目标批准）** 没有预定义受众)。 发送的消息包含一个链接，通过该链接可注册促销活动，如下所示：

![](assets/mkg_dist_mutual_op_notification.png)

利用此消息，本地实体还可以查看由创建资源包的中央运算符输入的描述以及链接到营销活动的文档。 这些内容不属于营销策划本身，但它们提供了关于该营销策划的其他信息。

一旦本地操作员通过Web界面登录，他们就可以向要订购的协作活动输入个性化信息：

![](assets/mkg_dist_mutual_op_command.png)

本地实体完成注册后，中心实体会通过电子邮件收到批准其订单的通知。

![](assets/mkg_dist_mutual_op_valid_command.png)

有关详情，请参阅 [审批流程](creating-a-local-campaign.md#approval-process) 部分。

## 批准订单 {#approving-an-order}

批准协作活动包订单的流程与批准本地活动包订单的流程相同。 请参阅[此小节](creating-a-local-campaign.md#approving-an-order)。
