---
product: campaign
title: 投放
description: 進一步瞭解預設傳遞工作流程
feature: Workflows
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 6%

---


# 投放{#deliveries}



以下詳述的工作流程會隨 **傳遞** 模組（預設）。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">报告聚合</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> 此工作流程會更新報告中使用的彙總。 預設會每天凌晨2:00觸發。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">付费</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> 此工作流程會透過電子郵件將系統活動報告傳送給「帳單」操作員。 預設會於每月25日觸發。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">別名清除</span> <br /> </td> 
   <td> <span class="uicontrol">aliasCleaning</span> <br /> </td> 
   <td> 此工作流程會將列舉值標準化。 預設會每天凌晨3:00觸發。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">可投放性更新</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> 此工作流程可讓您建立退信限定規則清單，以及平台中的網域和MX清單。 此工作流程僅適用於HTTPS連線埠開啟的情況。 除非安裝傳遞能力模組，否則不會更新這些清單。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">数据库清理</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> <p>此工作流程是資料庫維護工作流程：它會根據統計資料和程式進行不同的計算，並根據Deployment Assistant中定義的設定從資料庫刪除過時的資料。 預設會每天凌晨4:00觸發。</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">暫停的工作流程清理</span> <br /> </td> 
   <td> <span class="uicontrol">cleanupPausedWorkflows</span> <br /> </td> 
   <td> <p>此工作流程會分析嚴重程度設定為正常的暫停工作流程，並在暫停太久時觸發警告和通知。 一個月後，暫停的技術工作流程會無條件停止。 預設會每週一早上5:00觸發。</p> <p>如需詳細資訊，請參閱處理暫停的工作流程</a>.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">優惠通知</span> <br /> </td> 
   <td> <span class="uicontrol">offerMgt</span> <br /> </td> 
   <td> 此工作流程會將核准的優惠方案部署至線上環境，以及優惠方案目錄中包含的每個類別。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">预测</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> 此工作流程會分析臨時行事曆中儲存的傳遞（建立臨時記錄）。 預設會每天凌晨1:00觸發。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">跟踪</span> <br /> </td> 
   <td> <span class="uicontrol">追蹤</span> <br /> </td> 
   <td> 此工作流程會執行追蹤資訊的復原與合併。 此外，還可確保重新計算追蹤和傳遞統計資料，尤其是訊息中心封存工作流程所使用的資料。 預設會每小時觸發一次。 <br /> </td> 
  </tr> 
 </tbody> 
</table>

