---
product: campaign
title: 消息中心（执行）
description: 消息中心（执行）
feature: Workflows
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 8%

---


# 消息中心（执行）{#message-center-execution}

下面详述的工作流随 **消息中心 — 执行** 默认情况下为加载项。

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
   <td> 利用此工作流，可为事件分配状态。 事件状态如下所示：<br /> 
    <ul> 
     <li> <p><strong>待定</strong>:事件在队列中。 尚未关联消息模板。</p> </li> 
     <li> <p><strong>待定投放</strong>:事件在队列中，消息模板已与其关联，且投放当前正在处理该事件。</p> </li> 
     <li> <p><strong>已发送</strong>:此状态复制于投放日志。 这意味着投放已发送。</p> </li> 
     <li> <p><strong>被投放忽略</strong>:此状态复制于投放日志。 这意味着投放已被忽略。</p> </li> 
     <li> <p><strong>投放错误</strong>:此状态复制于投放日志。 这意味着投放失败。</p> </li> 
     <li> <p><strong>未涵盖的事件</strong>:事件未能与消息模板关联。 将不会重新处理该事件。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">处理批处理事件</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> 利用此工作流，可在将批处理事件与消息模板关联之前，先将它们放入队列中。 <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">处理实时事件</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> 利用此工作流，可在将实时事件与消息模板关联之前，将它们放入队列中。 <br /> </td> 
  </tr> 
 </tbody> 
</table>

