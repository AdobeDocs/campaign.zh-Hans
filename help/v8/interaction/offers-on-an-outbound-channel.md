---
product: campaign
title: 出站渠道产品建议
description: 出站渠道产品建议
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
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
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 1%
---
# 出站渠道产品建议{#offers-on-an-outbound-channel}



## 电子邮件选件投放 {#email-offer-delivery}

在我们的数据库中，有一类前往非洲的旅行优惠。 已配置每个优惠的资格、上下文和表示形式。 现在，我们要创建一个营销活动，通过电子邮件展示我们的优惠。

1. 创建营销活动和定位工作流。

   ![非洲之旅活动的定位工作流：文件夹、投放、重复数据删除和两个列表更新活动](assets/offer_delivery_example_001.png)

1. 编辑电子邮件投放并单击&#x200B;**[!UICONTROL Offers]**&#x200B;图标。

   ![电子邮件投放，带有“选件”图标以打开“选件管理”窗口、选件选择选项和“选件空间”字段](assets/offer_delivery_example_002.png)

1. 为优惠环境选择与假日匹配的电子邮件空间。

   ![选件管理窗口，其中选件空间列表显示可用的电子邮件空间，包括订阅者历程](assets/offer_delivery_example_003.png)

1. 选择包含非洲旅行优惠的类别。

   ![优惠管理窗口，在“优惠目录和历程，非洲”类别下展开类别树](assets/offer_delivery_example_004.png)

1. 将投放中的选件数设置为2。

   ![类别为“非洲”且每条消息的建议数设置为2](assets/offer_delivery_example_005.png)的优惠管理窗口

1. 关闭选件管理窗口并创建投放内容。

   ![电子邮件投放HTML内容编辑器，默认包含视图，可随时提出优惠建议](assets/offer_delivery_example_006.png)

1. 使用菜单插入第一个优惠建议并选择HTML渲染函数。

   ![HTML内容工具栏菜单：建议，然后建议1，渲染函数和HTML渲染](assets/offer_delivery_example_007.png)

1. 插入第二个优惠建议。

   ![在取消订阅链接之前，通过电子邮件发送包含渲染/html视图的行的HTML内容](assets/offer_delivery_example_008.png)

1. 单击&#x200B;**[!UICONTROL Preview]**&#x200B;以预览投放中的优惠，然后选择收件人以预览其接收优惠。

   ![“投放预览”选项卡，显示选定收件人的电子邮件标题、文本和图像，横穿撒哈拉](assets/offer_delivery_example_009.png)

1. 保存投放并启动定向工作流。
1. 打开您的投放，然后单击投放的&#x200B;**[!UICONTROL Audit]**&#x200B;选项卡：您可以看到优惠引擎已从目录中的各种优惠中选择要提出的主张。

   ![投放审核选项卡日志列出每个选件生成的建议，如金字塔和撒哈拉选件](assets/offer_delivery_example_010.png)

## 执行优惠模拟 {#perform-an-offer-simulation}

1. 在&#x200B;**[!UICONTROL Profiles and Targets]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Simulations]**&#x200B;链接，然后单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮。

   ![使用“创建”按钮的“模拟”列表，打开包含模板、标签和文件夹的“新建选件模拟”对话框](assets/offer_simulation_001.png)

1. 选择标签并根据需要指定执行设置。

   ![带有标签1年订阅者、Simulations文件夹和执行设置的新优惠模拟对话框](assets/offer_simulation_example_002.png)

1. 保存模拟。 然后，该操作将在新选项卡中打开。

   ![具有“编辑”选项卡和“开始”模拟按钮的1年订阅者的模拟仪表板](assets/offer_simulation_example_003.png)

1. 单击&#x200B;**[!UICONTROL Edit]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Scope]**。

   ![模拟编辑选项卡，范围部分，带有环境或类别、优惠空间、主题、联系日期和建议](assets/offer_simulation_example_004.png)

1. 选择要模拟优惠的类别。

   ![在“优惠 — 设计和优惠”目录下展开的环境或类别列表，并选择了旅行类别](assets/offer_simulation_example_005.png)

1. 选择要用于模拟的优惠空间。

   ![旅行类别下的优惠空间列表，提供直邮和电子邮件（环境 — 收件人）](assets/offer_simulation_example_006.png)

1. 输入有效日期。 您必须至少输入开始日期。 这允许优惠引擎筛选优惠，并选择在给定日期有效的优惠。
1. 如有必要，请指定一个或多个主题，以将选件数量限制为设置中包含此关键字的选件。

   在我们的示例中，**Travel**&#x200B;类别包含两个子类别，这两个子类别具有两个单独的主题。 我们希望对主题为&#x200B;**客户>1年**&#x200B;的优惠运行模拟。

   ![在旅行类别的“主题”字段中输入了客户> 1年主题的“范围”部分](assets/offer_simulation_example_007.png)

1. 选择要定位的收件人。

   ![目标选择筛选器向导选择收件人列表，然后选择频繁旅行者列表](assets/offer_simulation_example_008.png)

1. 配置要发送给每个收件人的优惠数量。

   在我们的示例中，选件引擎将选择每个收件人具有最高权重的3个选件。

   ![建议数设置为3的范围节，以及特殊优惠传递列表上的目标查询](assets/offer_simulation_example_009.png)

1. 保存设置，然后单击&#x200B;**[!UICONTROL Dashboard]**&#x200B;选项卡中的&#x200B;**[!UICONTROL Start]**&#x200B;以运行模拟。

   ![仪表板开始模拟对话框要求确认，并突出显示“确定”按钮](assets/offer_simulation_example_010.png)

1. 模拟完成后，请参阅&#x200B;**[!UICONTROL Results]**&#x200B;以了解每个选件的建议详细细分。

   在我们的示例中，优惠引擎将优惠划分基于3个建议。

   ![模拟结果选项卡，按选件划分建议：群体大小30，建议数30](assets/offer_simulation_example_011.png)

1. 显示&#x200B;**[!UICONTROL Breakdown of offers by rank]**&#x200B;以查看选件引擎选择的选件列表。

   ![按等级划分的优惠报表，其中包含“美国之旅”和“探索法国”的优惠等级表以及饼图](assets/offer_simulation_example_012.png)

1. 如有必要，您可以通过单击&#x200B;**[!UICONTROL Start simulation]**&#x200B;来更改范围设置并再次运行模拟。

   ![仪表板开始模拟对话框要求确认，并突出显示“确定”按钮](assets/offer_simulation_example_010.png)

1. 要保存模拟数据，请使用报告中提供的历史记录或导出函数。

   ![使用“导出”菜单和突出显示的保存图标按排名划分优惠报表](assets/offer_simulation_example_013.png)
