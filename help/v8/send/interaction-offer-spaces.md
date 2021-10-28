---
title: Campaign互动优惠空间
description: 了解如何创建优惠空间
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 889400a238f32968464f1425bb7d6c2dc3ff3cd0
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 3%

---

# 创建优惠空间{#creating-offer-spaces}

选件目录的内容在选件空间中进行配置。 默认情况下，内容可以包含以下字段： **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** 和 **[!UICONTROL Text content]**. 字段序列在选件空间中进行配置。

As a **技术管理员**，则可以在设计环境中创建选件空间。 您需要有权访问选件空间子文件夹。 创建后，这些选件空间会在选件批准期间自动复制到实时环境中。

HTML渲染是通过渲染函数创建的。 呈现函数中定义的字段序列必须与内容中配置的序列相同。

![](assets/offer_space_create_009.png)

要创建新选件空间，请执行以下步骤：

1. 在选件空间列表中，单击 **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. 选择要使用的渠道，并更改选件空间的标签。

   ![](assets/offer_space_create_002.png)

1. 检查 **[!UICONTROL Enable unitary mode]** 选项

1. 转到 **[!UICONTROL Content field]** 窗口，单击 **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. 转到 **[!UICONTROL Content]** 节点，然后按以下顺序选择字段： **[!UICONTROL Title]**，则 **[!UICONTROL Image URL]**，则 **[!UICONTROL HTML content]**，则 **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. 检查 **[!UICONTROL Required]** 选项，以使每个字段成为必填字段。

   >[!NOTE]
   >
   >此选项在预览时使用，如果选件中缺少一个必填字段，则会导致发布时选件空间无效。 但是，如果选件已在选件空间上处于实时状态，则不会考虑这些标准。

   ![](assets/offer_space_create_005.png)

1. 单击 **[!UICONTROL Edit functions]** 创建渲染函数。

   这些函数用于在选件空间上生成选件表示形式。 有多种可能的格式：HTML或文本。

   **注意** - XML格式仅限于集客交互，此类交互在此版本的产品中不可用。 [了解详情](../start/capability-matrix.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. 转到 **[!UICONTROL HTML rendering]** 选项卡，选择 **[!UICONTROL Overload the HTML rendering function]**.
1. 插入您的渲染函数。

   ![](assets/offer_space_create_007.png)

## 优惠建议状态 {#offer-proposition-statuses}

优惠建议状态因与目标群体的交互而异。 Campaign交互模块附带一组值，这些值可在选件的整个生命周期中应用于该选件建议。 您需要配置平台，以便在创建并接受选件建议时状态发生更改。

>[!NOTE]
>
>状态更新是 **异步** 进程。 它由每小时触发的跟踪工作流执行。

### 选件状态列表 {#status-list}

可用的选件状态包括：

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

默认情况下，不会应用这些值：必须配置它们。

>[!NOTE]
>
>如果选件链接到状态为“已发送”的投放，则选件建议的状态将自动更改为“已显示”。

### 创建建议时的选件状态 {#configuring-the-status-when-the-proposition-is-created}

当优惠建议为 **已创建**，则其状态会更新。

在 **[!UICONTROL Design]** 环境中，根据您希望在选件报表中显示的信息，对于每个选件空间，配置在创建建议时要应用的状态。

为此请执行以下操作步骤：

1. 转到 **[!UICONTROL Storage]** 选项卡。
1. 选择要在创建命题时应用于该命题的状态。

   ![](assets/offer_update_status_001.png)

### 建议被接受时的优惠状态 {#configuring-the-status-when-the-proposition-is-accepted}

一旦有优惠建议 **接受**，请使用默认提供的值之一配置建议的新状态。 当收件人单击选件中的链接时，将应用更新。

为此请执行以下操作步骤：

1. 转到 **[!UICONTROL Storage]** 选项卡。
1. 选择要在建议被接受时应用于该建议的状态。

   ![](assets/offer_update_status_002.png)


**入站互动**

的 **[!UICONTROL Storage]** 选项卡，用于定义状态 **建议** 和 **接受** 仅提供建议。 对于集客交互，应直接在用于调用选件引擎的URL中指定选件主张的状态，而不是通过界面指定。 这样，您就可以指定在其他情况下应用的状态，例如，如果选件建议被拒绝。

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

例如，建议（标识符） **40004**) **家庭保险** 选件 **尼奥班克** 网站包含以下URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

当访客单击该选件（从而单击该URL）时， **[!UICONTROL Accepted]** 状态（值） **3**)，且访客将被重定向到的新页面 **尼奥班克** 地点以履行保险合同。

>[!NOTE]
>
>如果您想要在URL中指定其他状态（例如，如果选件建议被拒绝），请使用与所需状态对应的值。 示例： **[!UICONTROL Rejected]** = &quot;5&quot;, **[!UICONTROL Presented]** =“1”等。
>
>可以在 **[!UICONTROL Offer propositions (nms)]** 数据架构。 有关详细信息，请参见[此页面](../dev/create-schema.md)。

**叫客互动**

您可以自动应用 **[!UICONTROL Interested]** 投放包含链接时的选件建议状态。 只需将 **_urlType=&quot;11&quot;** 值：

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## 每个空间的选件预览 {#offer-preview-per-space}

在 **[!UICONTROL Preview]** 选项卡，则可以通过所选方法查看收件人有资格使用的选件。 在以下示例中，收件人有资格通过邮件获得三个选件建议。

![](assets/offer_space_overview_002.png)

如果收件人不符合任何选件的条件，则会在预览中显示该选件。

![](assets/offer_space_overview_001.png)


当上下文被限制为空格时，预览可以忽略这些上下文。 当交互架构已扩展为使用集客渠道添加空间中引用的字段时，便属于这种情况。

![](../assets/do-not-localize/book.png)  有关更多信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html){target=&quot;_blank&quot;}。