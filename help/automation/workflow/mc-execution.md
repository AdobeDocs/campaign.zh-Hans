---
product: campaign
title: 消息中心（执行）
description: 消息中心（执行）
feature: Workflows
role: User
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 2%
---

# 消息中心（执行）{#message-center-execution}

下面详细介绍的工作流默认与&#x200B;**消息中心 — 执行**&#x200B;加载项一起安装。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新事件状态</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> 利用此工作流，可为事件分配状态。 事件状态如下： <br /> 
    <ul> 
     <li> <p><strong>挂起</strong>：事件在队列中。 尚未为其关联任何消息模板。</p> </li> 
     <li> <p><strong>待处理投放</strong>：事件在队列中，已为其关联消息模板，该投放当前正在处理该消息模板。</p> </li> 
     <li> <p><strong>已发送</strong>：此状态复制于投放日志。 这意味着投放已发送。</p> </li> 
     <li> <p><strong>被投放忽略</strong>：此状态复制于投放日志。 这意味着该投放已被忽略。</p> </li> 
     <li> <p><strong>投放错误</strong>：此状态复制于投放日志。 这意味着投放已失败。</p> </li> 
     <li> <p><strong>事件未被覆盖</strong>：该事件未能与消息模板相关联。 将不会重新处理该事件。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">正在处理批次事件</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> 利用此工作流，可在将批量事件与消息模板关联之前将其放入队列中。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">正在处理实时事件</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> 通过此工作流，在将实时事件与消息模板关联之前，您可以先将它们放入队列中。<br /> </td> 
  </tr> 
 </tbody> 
</table>

