---
product: campaign
title: 单元格
description: 单元格
feature: Workflows, Targeting Activity
role: User
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 2%

---

# 单元格{#cells}

此 **[!UICONTROL Cells]** 活动以数据列的形式提供各种子集的视图。 它有助于子集操作，并且还旨在利用个性化功能。

![](assets/wf_split_cells.png)

此活动可配置为根据用户需求输入特定参数。 默认情况下，每个子集的详细信息都会在专用窗口中通过 **[!UICONTROL Cells]** 和 **[!UICONTROL Advanced]** 选项卡。

![](assets/wf_split_cells_with_customization.png)

在下面的示例中，输入表单已修改： **[!UICONTROL Data]** 添加了选项卡，以启用选件与每个子集的优先级之间的关联。

![](assets/cells-activity-sample.png)

对于此配置，已将以下信息添加到工作流表单的 **[!UICONTROL Administration > Configurations > Input forms]** Adobe Campaign资源管理器节点：

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

Adobe Campaign中的输入表单个性化仅适用于专家用户。