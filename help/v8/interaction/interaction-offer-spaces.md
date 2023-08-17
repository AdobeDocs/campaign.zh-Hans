---
title: Campaign交互优惠空间
description: 了解如何创建优惠空间
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 3%

---

# 创建优惠空间{#creating-offer-spaces}

优惠目录的内容在优惠空间中配置。 默认情况下，内容可包含以下字段： **[!UICONTROL Title]**， **[!UICONTROL Destination URL]**， **[!UICONTROL Image URL]**， **[!UICONTROL HTML content]** 和 **[!UICONTROL Text content]**. 字段序列在选件空间中配置。

作为 **技术管理员**&#x200B;中，您可以在“设计”环境中创建选件空间。 您需要具有优惠空间子文件夹的访问权限。 创建后，在批准优惠期间，这些优惠空间会自动复制到实时环境中。

HTML渲染通过渲染函数创建。 渲染函数中定义的字段序列必须与内容中配置的序列相同。

![](assets/offer_space_create_009.png)

要创建新的选件空间，请执行以下步骤：

1. 在选件空间列表中，单击 **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. 选择要使用的渠道并更改优惠空间的标签。

   ![](assets/offer_space_create_002.png)

1. 查看 **[!UICONTROL Enable unitary mode]** option

1. 转到 **[!UICONTROL Content field]** 窗口，然后单击 **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. 转到 **[!UICONTROL Content]** 节点并按以下顺序选择字段： **[!UICONTROL Title]**，则 **[!UICONTROL Image URL]**，则 **[!UICONTROL HTML content]**，则 **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. 查看 **[!UICONTROL Required]** 选项，用于将每个字段设为必填。

   >[!NOTE]
   >
   >该选项在预览中使用，如果选件中缺少必填字段之一，则会在发布时使选件空格无效。 但是，如果优惠空间中已存在优惠，则不会考虑这些标准。

   ![](assets/offer_space_create_005.png)

1. 单击 **[!UICONTROL Edit functions]** 创建渲染函数。

   这些函数用于在优惠空间上生成优惠呈现。 有多种可能的格式：HTML或文本。

   **注意** - XML格式仅限于在此版本的产品中不可用的入站交互。 [了解详情](../start/v7-to-v8.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. 转到 **[!UICONTROL HTML rendering]** 选项卡并选择 **[!UICONTROL Overload the HTML rendering function]**.
1. 插入渲染函数。

   ![](assets/offer_space_create_007.png)

## 优惠建议状态 {#offer-proposition-statuses}

优惠建议状态因与目标群体的交互而异。 Campaign交互模块提供了一组值，可在优惠建议整个生命周期中应用于这些值。 您需要配置平台，以便在创建和接受优惠建议时更改状态。

>[!NOTE]
>
>状态更新为 **异步** 进程。 跟踪由跟踪工作流执行，跟踪工作流每小时触发一次。

### 优惠状态列表 {#status-list}

可用的优惠状态为：

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

默认情况下不应用这些值：必须配置这些值。

>[!NOTE]
>
>如果优惠与状态为“已发送”的投放关联，则优惠建议的状态将自动更改为“已呈现”。

### 创建建议时的优惠状态 {#configuring-the-status-when-the-proposition-is-created}

当优惠建议为 **已创建**，其状态会更新。

在 **[!UICONTROL Design]** 环境，根据要在优惠报表中显示的信息，为每个优惠空间配置在创建建议时要应用的状态。

为此请执行以下操作步骤：

1. 转到 **[!UICONTROL Storage]** 选项卡。
1. 选择建议在创建时应用于建议的状态。

   ![](assets/offer_update_status_001.png)

### 建议被接受时的优惠状态 {#configuring-the-status-when-the-proposition-is-accepted}

一旦优惠建议获得批准 **已接受**，使用默认提供的值之一来配置建议的新状态。 当收件人单击优惠中的链接时，将应用更新。

为此请执行以下操作步骤：

1. 转到 **[!UICONTROL Storage]** 选项卡。
1. 选择建议被接受时您希望应用于该建议的状态。

   ![](assets/offer_update_status_002.png)


**入站互动**

此 **[!UICONTROL Storage]** 选项卡允许您定义状态 **已建议** 和 **已接受** 仅限优惠建议。 对于入站交互，应直接在用于调用优惠引擎的URL中指定优惠建议的状态，而不是通过界面指定。 这样，您将能够指定在其他情况下要应用的状态，例如，如果优惠建议被拒绝。

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

例如，建议(标识符 **40004**)匹配 **家庭保险** 选件显示在 **新银行** 站点包含以下URL：

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

只要访客点击了选件，因此也点击了URL， **[!UICONTROL Accepted]** 状态（值） **3**)应用于建议，并且访客将被重定向到 **新银行** 保险合同办理地点。

>[!NOTE]
>
>如果要在URL中指定其他状态（例如，如果优惠建议被拒绝），请使用与所需状态对应的值。 示例： **[!UICONTROL Rejected]** =“5”， **[!UICONTROL Presented]** =“1”等。
>
>状态及其值可在 **[!UICONTROL Offer propositions (nms)]** 数据架构。 有关详细信息，请参见[此页面](../dev/create-schema.md)。

**出站交互**

您可以自动应用 **[!UICONTROL Interested]** 投放包含链接时优惠建议的状态。 只需添加 **_urlType=&quot;11&quot;** 链接的值：

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## 每个空间的优惠预览 {#offer-preview-per-space}

在 **[!UICONTROL Preview]** 选项卡中，您可以通过所选方法查看收件人符合条件的优惠。 在下面的示例中，收件人可以通过邮件获得三个优惠建议。

![](assets/offer_space_overview_002.png)

如果收件人不符合任何优惠的条件，则会在预览中显示。

![](assets/offer_space_overview_001.png)


当上下文限制为空格时，预览可以忽略上下文。 扩展交互架构以使用入站渠道添加空间中引用的字段时，会出现这种情况。

![](../assets/do-not-localize/book.png)  有关更多信息，请参阅以下示例中的 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html){target="_blank"}.