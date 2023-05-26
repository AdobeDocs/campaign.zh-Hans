---
product: campaign
title: 营销活动
description: 营销活动
feature: Workflows
topic-tags: technical-workflows
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 4%

---


# 营销活动{#campaign}

下面详述的工作流将随 **Campaign** 默认模块。

>[!CAUTION]
>
>为了在营销活动级别执行营销活动进程，必须启动这些工作流。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">成本计算</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span> <br /> </td> 
   <td> 此工作流会开始计算预算、计划、方案、营销策划、投放和任务中的费用和成本行。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">库存：订单和警报</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> 此工作流可启动订单行上的库存计算，并管理警告警报阈值。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">营销活动中投放的作业</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> 此工作流会触发已批准的投放，并开始后处理外部投放的服务提供程序。 它还会发送批准通知和提醒。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">营销活动作业</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> 此工作流用于管理营销活动（启动项定位、文件提取等）的作业。 它还创建与循环和定期活动相关的工作流。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">服务提供商上的作业</span> <br /> </td> 
   <td> <span class="uicontrol">supplierMgt</span> <br /> </td> 
   <td> 在投放获得批准后，此工作流将开始处理提供商（通过电子邮件发送到路由器并进行后处理）。 <br /> </td> 
  </tr> 
 </tbody> 
</table>

