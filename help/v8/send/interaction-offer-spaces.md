---
solution: Campaign
product: Adobe Campaign
title: 活动交互优惠空间
description: 了解如何创建优惠空间
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---

# 创建优惠空间{#creating-offer-spaces}

优惠目录的内容以优惠空间配置。 默认情况下，内容可以包括以下字段：**[!UICONTROL Title]**、**[!UICONTROL Destination URL]**、**[!UICONTROL Image URL]**、**[!UICONTROL HTML content]**&#x200B;和&#x200B;**[!UICONTROL Text content]**。 字段序列在优惠空间中配置。

作为&#x200B;**技术管理员**，您可以在设计环境中创建优惠空间。 您需要具有对优惠空间子文件夹的访问权限。 创建后，这些优惠空间会在优惠审批过程中自动复制到实时环境中。

高级参数允许您指定联系人标识键（例如，可以由各种元素组成，名称和电子邮件字段等）。 有关详细信息，请参阅[演示已识别的优惠](../../interaction/using/integration-via-javascript--client-side-.md#presenting-an-identified-offer)部分。

HTML渲染是通过渲染函数创建的。 渲染函数中定义的字段序列必须与内容中配置的序列相同。

![](assets/offer_space_create_009.png)

要创建新优惠空间，请执行以下步骤：

1. 在优惠空间列表中，单击&#x200B;**[!UICONTROL New]**。

   ![](assets/offer_space_create_001.png)

1. 选择要使用的渠道并更改优惠空间的标签。

   ![](assets/offer_space_create_002.png)

1. 选中&#x200B;**[!UICONTROL Enable unitary mode]**&#x200B;选项

1. 转到&#x200B;**[!UICONTROL Content field]**&#x200B;窗口并单击&#x200B;**[!UICONTROL Add]**。

   ![](assets/offer_space_create_003.png)

1. 转至&#x200B;**[!UICONTROL Content]**&#x200B;节点，按以下顺序选择字段：**[!UICONTROL Title]**、**[!UICONTROL Image URL]**、**[!UICONTROL HTML content]**、**[!UICONTROL Destination URL]**。

   ![](assets/offer_space_create_004.png)

1. 选中&#x200B;**[!UICONTROL Required]**&#x200B;选项，将每个字段设为必填。

   >[!NOTE]
   >
   >此选项在预览中使用，如果优惠中缺少一个必填字段，则在发布时使优惠空间无效。 但是，如果优惠已在某个优惠空间上生存，则不会考虑这些标准。

   ![](assets/offer_space_create_005.png)

1. 单击&#x200B;**[!UICONTROL Edit functions]**&#x200B;可创建渲染函数。

   这些函数用于在优惠空间上生成优惠呈现。 有多种可能的格式：HTML或文本。

   **注意** - XML格式仅限于临时不可用的入站交互。[了解详情](../start/capability-matrix.md#gs-unavailable-features)

   ![](assets/offer_spacecreate_006.png)_

1. 转到&#x200B;**[!UICONTROL HTML rendering]**&#x200B;选项卡并选择&#x200B;**[!UICONTROL Overload the HTML rendering function]**。
1. 插入您的渲染功能。

   ![](assets/offer_space_create_007.png)

如有必要，您可以使HTML和文本渲染功能过载。 [了解详情](../../interaction/using/about-inbound-channels.md)。

## 优惠建议状态{#offer-proposition-statuses}

优惠建议状态因与目标群体的交互而异。 活动交互模块附带一组值，这些值可在优惠建议的整个生命周期中应用到该应用程序。 您需要配置平台，以便创建并接受优惠建议时状态发生更改。

>[!NOTE]
>
>状态更新是一个异步进程。 它由每小时触发的跟踪工作流执行。

### 优惠状态列表{#status-list}

可用优惠状态为：

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

默认情况下不应用这些值：它们必须配置。

>[!NOTE]
>
>如果优惠建议链接到状态为“已发送”的投放，则优惠的状态将自动更改为“已显示”。

### 优惠创建命题时的状态{#configuring-the-status-when-the-proposition-is-created}

当优惠建议&#x200B;**已创建**&#x200B;时，其状态将更新。

在&#x200B;**[!UICONTROL Design]**&#x200B;环境中，对于每个优惠空间，根据要在优惠报告中显示的信息，配置创建命题时要应用的状态。

为此请执行以下操作步骤：

1. 转到所需空间的&#x200B;**[!UICONTROL Storage]**&#x200B;选项卡。
1. 选择创建时要应用于命题的状态。

   ![](assets/offer_update_status_001.png)

### 优惠接受命题时的状态{#configuring-the-status-when-the-proposition-is-accepted}

优惠建议&#x200B;**已接受**&#x200B;后，使用默认提供的值之一配置命题的新状态。 当收件人单击优惠中的链接时，将应用更新。

为此请执行以下操作步骤：

1. 转到所需空间的&#x200B;**[!UICONTROL Storage]**&#x200B;选项卡。
1. 选择要在被接受时应用于建议的状态。

   ![](assets/offer_update_status_002.png)

<!--
**Inbound interaction**

The **[!UICONTROL Storage]** tab lets you define statuses for **proposed** and **accepted** offer propositions only. For inbound interaction, the status of offer propositions should be specified directly in the URL for calling the offer engine, rather than through the interface. This way, you will be able to specify which status to apply in other cases, for example if an offer proposition is rejected.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

For instance, the proposition (identifier **40004**) that matches the **Home insurance** offer displayed on the **Neobank** site contains the following URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

As soon as a visitor clicks the offer, and therefore the URL, the **[!UICONTROL Accepted]** status (value **3**) is applied to the proposition and the visitor is redirected to a new page of the **Neobank** site to take out the insurance contract.

>[!NOTE]
>
>If you want to specify another status in the url (for example if an offer proposition is rejected), use the value corresponding to the desired status. Example: **[!UICONTROL Rejected]** = "5", **[!UICONTROL Presented]** = "1" and so on.
>
>Statuses and their values can be retrieved in the **[!UICONTROL Offer propositions (nms)]** data schema. For more on this, refer to [this page](../../configuration/using/data-schemas.md).

**Outbound interaction**
-->

当优惠建议包含链接时，可以自动将&#x200B;**[!UICONTROL Interested]**&#x200B;状态应用到投放。 只需将&#x200B;**_urlType=&quot;11&quot;**&#x200B;值添加到链接：

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## 优惠预览/空间{#offer-preview-per-space}

在&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡中，可以通过选择的方法视图收件人符合其条件的优惠。 在以下示例中，收件人有资格通过邮件获得三个优惠建议。

![](assets/offer_space_overview_002.png)

如果收件人没有资格获得任何优惠，则预览中会显示此信息。

![](assets/offer_space_overview_001.png)

<!--
The preview can ignore contexts when they are restricted to a space. This is the case when the interaction schema has been extended to add fields referenced in a space using an inbound channel (for more on this, refer to [Extension example](../../interaction/using/extension-example.md)).
-->
