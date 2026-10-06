---
product: campaign
title: 传输到中间源
description: 了解有关传输到中间源工作流的更多信息
feature: Workflows
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 1%
---

# 传输到中间源{#transfer-to-mid-sourcing}

默认情况下，下面详述的工作流随&#x200B;**传输到中间源**&#x200B;模块一起安装。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>内部名称</strong><br /> </td> 
   <td> <strong>说明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">中间源（投放计数器）</span> <br /> </td> 
   <td> <span class="uicontrol">defaultMidSourcingDlv</span> <br /> </td> 
   <td> <p>此工作流收集中间源服务器上投放的计数信息。 计数信息包括常规投放指标，如已发送的投放数量等。</p> <p>不包括打开等跟踪信息。</p> <p>默认情况下，每10分钟触发一次。</p> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">中间源（投放日志）</span> <br /> </td> 
   <td> <span class="uicontrol">defaultMidSourcingLog</span> <br /> </td> 
   <td> 此工作流在中间源服务器上收集投放日志。 默认情况下每小时触发一次。<br /> </td> 
  </tr> 
 </tbody> 
</table>

