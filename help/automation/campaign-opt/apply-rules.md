---
product: campaign
title: 应用分类规则
description: 了解如何应用类型规则
feature: Typology Rules
exl-id: 4ec3bbe1-fc4c-4b1e-989c-f4dcf8ee8d5e
source-git-commit: a8568e0c1e9af11b533b7d435691dc12cc0a2485
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 8%

---

# 应用分类规则{#applying-rules}

## 将分类应用于投放 {#apply-a-typology-to-a-delivery}

要应用您创建的分类规则，请将其关联到分类，然后在投放中引用此分类。

为此请执行以下操作步骤：

1. 创建活动类型。

   可通过访问分类 **[!UICONTROL Administration > Campaign Management > Typology management]** > **[!UICONTROL Typologies]** Campaign资源管理器的文件夹。

1. 转到 **[!UICONTROL Rules]** 选项卡，单击 **[!UICONTROL Add]** 按钮选择要应用于此分类的规则。

   ![](assets/campaign_opt_pressure_sample_1_6.png)

1. 保存分类：是否将其添加到现有分类的列表。
1. 打开要应用规则的投放。
1. 浏览到投放属性并打开 **[!UICONTROL Typology]** 选项卡。
1. 在下拉列表中选择分类。

   ![](assets/campaign_opt_pressure_sample_1_7.png)

   >[!NOTE]
   >
   >可以在投放模板中定义分类，以自动应用至使用此模板创建的所有投放。

## 定义申请条件 {#define-application-conditions}

您可以根据需要限制规则的应用字段（控制规则除外）。

可以配置分类规则，使其仅涉及与之关联的特定投放，或投放目标中的特定收件人。

要定义规则的应用条件，请单击 **[!UICONTROL Edit the rule application conditions...]** 中的链接 **[!UICONTROL General]** 选项卡。

然后，使用查询编辑器定义筛选条件。 在以下示例中，容量规则仅涉及标签中带有“offer”一词的投放或在2013年4月1日之前创建的投放。

![](assets/campaign_opt_create_capacity_criterion.png)

>[!NOTE]
>
>对于筛选规则，您可以选择筛选标准的应用条件：它们可以取决于投放或投放大纲。 [了解详情](filtering-rules.md#condition-a-filtering-rule)。

## 调整计算频率 {#adjust-calculation-frequency}

通过数据库清理工作流，仲裁每晚自动重新执行。 但是，可以保存超出此期限的值。

事实上，有些计算使用的值不会每天更改。 因此，每天重新计算数据并毫无意义地让数据库过载是无关紧要的。 例如，如果某个流程用客户倾向得分每周一次地丰富营销数据库并购买信息，则无需每天重新计算基于这些值的数据。

要执行此操作， **[!UICONTROL Frequency]** 字段 **[!UICONTROL General]** 选项卡允许您定义保存定位的最长时段。 默认情况下，值 **0** 指示在下次执行每日重新仲裁之前计算保持有效。

要保存此时间段之后的结果，请在 **[!UICONTROL Frequency]** 字段：此期限过期后，将重新应用所有规则。

此 **[!UICONTROL Re-apply the rule at the start of personalization]** 选项允许您在个性化阶段自动应用规则，包括 **[!UICONTROL Frequency]** 字段仍然有效。

## 选择规则应用阶段 {#selecting-the-rule-application-phase}

在投放的定位、分析和个性化阶段中，按特定顺序应用分类规则。

### 执行顺序 {#execution-order}

在标准操作模式下，按以下顺序应用规则：

1. 控制规则（如果在开始定向时应用）。
1. 筛选规则：

   * 地址限定的本机应用程序规则：定义的地址/未验证的地址/阻止列表上的地址/隔离的地址/地址质量。
   * 筛选用户定义的规则。
   * 地址或标识符上的重复数据删除规则（如有必要，应用）。

1. 压力规则。
1. 容量规则。
1. 控制规则（如果在定向结束时应用）。
1. 控制规则（如果在开始个性化时应用）。 如果用户规则（过滤/压力/电容）已过期且需要重新计算，则在此步骤中应用这些规则。
1. 控制规则（如果在个性化结束时应用）。

>[!NOTE]
>
>如果您使用的是Campaign交互模块，则在应用优惠资格规则的同时应用筛选规则（适用于投放大纲中的优惠），或者在个性化阶段调用优惠引擎期间应用优惠资格规则。

您可以使用中的相应字段调整具有相同类型的规则的执行顺序 **[!UICONTROL General]** 选项卡中。 在同一消息处理阶段执行多个规则时，您可以在以下位置配置其执行顺序： **[!UICONTROL Execution sequence]** 字段。

例如，执行顺序为20的压力规则在执行顺序为30的压力规则之前执行。

### 控制规则 {#control-rules}

对象 **[!UICONTROL Control]** 规则，您可以决定应用规则的投放生命周期的哪个阶段：定位之前或之后、个性化开始时、分析结束时。 在的下拉列表中选择要应用的值 **[!UICONTROL Phase]** 字段，在 **[!UICONTROL General]** 类型规则的选项卡。

![](assets/campaign_opt_define_control_phase.png)

可能的值包括：

* **[!UICONTROL At the start of targeting]**

  要防止在发生错误时执行个性化步骤，您可以在此处应用控制规则。

* **[!UICONTROL After targeting]**

  如果需要知道目标的体积以应用控制规则，请选择此阶段。

  例如， **[!UICONTROL Check proof size]** 控制规则在每个定位阶段之后应用：如果验证收件人过多，此规则将阻止消息个性化。

* **[!UICONTROL At the start of personalization]**

  如果控制与批准报文个性化相关，则必须选择此阶段。 在分析阶段执行消息个性化。

* **[!UICONTROL At the end of the analysis]**

  如果检查要求完成消息个性化，请选择此阶段。

## 其他配置 {#additional-configurations}

### 控制传出SMTP流量 {#control-outgoing-smtp-traffic}

作为一个选项，您可以使用 **[!UICONTROL Managing affinities with IP addresses]** 用于将投放链接到此关联性的投放服务器(MTA)的字段。 这样，您就可以限制向计算机或输出地址投放特定内容的电子邮件数量。

![](assets/campaign_opt_select_ip_affinity.png)

>[!NOTE]
>
>关联管理不适用于 **[!UICONTROL Filtering]** 类型。

<!--
>Affinities are defined in the instance configuration file, on the Adobe Campaign server. For more on this, refer to [this section](../../installation/using/about-initial-configuration.md).-->

### 活动优化和分布式营销 {#campaign-optimization-and-distributed-marketing}

此 **[!UICONTROL Distributed Marketing]** 选项卡允许您定义在订购和/或保留共享营销活动时应用的类型和/或规则的重新映射。 为本地实体定义的类型/规则（链接到为中央实体定义的类型/规则）替换链接到中央实体的规则/类型。 通过重新映射，可将中央实体规则调整为适合订购营销活动的本地实体。

![](assets/simu_campaign_opti_distrib_mkg.png)

>[!NOTE]
>
>在类型和类型规则中， **[!UICONTROL Distributed Marketing]** 如果您的许可包含此选项，则会添加选项卡：请检查您的许可协议。\
>有关分布式营销的详细信息，请参阅 [本节](../distributed-marketing/about-distributed-marketing.md).
