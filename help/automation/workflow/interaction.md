---
product: campaign
title: 交互
description: 交互
feature: Workflows, Interaction
role: User, Admin
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 3%

---


# 交互{#interaction}

默认情况下，下面详细介绍的工作流与&#x200B;**选件引擎（交互）**&#x200B;加载项一起安装。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">完全聚合计算（propositionrcp多维数据集）</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> 此工作流更新<strong>优惠建议</strong>多维数据集的<strong>完整</strong>聚合。 默认情况下，此工作流于每日早上6点触发。 此聚合可捕获以下维度：渠道、投放、营销选件和日期。<br /> <strong>优惠建议</strong>多维数据集随后用于根据优惠生成报告。<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter完全聚合计算</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> 此工作流更新<strong>消息中心</strong>多维数据集的<strong>完整</strong>聚合。 默认情况下，此工作流于每日凌晨3点触发。 此聚合捕获以下维度：渠道、日期、状态和事件类型。<br /> <strong>消息中心</strong>多维数据集随后用于根据事件生成报告。<br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

在[本节](../../v8/reporting/gs-cubes.md)中了解有关多维数据集和聚合的详细信息。

