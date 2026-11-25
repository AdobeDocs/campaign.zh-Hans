---
product: campaign
title: 关于产品建议模拟
description: 关于产品建议模拟
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
exl-id: facaa88e-1fa2-4189-9d8f-348aaef3e235
TQID: 'https://experienceleague.adobe.com/034-CFbQIFVm9QiSpDyRHlVsIrF46NSqKMwp-Gm3-mc'
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 2%
---
# 关于产品建议模拟{#about-offers-simulation}



使用&#x200B;**Simulation**&#x200B;模块，您可以在向收件人发送建议之前测试属于某个类别或某个环境的选件分布。

模拟会考虑以前应用于优惠的上下文和资格规则(请参阅[优惠目录概述](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/offers/interaction-offer-catalog){target="_blank"} （Campaign v8文档）)及其呈现规则（请参阅[管理优惠呈现](managing-offer-presentation.md)）。 这样，您就可以测试和优化各种版本的优惠建议，而无需实际使用优惠或过度/缺征询目标，因为模拟对目标收件人没有影响。

要了解如何模拟优惠，请阅读以下步骤。

![播放视频](assets/how-to-video.png)您还可以观看此[视频](https://helpx.adobe.com/campaign/classic/how-to/simulate-offer-in-acv6.html?playlist=/ccx/v1/collection/product/campaign/classic/segment/digital-marketers/explevel/intermediate/applaunch/introduction/collection.ccx.js&ref=helpx.adobe.com)。

## 创建模拟的主要步骤 {#main-steps-for-creating-a-simulation}

要运行优惠模拟，请应用以下步骤：

1. 在&#x200B;**[!UICONTROL Profiles and Targets]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Simulations]**&#x200B;链接，然后单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮。

   ![使用“创建”按钮的“模拟”列表，打开包含模板、标签和文件夹的“新建选件模拟”对话框](assets/offer_simulation_001.png)

1. 保存并编辑刚刚创建的模拟。
1. 转到&#x200B;**[!UICONTROL Edit]**&#x200B;选项卡并指定执行设置。

   有关详细信息，请参阅[执行设置](execution-settings.md)。

   ![模拟常规选项卡，执行设置：低活动计划、SQL日志记录和优先级列表](assets/offer_simulation_003.png)

   >[!NOTE]
   >
   >执行设置仅在与Campaign使用交互时才可用。

1. 指定模拟范围。

   有关详细信息，请参阅作用域[&#128279;](simulation-scope.md#definition-of-the-scope)的定义。

   ![包含环境、优惠空间、联系日期、建议和“文件夹最佳旅行者”目标的“模拟范围”选项卡](assets/offer_simulation_004.png)

1. 添加报告轴以增强&#x200B;**[!UICONTROL Offer distribution by rank]**&#x200B;报告（可选）。

   有关详细信息，请参阅[添加报告轴](simulation-scope.md#adding-reporting-axes)。

   ![模拟计算选项卡，具有目标上和选件上的报告轴，以及添加按钮](assets/offer_simulation_005.png)

1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;以记录模拟设置。
1. 通过仪表板开始模拟。

   ![突出显示开始模拟按钮的模拟仪表板](assets/offer_simulation_006.png)

1. 检查仿真结果并显示分析报告。

   有关详细信息，请参阅[模拟跟踪](simulation-tracking.md)。

   ![结果选项卡和按排名列出的优惠细分报告，带有优惠排名表和饼图](assets/offer_simulation_007.png)
