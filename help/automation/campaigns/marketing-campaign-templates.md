---
product: campaign
title: 营销活动模板
description: 营销活动模板
feature: Campaigns, Templates
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 1bd8d3e7-aaa9-4e00-96bb-0d30614ab380
TQID: 'https://experienceleague.adobe.com/qmz-Sd1EJmACFfgozVirCHCaeiQN-lGKuxd9-VAPMHs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: baf8e746-117b-5e73-b179-0a83edc0295f
    internal-label: Templates
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1331'
ht-degree: 3%
---
# 创建和配置营销活动模板 {#campaign-templates}

所有营销活动都基于存储主要特性和功能的模板。 Campaign附带创建营销活动的内置模板。 此模板启用了所有功能：文档、种子地址、批准、投放概述等。

可用功能取决于您的权限、插件以及Adobe Campaign平台的配置。


>[!NOTE]
>
>单击主页上的&#x200B;**[!UICONTROL Explorer]**&#x200B;图标时，将显示树。

提供了内置模板以用于创建尚未定义特定配置的活动。 您可以创建和配置活动模板，然后从这些模板创建活动。

## 创建活动模板 {#create-a-campaign-template}

要创建营销活动模板，请执行以下步骤：

1. 打开Campaign **资源管理器**，并浏览至&#x200B;**资源>模板>营销活动模板**。
1. 单击模板列表上方工具栏中的&#x200B;**新建**。

![活动模板列在“资源”>“模板”下，工具栏中突出显示“新建”按钮。](assets/campaign-template-node.png)

您还可以&#x200B;**复制**&#x200B;内置模板以重复使用并调整其配置。 为此，请右键单击模板并选择&#x200B;**复制**。

1. 输入新活动模板的标签。
1. 单击&#x200B;**保存**&#x200B;并重新打开模板。
1. 在&#x200B;**编辑**&#x200B;选项卡中，定义模板属性。
1. Select **高级促销活动参数……**&#x200B;链接，用于向促销活动模板添加工作流。

   ![新的营销活动模板“编辑”选项卡，其中高亮显示了“高级营销活动参数”链接。](assets/campaign-template-parameters.png)

1. 将&#x200B;**定位和工作流**&#x200B;值更改为&#x200B;**是**，然后确认。 了解如何在[模块类型](#typology-of-enabled-modules)中添加功能。
1. **定位和工作流**&#x200B;选项卡已添加到模板。 单击&#x200B;**添加工作流……**，输入&#x200B;**标签**，然后单击&#x200B;**确定**。
1. 根据需要创建工作流。

   ![模板的“定位和工作流”选项卡，其工作流包含查询和读取列表，可导致电子邮件投放。](assets/campaign-template-create-wf.png)

1. 单击&#x200B;**保存**。 您的模板现在已准备好用于创建新营销活动。

营销活动模板的各种选项卡和子选项卡允许您访问其设置，如[常规配置](#general-configuration)中所述。

## Select模块 {#select-modules}

通过&#x200B;**[!UICONTROL Advanced campaign parameters...]**&#x200B;链接，您可以基于此模板为营销活动启用和禁用作业。 要在基于此模板创建的营销活动中启用的Select功能。

![高级设置配置选项卡列出了值为“是”或“否”的每个功能；支出和目标为“否”。](assets/campaign-template-select-modules.png)

如果未选择某个功能，则将与进程有关的元素（菜单、图标、选项、选项卡、子选项卡等） 不会显示在模板的界面中或基于此模板的营销活动中。 营销活动详细信息左侧的选项卡，以及可用的选项卡，与模板中选择的功能一致。 例如，**费用和目标**&#x200B;功能未启用，相应的&#x200B;**[!UICONTROL Budget]**&#x200B;选项卡未显示在基于此模板的营销活动中。

此外，配置窗口的快捷方式已添加到营销活动仪表板。 启用某个功能后，可通过直接链接从Campaign仪表板访问该功能。

### 配置示例

* 例如，具有以下设置：

  ![高级设置：将控制组、种子地址和文档设置为“是”；将审批、定位和工作流程设置为“否”](assets/campaign-template-select-functionalities.png)

  营销活动仪表板显示：

  ![仅包含“仪表板”和“编辑”选项卡的Campaign仪表板，以及添加投放和添加文档链接。](assets/campaign-template-dashboard-sample-1.png)

  请注意，**[!UICONTROL Targeting and workflows]**&#x200B;选项卡缺失。

  可以使用以下功能：

  ![具有“属性”、“文档”和“审核”节且没有“预算”节的营销活动的“编辑”选项卡。](assets/campaign-template-edit-sample-1.png)

  请注意，**[!UICONTROL Budget]**&#x200B;选项卡缺失。

  Campaign高级设置也反映此配置。

  ![Campaign高级设置，带有控制人口和种子地址选项卡，但没有审批选项卡。](assets/campaign-template-parameters-sample-1.png)

  请注意，**[!UICONTROL Approvals]**&#x200B;选项卡不可用。

* 使用此配置：
  ![高级设置：审批、定位和工作流、费用和目标设置为“是”；其他功能否](assets/campaign-template-dashboard-sample-2.png)

  营销活动仪表板显示：

  ![包含“定位和工作流”选项卡和“添加投放”链接但未添加“文档”链接的“营销活动”仪表板。](assets/campaign-template-select-functionalities-2.png)

  请注意，**[!UICONTROL Targeting and workflows]**&#x200B;选项卡可用，但缺少&#x200B;**添加文档**&#x200B;链接。

  可以使用以下功能：

  ![编辑选项卡，并打开预算节，显示相关的预算、目标以及成本和费用选项卡。](assets/campaign-template-edit-sample-2.png)

  请注意，**[!UICONTROL Budget]**&#x200B;选项卡可用。

  Campaign高级设置也反映此配置。

  ![具有“审批”选项卡和“作业验证”的高级设置，没有“控制填充”或“种子地址”选项卡。](assets/campaign-template-parameters-sample-2.png)

  请注意，**[!UICONTROL Approvals]**&#x200B;选项卡可用，但未启用&#x200B;**[!UICONTROL Control population]**&#x200B;和&#x200B;**[!UICONTROL Seed addresses]**&#x200B;选项卡。


## 模块类型 {#typology-of-enabled-modules}

* **对照组**

  选择此模块后，模板的高级设置以及基于此模板的营销活动会添加一个附加选项卡。 可以通过模板定义配置，也可以单独为每个营销活动定义配置。 了解有关[营销活动投放](marketing-campaign-deliveries.md)中控制组的详细信息。

  ![高级设置的“控制群”选项卡，其中启用了“控制组”选项，且其配置有一个“编辑”链接。](assets/template-activate-1.png)


* **种子地址**

  选择此模块后，模板的高级设置以及基于此模板的营销活动会添加一个附加选项卡。 可以通过模板定义配置，也可以单独为每个营销活动定义配置。

  ![高级设置种子地址选项卡，带有导入种子模板链接和种子地址列表。](assets/template-activate-2.png)

* **文档**

  选择此模块后，模板的&#x200B;**[!UICONTROL Edit]**&#x200B;选项卡中会添加一个附加选项卡，以及基于此模板的营销活动。 可从模板添加附加文档，或单独为每个营销活动添加附加文档。 了解有关[营销活动投放](marketing-campaign-deliveries.md)中文档的更多信息。

  ![“编辑”选项卡的“文档”部分列出了附加文档，带有“添加”、“删除”和“详细信息”按钮。](assets/template-activate-3.png)

* **投放概要**

  选择此模块后，将在&#x200B;**[!UICONTROL Documents]**&#x200B;选项卡中添加一个&#x200B;**[!UICONTROL Delivery outlines]**&#x200B;子选项卡，以定义营销活动的投放大纲。 在[使用投放概要](marketing-campaign-assets.md#delivery-outlines)中了解有关投放概要的更多信息。

  ![包含“添加投放概要”链接的“文档”部分的投放概要子选项卡。](assets/template-activate-4.png)

* **定位和工作流**

  选择&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;模块后，将添加一个选项卡，允许您基于此模板为营销活动创建一个或多个工作流。 还可以根据此模板为每个营销活动单独配置工作流。了解有关[营销活动投放](marketing-campaign-deliveries.md)中的营销活动工作流的更多信息。

  ![使用工作流的“定位和工作流”选项卡：“查询和读取”列表，重复数据删除，然后移动投放。](assets/template-activate-5.png)

  启用此模块后，将向营销活动的高级设置添加一个&#x200B;**[!UICONTROL Jobs]**&#x200B;选项卡以定义流程执行顺序。

* **审批**

  如果启用&#x200B;**[!UICONTROL Approvals]**，则可以选择要批准的进程和负责批准的操作员。 在[Select审阅人](marketing-campaign-approval.md#select-reviewers)中了解有关审批的更多信息。

  ![高级设置的“批准”选项卡，其中启用了内容、目标、预算和提取批准，并分配了审阅人。](assets/template-activate-6.png)

  您可以通过模板高级设置部分的&#x200B;**[!UICONTROL Approvals]**&#x200B;选项卡选择是否启用流程审批。

* **费用和目标**

  选择此模块后，模板和基于此模板的营销活动的详细信息中将添加&#x200B;**[!UICONTROL Budget]**&#x200B;选项卡，以便选择关联的预算。

  ![具有相关预算字段的“编辑”选项卡的“预算”部分、具有成本行的“目标”和“成本”选项卡。](assets/template-activate-7.png)


## 模板属性 {#template-properties}

![打开了“操作类型”下拉列表的“活动模板编辑”选项卡，其中显示了“唯一”、“周期性”和“定期”。](assets/template-op-type.png)

创建活动模板时，需要输入以下信息：

* 输入模板的&#x200B;**标签**：标签是必需的，并且是基于此模板的所有营销活动的默认标签。
* 从下拉列表中Select促销活动&#x200B;**性质**。 此列表中的可用值是保存在&#x200B;**[!UICONTROL natureOp]**&#x200B;枚举中的值。

  了解如何在[管理枚举](../../v8/config/enumerations.md)中访问和配置您的枚举。

* Select营销活动&#x200B;**的**&#x200B;类型：唯一、定期或定期。 默认情况下，营销活动模板适用于独特营销活动。 在[创建循环和定期营销活动](recurring-periodic-campaigns.md)中详细介绍了循环和定期营销活动。
* 指定营销活动的持续时间，即营销活动将发生的天数。 基于此模板创建营销活动时，将自动填充营销活动开始和结束日期。

  如果促销活动是重复性的，则必须直接在模板中指定促销活动的开始和结束日期。

* 指定模板的&#x200B;**相关项目**：基于此模板的营销活动已链接到所选项目。

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.
-->
