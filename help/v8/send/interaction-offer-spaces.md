---
title: Campaign互动优惠空间
description: 了解如何创建优惠空间
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 3%

---

# 创建优惠空间{#creating-offer-spaces}

选件目录的内容在选件空间中进行配置。 默认情况下，内容可以包含以下字段：**[!UICONTROL Title]**、**[!UICONTROL Destination URL]**、**[!UICONTROL Image URL]**、**[!UICONTROL HTML content]**&#x200B;和&#x200B;**[!UICONTROL Text content]**。 字段序列在选件空间中进行配置。

作为&#x200B;**技术管理员**，您可以在设计环境中创建选件空间。 您需要有权访问选件空间子文件夹。 创建后，这些选件空间会在选件批准期间自动复制到实时环境中。

HTML渲染是通过渲染函数创建的。 呈现函数中定义的字段序列必须与内容中配置的序列相同。

![](assets/offer_space_create_009.png)

要创建新选件空间，请执行以下步骤：

1. 在选件空间列表中，单击&#x200B;**[!UICONTROL New]**。

   ![](assets/offer_space_create_001.png)

1. 选择要使用的渠道，并更改选件空间的标签。

   ![](assets/offer_space_create_002.png)

1. 检查&#x200B;**[!UICONTROL Enable unitary mode]**&#x200B;选项

1. 转到&#x200B;**[!UICONTROL Content field]**&#x200B;窗口，然后单击&#x200B;**[!UICONTROL Add]**。

   ![](assets/offer_space_create_003.png)

1. 转到&#x200B;**[!UICONTROL Content]**&#x200B;节点并按以下顺序选择字段：**[!UICONTROL Title]**、**[!UICONTROL Image URL]**、**[!UICONTROL HTML content]**、**[!UICONTROL Destination URL]**。

   ![](assets/offer_space_create_004.png)

1. 选中&#x200B;**[!UICONTROL Required]**&#x200B;选项，以将每个字段设为必填字段。

   >[!NOTE]
   >
   >此选项在预览时使用，如果选件中缺少一个必填字段，则会导致发布时选件空间无效。 但是，如果选件已在选件空间上处于实时状态，则不会考虑这些标准。

   ![](assets/offer_space_create_005.png)

1. 单击&#x200B;**[!UICONTROL Edit functions]**&#x200B;以创建渲染函数。

   这些函数用于在选件空间上生成选件表示形式。 有多种可能的格式：HTML或文本。

   **注意**  - XML格式仅限于集客交互，而在此版本的产品中，这些交互不可用。[了解详情](../start/capability-matrix.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. 转到&#x200B;**[!UICONTROL HTML rendering]**&#x200B;选项卡，然后选择&#x200B;**[!UICONTROL Overload the HTML rendering function]**。
1. 插入您的渲染函数。

   ![](assets/offer_space_create_007.png)

## 优惠建议状态 {#offer-proposition-statuses}

优惠建议状态因与目标群体的交互而异。 Campaign交互模块附带一组值，这些值可在选件的整个生命周期中应用于该选件建议。 您需要配置平台，以便在创建并接受选件建议时状态发生更改。

>[!NOTE]
>
>状态更新是一个&#x200B;**异步**&#x200B;进程。 它由每小时触发的跟踪工作流执行。

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

当选件建议为&#x200B;**created**&#x200B;时，其状态会更新。

在&#x200B;**[!UICONTROL Design]**&#x200B;环境中，对于每个选件空间，根据您希望在选件报表中显示的信息，将状态配置为在创建命题时应用。

为此请执行以下操作步骤：

1. 转到所需空间的&#x200B;**[!UICONTROL Storage]**&#x200B;选项卡。
1. 选择要在创建命题时应用于该命题的状态。

   ![](assets/offer_update_status_001.png)

### 建议被接受时的优惠状态 {#configuring-the-status-when-the-proposition-is-accepted}

在&#x200B;**已接受**&#x200B;选件建议后，使用默认提供的值之一配置建议的新状态。 当收件人单击选件中的链接时，将应用更新。

为此请执行以下操作步骤：

1. 转到所需空间的&#x200B;**[!UICONTROL Storage]**&#x200B;选项卡。
1. 选择要在建议被接受时应用于该建议的状态。

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

当投放包含链接时，您可以自动将&#x200B;**[!UICONTROL Interested]**&#x200B;状态应用到选件建议。 只需将&#x200B;**_urlType=&quot;11&quot;**&#x200B;值添加到链接：

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## 每个空间的选件预览 {#offer-preview-per-space}

在&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡中，您可以通过所选方法查看收件人有资格查看的选件。 在以下示例中，收件人有资格通过邮件获得三个选件建议。

![](assets/offer_space_overview_002.png)

如果收件人不符合任何选件的条件，则会在预览中显示该选件。

![](assets/offer_space_overview_001.png)

<!--
The preview can ignore contexts when they are restricted to a space. This is the case when the interaction schema has been extended to add fields referenced in a space using an inbound channel (for more on this, refer to Extension example.
-->
