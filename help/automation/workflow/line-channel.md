---
product: campaign
title: LINE 渠道
description: LINE 渠道
feature: Workflows, Line App
role: User
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 27%

---


# LINE 渠道{#line-channel}

下面详细介绍的工作流将随 **LINE渠道** 默认模块。 有关此模块的更多信息，请参阅 [此页面](../../v8/send/line.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">LINE V2 访问令牌更新</span> <br /> </td> 
   <td> <span class="uicontrol">updateLineV2AccessToken</span> <br /> </td> 
   <td> 此工作流将刷新对LINE V2的访问令牌。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">删除阻止的 LINE 用户</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> 此工作流可确保在阻止LINE正式帐户180天后，删除LINE V2用户的数据。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">MID 到 LineUserID 迁移</span> <br /> </td> 
   <td> <span class="uicontrol">MIDToUserIDMigration</span> <br /> </td> 
   <td> 此工作流会生成LINE V2用户ID，以便从LINE V1迁移到LINE V2。<br /> </td> 
  </tr> 
 </tbody> 
</table>

