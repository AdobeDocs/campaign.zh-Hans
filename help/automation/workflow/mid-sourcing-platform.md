---
product: campaign
title: 中间源平台
description: 中间源平台
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
source-git-commit: 8a7bf8408d15e0bd9e1c3e72f7846bf9a79c6885
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 1%
---

# 中间源平台{#mid-sourcing-platform}



默认情况下，下面详细介绍的工作流随&#x200B;**中间源平台**&#x200B;模块一起安装。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">传递指示器</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryIndicators</span> <br /> </td> 
   <td> 此工作流可更新投放的投放跟踪指示器。 默认情况下，此工作流每小时触发一次。<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>中间源服务器上的日志保留期必须长于投放有效期加上&#x200B;**indicatorsDuration**&#x200B;值。 否则，在清除旧日志时，投放指标会减少，并且较低的值会同步到营销实例。 例如，如果有效期为5天，**indicatorsDuration**&#x200B;为30天，则将保留期设置为至少36天。
