---
product: campaign
title: 消息中心（控制）
description: 消息中心（控制）
feature: Workflows
role: User
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---


# 消息中心（控制）{#message-center-control}

下面详细介绍的工作流计划每小时运行一次。 默认情况下，它与&#x200B;**消息中心 — Control**&#x200B;模块一起安装。


<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 消息中心&lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;外部帐户名称&gt;<br /> </td> 
   <td> 此工作流：<br /> 
    <ul> 
     <li> <p>恢复操作处理的事件列表。</p> </li> 
     <li> <p>与NmsBroadLogMsg表同步，以恢复投放消息资格。</p> </li> 
     <li> <p>与NmsBroadLogMsg表的同步完成后，立即恢复事件投放日志。</p> </li> 
     <li> <p>与NmsTrackingUrl表同步，以恢复对投放URL的跟踪。</p> </li> 
     <li> <p>与NmsTrackingUrl表的同步完成后，立即恢复事件跟踪URL。</p> </li> 
     <li> <p>用于在发送投放后，每三小时恢复一次所有被隔离的电子邮件地址。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

