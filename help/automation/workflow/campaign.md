---
product: campaign
title: 营销活动
description: 营销活动
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 3%
---

# 营销活动{#campaign}

默认情况下，下面详细介绍的工作流将与&#x200B;**Campaign**&#x200B;模块一起安装。

>[!CAUTION]
>
>为了在营销活动级别执行营销活动流程，必须启动这些工作流。

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
   <td> 此工作流开始计算预算、计划、方案、营销活动、投放和任务中的费用和成本行。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">库存：订单和警报</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> 此工作流在订单行上启动库存计算，并管理警告警报阈值。<br /> </td> 
  </tr> 
  <tr> 
   <td> 营销活动中的投放<span class="uicontrol">作业</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> 此工作流会触发批准的投放，并开始后处理外部投放的服务提供程序。 它还会发送批准通知和提醒。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">营销活动作业</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> 此工作流用于管理营销活动（启动项定位、文件提取等）的作业。 它还创建与循环和定期活动相关的工作流。<br /> </td> 
  </tr> 
  <tr> 
   <td> 服务提供者上的<span class="uicontrol">作业</span> <br /> </td> 
   <td> <span class="uicontrol">supplierMgt</span> <br /> </td> 
   <td> 在投放获得批准后，此工作流将开始处理提供程序（通过电子邮件发送到路由器并进行后处理）。<br /> </td> 
  </tr> 
 </tbody> 
</table>

