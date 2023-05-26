---
product: campaign
title: LINE 渠道
description: LINE 渠道
feature: Workflows
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 13%

---


# LINE 渠道{#line-channel}

下面详述的工作流将随 **LINE渠道** 默认模块。 有关此模块的更多信息，请参阅 [此页面](../../v8/send/line.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">LINE V2访问令牌更新</span> <br /> </td> 
   <td> <span class="uicontrol">updateLineV2AccessToken</span> <br /> </td> 
   <td> 此工作流将刷新对LINE V2的访问令牌。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">删除被阻止的LINE用户</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> 此工作流可确保在LINE V2用户阻止LINE官方帐户180天后删除这些用户数据。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">MID到LineUserID迁移</span> <br /> </td> 
   <td> <span class="uicontrol">MIDToUserIDMigration</span> <br /> </td> 
   <td> 此工作流会生成LINE V2用户的ID，以便从LINE V1迁移到LINE V2。<br /> </td> 
  </tr> 
 </tbody> 
</table>

