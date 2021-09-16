---
title: Campaign互动优惠
description: 了解如何创建优惠
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4dc2008d-681c-4a79-8fc8-c270c9224ab9
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---

# 创建优惠

要创建选件，请执行以下步骤：

1. 浏览到&#x200B;**[!UICONTROL Campaigns]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Offers]**&#x200B;链接。

1. 单击 **[!UICONTROL Create]** 按钮。

1. 更改标签并选择选件应属于的类别。

1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;以创建选件。

   该选件在平台中可用，并且可以配置其内容。

## 资格设置

您现在可以使用&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡定义：

* 优惠的资格期。 [了解详情](#eligibility-period)
* 选件目标群体的过滤器。 [了解详情](#filters-on-the-target)
* 选件权重。 [了解详情](#offer-weight)

### 优惠资格期{#eligibility-period}

在选件的&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡中，定义选件的资格期。 使用下拉列表在日历中选择开始日期和结束日期。

![](assets/offer_eligibility_create_002.png)

在此期间之外，将不会选择选件。 如果您还为选件类别配置了资格日期，则将适用最严格的期限。

### 在目标中添加过滤器 {#filters-on-the-target}

在选件的&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡中，将过滤器应用到选件目标。

要实现此目的，请单击&#x200B;**[!UICONTROL Edit query]**&#x200B;链接，然后选择要应用的过滤器。

![](assets/offer_eligibility_create_003.png)

如果已创建预定义过滤器，则可以从用户过滤器列表中选择它们。 [了解详情](interaction-predefined-filters.md)

![](assets/offer_eligibility_create_004.png)

### 设置选件权重 {#offer-weight}

要使引擎能够在目标符合条件的多个选件之间做出决定，您需要为选件分配一个或多个权重。 您还可以根据需要将过滤器应用到目标，或限制权重要应用到的选件空间。 与重量较轻的选件相比，将更喜欢权重较大的选件。

您可以为同一选件配置多个权重，例如，以区分特定时段、特定目标，甚至选件空间。

例如，对于年龄在18到25岁的联系人，选件可以具有A的重量，对于超过该范围的联系人，选件可以具有B的重量。 如果选件在整个夏天都符合条件，则它在7月份的权重为A，在8月份的权重为B。

>[!NOTE]
>
>可以根据选件所属类别的参数暂时修改分配的权重。 [了解详情](interaction-offer-catalog.md#creating-offer-categories)

要在选件中创建权重，请应用以下步骤：

1. 在选件的&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Add]**。

   ![](assets/offer_weight_create_001.png)

1. 更改标签并分配权重。 默认值为 1。

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >如果未输入权重(0)，则目标将不被视为符合选件条件。

1. 如果您希望将权重应用于给定期间，请定义资格日期。

   ![](assets/offer_weight_create_002.png)

1. 如有必要，请将权重限制为特定选件空间。

   ![](assets/offer_weight_create_003.png)

1. 将过滤器应用到目标。

   ![](assets/offer_weight_create_004.png)

1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;以节省重量。

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >如果目标符合为选定选件赋予多个权重的条件，则引擎会保持最佳（最高）权重。 在调用选件引擎时，每个联系人最多选择一个选件。

### 优惠资格规则摘要 {#a-summary-of-offer-eligibility-rules}

配置完成后，资格规则的摘要将显示在选件仪表板中。

要查看，请单击&#x200B;**[!UICONTROL Schedule and eligibility rules]**&#x200B;链接。

![](assets/offer_eligibility_create_005.png)

## 创建选件内容 {#creating-the-offer-content}

使用&#x200B;**[!UICONTROL Content]**&#x200B;选项卡定义选件内容。

![](assets/offer_content_create_001.png)

1. 定义选件内容的各种参数。

   * **[!UICONTROL Title]** :指定要在选件中显示的标题。警告：这不是指选件的标签，该标签在&#x200B;**[!UICONTROL General]**&#x200B;选项卡中定义。
   * **[!UICONTROL Destination URL]** :指定选件的URL。必须以“http://”或“https://”开头。
   * **[!UICONTROL Image URL]** :指定选件图像的URL或访问路径。
   * **[!UICONTROL HTML content]** /  **[!UICONTROL Text content]** :在所需的选项卡中输入选件的正文。要生成跟踪，**[!UICONTROL HTML content]**&#x200B;必须由HTML元素组成，这些元素可以包含在`<div>`类型元素中。 例如，HTML页面中`<table>`元素的结果将如下所示：

   ```
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   了解如何在[此部分](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted)中定义接受URL。

   ![](assets/offer_content_create_002.png)

   要查找在选件空间配置期间定义的必填字段，请单击&#x200B;**[!UICONTROL Content definitions]**&#x200B;链接以显示列表。 [了解详情](interaction-offer-spaces.md)

   ![](assets/offer_content_create_003.png)

   在此示例中，选件必须包含标题、图像、HTML内容和目标URL。

## 预览选件 {#previewing-the-offer}

配置选件内容后，您可以预览该选件在其收件人看到时的显示效果。

操作步骤：

1. 单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡。

   ![](assets/offer_preview_create_001.png)

1. 选择要查看的选件的表示形式。

   ![](assets/offer_preview_create_002.png)

1. 如果您已对选件内容进行了个性化，请选择选件目标以查看个性化。

<!--

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../campaign/using/about-response-manager.md).

-->

## 批准和激活优惠{#approve-offers}

您现在可以批准并激活选件，以使其在&#x200B;**Live**&#x200B;环境中可用。

↗️有关更多信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content)

## 管理优惠演示{#offer-presentation}

Campaign允许您使用演示规则控制优惠建议的流程。 这些特定于Campaign交互的规则是&#x200B;**分类规则**。 它们允许您根据已向收件人提出的建议的历史记录排除优惠。 在环境中引用了这些参数。

↗️有关更多信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html?lang=en#managing-offers)

## 优惠模拟

通过模拟模块，您可以在向收件人发送建议之前，测试属于某个类别或环境的选件的分布。

模拟会考虑以前应用于选件的上下文和资格规则及其演示规则。 这样，您就可以测试和优化选件建议的各种版本，而无需实际使用选件，或者超量/不限次地吸引目标，因为模拟对目标收件人没有影响。

↗️有关优惠模拟的更多信息，请参阅[Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.html?lang=en)
