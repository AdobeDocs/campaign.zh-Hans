---
product: campaign
title: 入站渠道产品建议
description: 入站渠道产品建议
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 90afced3-465d-4370-8a33-51a7e4356135
TQID: 'https://experienceleague.adobe.com/HkXtRV9hn2hZSZyxx86o2muGafhdhWuLp-uYBe4xTaU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '2986'
ht-degree: 1%
---
# 入站渠道产品建议{#offers-on-an-inbound-channel}



## 向匿名访客展示优惠 {#presenting-an-offer-to-an-anonymous-visitor}

Neobank网站希望在其网站上显示选件，以定向浏览页面的未识别访客。

要设置此交互，我们将：

1. [创建匿名环境](#creating-an-anonymous-environment)
1. [创建匿名优惠空间](#creating-anonymous-offer-spaces)
1. [创建优惠类别和主题](#creating-an-offer-category-and-a-theme)
1. [创建匿名优惠。](#creating-anonymous-offers)
1. [在网站上配置Web选件空间](#configure-the-web-offer-space-on-the-website)

### 创建匿名环境 {#creating-an-anonymous-environment}

按照[创建优惠环境](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/offers/interaction-settings/interaction-env#create-an-offer-environment){target="_blank"}（Campaign v8文档）中详述的过程创建基于&#x200B;**访客**&#x200B;维度的匿名环境。

您将获得一个包含新环境的树结构：

![优惠设计树和环境 — 访客属性，传入匿名交互的环境](assets/offer_env_anonymous_003.png)

### 创建匿名优惠空间 {#creating-anonymous-offer-spaces}

1. 在匿名环境中（**访客**）转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Spaces]**&#x200B;节点。
1. 单击&#x200B;**[!UICONTROL New]**&#x200B;以创建呼叫渠道。

   ![优惠空间列表中的“新建”按钮使用“属性”选项卡打开“新建优惠空间”对话框](assets/offer_inbound_anonymous_example_010.png)

   >[!NOTE]
   >
   >空间会自动链接到匿名环境。

1. 更改标签并选择&#x200B;**[!UICONTROL Inbound Web]**&#x200B;渠道。 您还必须选中&#x200B;**[!UICONTROL Enable unitary mode]**&#x200B;框。

   ![带有标签匿名Web高级优惠和已选择入站Web渠道的优惠空间对话框](assets/offer_inbound_anonymous_example_006.png)

1. 选择用于空间的选件内容字段，并通过选中相关框根据需要指定这些字段。

   这样，任何缺少以下元素之一的选件都将不符合此空间的条件：

   * 标题
   * HTML 内容
   * 图像 URL
   * 目标 URL

   ![Select表达式对话框，其“标题”字段被选为优惠空间的优惠内容字段](assets/offer_inbound_anonymous_example_030.png)

1. 编辑HTML渲染函数，例如，如下所示：

   ```javascript
   function (imageUrl, targetUrl, shortContent, htmlSource){
         var html = "<p><b>" + shortContent + "</b></p>";
         html += "<p>" + htmlSource + "</p>";
         html += "<a _urlType='11' href='" + targetUrl + "'><img src='" + encodeURI(imageUrl) + "'/></a>";
         return html;
       }   
   ```

   >[!IMPORTANT]
   >
   >渲染函数必须按照之前选择的顺序命名用于空间的字段，以便正确显示选件。

   ![编辑函数链接打开选件空间的HTML渲染选项卡以重载渲染函数](assets/offer_inbound_anonymous_example_031.png)

1. 保存优惠空间。

### 创建优惠类别和主题 {#creating-an-offer-category-and-a-theme}

1. 转到刚刚创建的环境中的&#x200B;**[!UICONTROL Offer catalog]**&#x200B;节点。
1. 右键单击&#x200B;**[!UICONTROL Offer catalog]**&#x200B;节点并选择&#x200B;**[!UICONTROL Create a new 'Offer category' folder]**。

   为新类别命名&#x200B;**金融产品**。

1. 转到类别的&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡并输入&#x200B;**融资**&#x200B;作为主题，然后保存更改。

   ![优惠类别资格选项卡，“主题”字段设置为“融资”](assets/offer_inbound_anonymous_example_023.png)

### 创建匿名优惠 {#creating-anonymous-offers}

1. 转到您刚刚创建的类别。
1. 单击 **[!UICONTROL New]**。

   ![Financial产品类别的“选件”列表中的“新建”按钮打开“新建选件”对话框](assets/offer_inbound_anonymous_example_013.png)

1. 选择现成的匿名优惠模板或之前创建的模板。

   ![包含新匿名选件(emptyAnonOffer)和新选件(emptyOfferVisitor)的选件模板列表](assets/offer_inbound_anonymous_example_014.png)

1. 更改标签并保存选件。

   ![在保存之前使用标签匿名高级优惠#1的“新建匿名优惠”对话框](assets/offer_inbound_anonymous_example_015.png)

1. 转到&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡，并根据其应用程序上下文指定优惠的权重。

   在本例中，选件配置为在年底之前优先显示在站点的主页上。

   ![具有优惠权重的优惠资格选项卡，且“权重”对话框限制为匿名优惠空间](assets/offer_inbound_anonymous_example_016.png)

1. 转到&#x200B;**[!UICONTROL Content]**&#x200B;选项卡并定义选件的内容。

   >[!NOTE]
   >
   >您可以选择&#x200B;**[!UICONTROL Content definitions]**&#x200B;以显示Web空间所需的元素列表。

   ![包含标题、目标URL、图像URL和第一个匿名优惠的HTML内容的“优惠内容”选项卡](assets/offer_inbound_anonymous_example_017.png)

1. 创建第二个选件。

   ![具有标题、目标URL和HTML内容的第二个匿名优惠的“内容”选项卡](assets/offer_inbound_anonymous_example_018.png)

1. 转到&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡并应用与第一个选件相同的权重。
1. 运行每个选件的批准周期，以便在在线环境中提供这些选件及其批准的选件空间。

### 在网站上配置Web选件空间 {#configure-the-web-offer-space-on-the-website}

要使您刚刚配置的选件在网站上可见，请将JavaScript代码插入网站的HTML页面，以调用交互引擎(有关更多信息，请参阅[关于入站渠道](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/offers/inbound/interaction-present-offers){target="_blank"}（Campaign v8文档）)。

1. 转到HTML页面并插入一个@id属性，该属性的值与之前创建的匿名优惠空间的内部名称匹配（请参阅[创建匿名优惠空间](#creating-anonymous-offer-spaces)），前面有&#x200B;**i_**。

   ![HTML页面源，其div的id为i_SPC3，选件空间的内部名称以i_](assets/offer_inbound_anonymous_example_019.png)开头

1. 插入调用URL。

   在突出显示env=liveVisitor和th=financing参数的情况下，![对interactionProposal.js的HTML脚本调用](assets/offer_inbound_anonymous_example_020.png)

   上面的蓝色URL框对应于实例名称、环境的内部名称（请参阅[创建匿名环境](#creating-an-anonymous-environment)）以及链接到类别的主题（[创建优惠类别和主题](#creating-an-offer-category-and-a-theme)）。 后者是可选的。

当访客访问网站主页时，带有&#x200B;**融资**&#x200B;主题的选件将按HTML页面上的配置显示。

![带有特殊优惠块的Neobank主页在侧栏中显示匿名优惠](assets/offer_inbound_anonymous_example_022.png)

多次访问页面的用户将看到类别中的一个选件或其他选件，因为它们都被分配了相同的权重。

## 在无法识别联系人的情况下切换到匿名环境 {#switching-to-an-anonymous-environment-in-case-of-unidentified-contacts}

Neobank公司希望为两个不同的目标创建营销选件。 它希望为其匿名网站浏览器显示通用选件。 如果其中一位用户是具有Neobank提供的标识符的客户，公司希望他们在登录后立即收到个性化优惠。

此案例研究基于以下情景：

1. 访客无需登录即可浏览Neobank网站。

   ![向未登录的访客显示登录面板的Neobank主页](assets/offer_inbound_fallback_example_050.png)

   页面上显示了三个匿名选件：两个用于Neobank产品的&#x200B;**最佳选件**&#x200B;选件和一个来自Neobank合作伙伴的选件。

   ![包含三个匿名选件的Neobank页面：两个最佳选件和一个合作伙伴选件](assets/offer_inbound_fallback_example_051.png)

1. 该用户是Neobank客户，使用其凭据登录。

   ![用户登录之前已输入凭据的Neobank登录面板](assets/offer_inbound_fallback_example_052.png)

   将显示三个个性化优惠。

   使用特别优惠块中突出显示的三个个性化优惠登录后的![Neobank页面](assets/offer_inbound_fallback_example_053.png)

要实施此案例研究，您需要具有两个选件环境：一个用于匿名交互，另一个具有专门为已识别联系人配置的选件。 如果联系人未登录并因此未被识别，则识别的选件环境将配置为自动切换到匿名选件环境。

应用以下步骤：

* 使用以下步骤创建特定于匿名入站交互的优惠目录：

  1. [为匿名联系人创建环境](#creating-an-environment-for-anonymous-contacts)
  1. [为匿名环境配置优惠空间](#configuring-offer-spaces-for-the-anonymous-environment)
  1. [在匿名环境中创建优惠类别](#creating-offer-categories-in-an-anonymous-environment)
  1. [创建匿名访客优惠](#creating-offers-for-anonymous-visitors)

* 使用以下步骤创建特定于已识别集客交互的优惠目录：

  1. [在标识的环境中配置优惠空间](#configure-the-offer-spaces-in-the-identified-environment)
  1. [在已识别的环境中创建优惠类别](#creating-offer-categories-in-an-identified-environment)
  1. [创建个性化优惠](#creating-personalized-offers)

* 配置对优惠引擎的调用：

  1. [在网页上配置优惠空间](#configuring-offer-spaces-on-the-web-page)
  1. [指定已标识的选件空间的高级设置](#specifying-the-advanced-settings-of-the-identified-offer-spaces)

### 为匿名联系人创建环境 {#creating-an-environment-for-anonymous-contacts}

1. 通过投放映射助手（**访客**&#x200B;映射）为匿名入站交互创建优惠环境。 有关更多信息，请参阅[创建选件环境](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/offers/interaction-settings/interaction-env#create-an-offer-environment){target="_blank"}（Campaign v8文档）。

   ![优惠设计树和环境 — 访客属性，传入匿名交互的环境](assets/offer_env_anonymous_003.png)

### 为匿名环境配置优惠空间 {#configuring-offer-spaces-for-the-anonymous-environment}

网站上必须呈现的选件属于两个不同的类别： **最佳选件**&#x200B;和&#x200B;**合作伙伴**。 在本例中，我们将为每个类别创建特定的优惠空间。

要创建优惠空间以匹配&#x200B;**最佳优惠**&#x200B;类别，请应用以下流程：

1. 在Adobe Campaign树中，转到您刚刚创建的匿名环境并添加优惠空间。

   ![环境 — 访客设计环境中的优惠空间列表，其中突出显示“新建”按钮](assets/offer_inbound_fallback_example_023.png)

1. 创建新的&#x200B;**[!UICONTROL Inbound web]**&#x200B;类型空间。

   ![已选择入站Web的新优惠空间渠道下拉列表](assets/offer_inbound_fallback_example_024.png)

1. 为它输入一个标签： **Web最佳匿名优惠**&#x200B;用于实例。
1. 添加用于此选件空间的选件内容字段并配置渲染函数。

   ![具有入站Web渠道、内容字段和HTML渲染功能的优惠空间Web最佳匿名优惠](assets/offer_inbound_fallback_example_025.png)

   >[!IMPORTANT]
   >
   >渲染函数必须按照之前选择的顺序命名用于空间的字段，以便正确显示选件。

1. 使用同一进程创建入站Web渠道优惠空间以匹配&#x200B;**合作伙伴**&#x200B;类别。

   ![具有入站Web渠道、HTML内容和图像URL字段的优惠空间Web合作伙伴匿名](assets/offer_inbound_fallback_example_026.png)

### 在匿名环境中创建优惠类别 {#creating-offer-categories-in-an-anonymous-environment}

首先，创建两个优惠类别：**最佳优惠**&#x200B;类别和&#x200B;**合作伙伴**&#x200B;类别。 每个类别将包含两个匿名联系人的选件。

1. 转到刚刚创建的匿名环境中的&#x200B;**[!UICONTROL Offer catalog]**。
1. 添加具有&#x200B;**最佳选件**&#x200B;的&#x200B;**[!UICONTROL Offer category]**&#x200B;文件夹作为标签。

   ![设计树中标有“环境 — 访客”下最佳选件的选件类别文件夹](assets/offer_inbound_fallback_example_027.png)

1. 创建第二个类别，并将&#x200B;**合作伙伴**&#x200B;作为标签。

   在“环境 — 访客”下的“最佳选件”旁创建![选件类别合作伙伴](assets/offer_inbound_fallback_example_028.png)

### 创建匿名访客优惠 {#creating-offers-for-anonymous-visitors}

现在，我们将在上面创建的每个类别中创建两个选件。

1. 转到&#x200B;**最佳优惠**&#x200B;类别并创建匿名优惠。

   ![标签为“最佳优惠”的“最佳优惠”类别中的新匿名优惠对话框#1](assets/offer_inbound_fallback_example_029.png)

1. 转到&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡，并根据其应用程序上下文指定优惠的权重。

   最佳优惠的![资格选项卡#1具有主页和保存页面权重的匿名优惠](assets/offer_inbound_fallback_example_030.png)

1. 转到&#x200B;**[!UICONTROL Content]**&#x200B;选项卡并定义选件的内容。

   匿名最佳优惠的![内容选项卡，标题为Neobank银行帐户和HTML内容](assets/offer_inbound_fallback_example_032.png)

1. 在&#x200B;**最佳优惠**&#x200B;类别中创建第二个优惠。

   标题为“Neobank家庭保险”和“HTML内容”的第二个最佳选件的![内容选项卡](assets/offer_inbound_fallback_example_031.png)

1. 转到&#x200B;**合作伙伴**&#x200B;类别并创建匿名优惠。
1. 转到&#x200B;**[!UICONTROL Content]**&#x200B;选项卡并定义选件的内容。

   匿名合作伙伴优惠的![内容选项卡，标题为“Neo每周”和“HTML内容”](assets/offer_inbound_fallback_example_033.png)

1. 转到&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡，并根据其应用程序上下文指定优惠的权重。

   主页权重为3的匿名合作伙伴媒体优惠的![资格选项卡](assets/offer_inbound_fallback_example_034.png)

1. 为&#x200B;**合作伙伴**&#x200B;类别创建第二个选件。

   具有标题偏移和HTML内容的第二个匿名Partner优惠的![内容选项卡](assets/offer_inbound_fallback_example_035.png)

1. 转到&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡，应用与应用于此类别中第一个选件的权重相同的权重，以便这些选件在网站上连续显示。

   首页权重为3的第二个合作伙伴优惠的![资格选项卡，与第一个](assets/offer_inbound_fallback_example_036.png)相同

1. 运行每个选件的批准周期以开始使其上线。 批准内容时，根据优惠激活&#x200B;**合作伙伴**&#x200B;或&#x200B;**最佳优惠**&#x200B;优惠空间。

### 在标识的环境中配置优惠空间 {#configure-the-offer-spaces-in-the-identified-environment}

您将在网站上展示的选件来自两个不同的类别：**最佳选件**&#x200B;和&#x200B;**合作伙伴**。 在本例中，我们希望为每个类别创建一个特定的空间。

要创建两个优惠空间，请应用与匿名优惠空间相同的过程。 请参阅[为匿名环境配置优惠空间](#configuring-offer-spaces-for-the-anonymous-environment)。

1. 在Adobe Campaign树中，转到您刚刚创建的环境，并添加&#x200B;**最佳选件**&#x200B;和&#x200B;**合作伙伴**&#x200B;选件空间。
1. 应用[为匿名环境配置优惠空间](#configuring-offer-spaces-for-the-anonymous-environment)中详述的进程。

   ![环境 — 收件人设计环境的优惠空间列表，Web合作伙伴标识的空间已打开](assets/offer_inbound_fallback_example_005.png)

1. 选择 **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]** 选项。

   ![如果未在优惠空间中选择任何已识别的个人选项，则回退到匿名环境](assets/offer_inbound_fallback_example_006.png)

1. 使用下拉列表，选择之前创建的匿名Web优惠空间（请参阅[为匿名环境配置优惠空间](#configuring-offer-spaces-for-the-anonymous-environment)）。

   ![为链接的匿名空间选择了Web合作伙伴匿名的匿名优惠空间下拉列表](assets/offer_inbound_fallback_example_007.png)

### 指定已标识的选件空间的高级设置 {#specifying-the-advanced-settings-of-the-identified-offer-spaces}

在此示例中，联系人识别是根据Adobe Campaign数据库中的电子邮件地址进行的。 要将收件人电子邮件添加到空间，请应用以下流程：

1. 在已识别的环境中，转到选件空间文件夹。
1. 选择&#x200B;**最佳选件**&#x200B;选件空间，然后单击&#x200B;**[!UICONTROL Advanced parameters]**。

   ![使用高级参数链接打开“目标识别”选项卡](assets/offer_inbound_fallback_example_044.png)的Web最佳优惠已识别空间

1. 在 **[!UICONTROL Target identification]** 选项卡中，单击 **[!UICONTROL Add]**。

   ![高级参数带有键路径](assets/offer_inbound_fallback_example_046.png)的“添加”按钮的“目标标识”选项卡

1. 单击&#x200B;**[!UICONTROL Edit expression]**，转到收件人表并选择&#x200B;**[!UICONTROL Email]**&#x200B;字段。

   ![在选择了Email字段的收件人表上编辑表达式字段选择器](assets/offer_inbound_fallback_example_047.png)

1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;以关闭&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;窗口并完成配置&#x200B;**最佳选件**&#x200B;选件空间。
1. 对&#x200B;**合作伙伴**&#x200B;优惠空间应用相同的进程。

   ![Web合作伙伴已识别在“高级参数”“目标识别”选项卡中设置了@email键路径的空间](assets/offer_inbound_fallback_example_048.png)

### 在已识别的环境中创建优惠类别 {#creating-offer-categories-in-an-identified-environment}

我们将创建两个单独的类别：**最佳优惠**&#x200B;类别和&#x200B;**合作伙伴**&#x200B;类别，每个类别具有两个个性化优惠。

1. 转到已识别环境中的&#x200B;**[!UICONTROL Offer catalogs]**&#x200B;节点。
1. 与匿名环境中一样，添加两个具有&#x200B;**最佳选件**&#x200B;和&#x200B;**合作伙伴**&#x200B;的&#x200B;**[!UICONTROL Offer category]**&#x200B;文件夹作为标签。

   ![环境 — 包含最佳选件和合作伙伴类别的收件人设计树，镜像访客环境](assets/offer_inbound_fallback_example_009.png)

### 创建个性化优惠 {#creating-personalized-offers}

我们希望为每个类别创建两个个性化选件，即四个选件。

1. 转到&#x200B;**最佳优惠**&#x200B;类别并创建第一个个性化优惠。

   ![使用新选件(emptyOffer)模板的已识别最佳选件类别中的新选件对话框，为最佳选件添加标签#1](assets/offer_inbound_fallback_example_011.png)

1. 转到&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡，并根据其应用程序上下文指定优惠的权重。

   ![第一个确定的最佳优惠的资格选项卡，其权重为Neobank主页和银行页面](assets/offer_inbound_fallback_example_012.png)

1. 转到&#x200B;**[!UICONTROL Content]**&#x200B;选项卡并定义选件的内容。

   个性化最佳优惠的![内容选项卡，标题为Neobank银行帐户和Neobank客户优惠](assets/offer_inbound_fallback_example_013.png)

1. 在&#x200B;**最佳优惠**&#x200B;类别中创建第二个优惠。

   Neobank Home Insurance第二个个性化最佳优惠的![内容选项卡，现有客户可退款](assets/offer_inbound_fallback_example_014.png)

1. 转到&#x200B;**合作伙伴**&#x200B;类别并创建个性化优惠。

   个性化合作伙伴优惠的![内容选项卡，标题为“Excursion”，Neobank客户可享受20%的折扣](assets/offer_inbound_fallback_example_015.png)

1. 转到&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡，并根据其应用程序上下文指定优惠的权重。

   Neobank主页中权重为5的合作伙伴旅行优惠的![资格选项卡](assets/offer_inbound_fallback_example_016.png)

1. 为&#x200B;**合作伙伴**&#x200B;类别创建第二个选件。

   第二个Partner选件Neo Weekly的![Content选项卡，为Neobank客户提供50%的折扣](assets/offer_inbound_fallback_example_017.png)

1. 转到&#x200B;**[!UICONTROL Eligibility]**&#x200B;选项卡，应用与应用于此类别中第一个选件的权重相同的权重，以便这些选件在网站上连续显示。
1. 运行每个优惠的审批周期以开始更新它们。 在内容审批期间，激活&#x200B;**合作伙伴**&#x200B;或&#x200B;**最佳优惠**&#x200B;优惠空间。

### 在网页上配置优惠空间 {#configuring-offer-spaces-on-the-web-page}

Neobank公司的网站有三个优惠空间：两个用于&#x200B;**最佳优惠**&#x200B;类别中与银行相关的优惠，另一个用于&#x200B;**合作伙伴**&#x200B;类别中的优惠。

![已登录用户的Neobank主页，该用户具有两个最佳优惠框架和一个特殊优惠中的合作伙伴优惠框架](assets/offer_inbound_fallback_example_038.png)

要在网站的HTML页面上配置这些选件空间，请应用以下流程：

1. 在HTML页面的内容中，插入三个

   具有@id属性的元素，其值允许我们在网站的各种选件空间中调用选件。

   ![HTML页面源，其中div ContBO1、ContBO2和ContPtn定义了三个优惠空间](assets/offer_inbound_fallback_example_039.png)

1. 然后插入用于定义属性值的脚本。

   ![用于定义ContBO1、ContBO2和ContPtn的interactionDiv及其空格和类别的脚本](assets/offer_inbound_fallback_example_040.png)

   在此示例中，**ContBO1**&#x200B;和&#x200B;**ContBO2**&#x200B;接收值&#x200B;**OsWebBestOfferIdentified**，即先前在已识别环境中创建的&#x200B;**最佳选件**&#x200B;选件空间的内部名称。 **CatBestOffer**&#x200B;和&#x200B;**CatBestOfferAnonym**&#x200B;值与匿名环境和已识别环境的&#x200B;**最佳优惠**&#x200B;类别的内部名称匹配。

   ![已识别和匿名环境的最佳优惠空间OSWebBestOfferIdentified和最佳优惠类别](assets/offer_inbound_fallback_example_041.png)

   同样，**ContPtn**&#x200B;接收&#x200B;**OSWebPartnerIdentified**&#x200B;值，该值与在已识别环境中创建的&#x200B;**Partner**&#x200B;优惠空间的内部名称匹配。 **CatPartner**&#x200B;和&#x200B;**CatPartnerAnonym**&#x200B;与匿名环境和已识别环境的&#x200B;**Partner**&#x200B;类别的内部名称匹配。

   ![脚本中的合作伙伴空间OSWebPartnerIdentified和CatPartner和CatPartnerAnonym类别值](assets/offer_inbound_fallback_example_042.png)

1. 将可让您识别登录到Neobank网站的用户的信息分配给&#x200B;**interactionTarget**&#x200B;变量。

   ![interactionTarget变量设置为页面脚本中登录人员的电子邮件](assets/offer_inbound_fallback_example_043.png)

   人员的身份可以基于浏览器Cookie、URL中的阅读参数、电子邮件或人员的标识符。 如果使用主键以外的收件人表字段，则需要在空间的高级参数中定义该字段（请参阅[指定已识别优惠空间的高级设置](#specifying-the-advanced-settings-of-the-identified-offer-spaces)）。

1. 插入调用URL。

   ![使用env=EnvNeobankIdnRecip（已识别的环境内部名称）对interactionProposal.js进行脚本调用](assets/offer_inbound_fallback_example_049.png)

   URL包含&#x200B;**EnvNeobankIdnRecip**，已识别环境的内部名称。

打开网页时，脚本允许您调用交互引擎，以在网页的相关空间中显示选件的内容。 在对Adobe Campaign服务器的单个调用中，引擎会确定环境、选件空间和要选择的类别。

在此示例中，引擎识别了已识别的环境(**EnvNeobankIdnRecip**)。 它标识了网页上第一个和第二个优惠空间的优惠空间(**OSWebBestOfferIdentified**)和&#x200B;**最佳优惠**&#x200B;类别(**CatBestOffer**)，以及网站上第三个优惠空间的(**OSWebPartnerIdentified**)优惠空间和&#x200B;**Partner**&#x200B;类别(**CatPartner**)。

如果引擎无法识别收件人，则它会切换到已识别优惠空间中引用的匿名优惠空间，并切换到脚本中指定的匿名类别（**CatPartner**&#x200B;和&#x200B;**CatPartnerAnonym**）。
