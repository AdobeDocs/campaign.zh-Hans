---
product: campaign
title: 单元格
description: 单元格
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 2%

---

# 单元格{#cells}

的 **[!UICONTROL Cells]** 活动提供了各种子集作为数据列的视图。 它有助于处理子集，而且还设计为利用个性化功能。

![](assets/wf_split_cells.png)

此活动可配置为根据用户需求输入特定参数。 默认情况下，每个子集的详细信息会通过 **[!UICONTROL Cells]** 和 **[!UICONTROL Advanced]** 选项卡。

![](assets/wf_split_cells_with_customization.png)

在以下示例中，输入表单已修改：a **[!UICONTROL Data]** 选项卡，以启用选件的关联和每个子集的优先级。

![](assets/cells-activity-sample.png)

对于此配置，在工作流表单的 **[!UICONTROL Administration > Configurations > Input forms]** Adobe Campaign explorer节点：

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

Adobe Campaign中的输入表单个性化是专家用户保留的内容。 有关更多信息，请参阅此。
