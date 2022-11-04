---
product: campaign
title: 互动
description: 互动
feature: Workflows, Interaction
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%

---


# 互动{#interaction}

下面详述的工作流随 **优惠引擎（交互）** 默认情况下为加载项。

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
   <td> 此工作流会更新 <strong>完整</strong> 聚合 <strong>优惠建议</strong> 多维数据集。 默认情况下，此工作流于每日早上6点触发。 此聚合会捕获以下维度：渠道、投放、营销选件和日期。<br /> 的 <strong>优惠建议</strong> 然后，使用多维数据集根据选件生成报表。<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter完整聚合计算</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> 此工作流会更新 <strong>完整</strong> 聚合 <strong>消息中心</strong> 多维数据集。 默认情况下，此工作流于每日凌晨3点触发。 此聚合会捕获以下维度：渠道、日期、状态和事件类型。<br /> 的 <strong>消息中心</strong> 然后，使用多维数据集生成基于事件的报告。 <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

了解有关 [此部分](../../v8/reporting/gs-cubes.md).

