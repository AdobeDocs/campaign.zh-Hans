---
title: 投放状态
description: 了解有关投放仪表板上可用的状态的更多信息
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 3%

---

# 投放状态 {#delivery-statuses}

发送投放后，投放仪表板会显示一个状态，允许您监测发送是否成功。 可能的状态详见下节。

![](assets/delivery-status.png)

有关您可以遇到的不同投放失败以及如何解决这些失败的更多详细信息，请参阅[了解投放失败](delivery-failures.md)。

**相关主题：**

* [发送和监控电子邮件](send.md)
* [了解投放失败](delivery-failures.md)
* [可投放性入门](about-deliverability.md)

## 投放状态列表 {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> 状态<br /> </th> 
   <th> 定义和解决方案<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已发送<br /> </td> 
   <td> 传递正确发送到消息提供程序（但收件人不一定收到它）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已忽略<br /> </td> 
   <td> 由于收件人地址错误，该投放未发送给收件人。 该文件被阻止列表、隔离、未提供或重复。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失败<br /> </td> 
   <td> 例如，由于地址无效或收件箱已满，投放无法到达收件人。 它还可能链接到个性化块的问题，因为它们可能会在架构与投放映射不匹配时生成错误。 请参阅<a href="delivery-failures.md" target="_blank">了解投放失败</a><br /> </td> 
  </tr>
  <tr> 
   <td> 挂起<br /> </td> 
   <td> 投放已准备好发送，将由投放服务器(MTA)处理。 查看<a href="#pending-status" target="_blank">待处理状态</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 不适用<br /> </td> 
   <td> 服务器(MTA)已考虑该投放，但未处理。<br /> </td> 
  </tr>  
  <tr> 
   <td> 投放已取消<br /> </td> 
   <td> 操作员已取消投放。<br /> </td> 
  </tr> 
  <tr> 
   <td> 服务提供商<br />已考虑 </td> 
   <td> 对于SMS投放，SMS服务提供商会收到投放。<br />对于电子邮件投放，消息已成功从Campaign中继到MTA（邮件传输代理）。</td> 
  </tr> 
  <tr> 
   <td> 已在移动设备<br />上收到 </td> 
   <td> 收件人在其移动设备上收到了SMS。<br /> </td> 
  </tr>
  <tr> 
   <td> 已发送给服务提供商<br /> </td> 
   <td> 传递已发送到SMS服务提供程序，但尚未收到。<br />
   </td> 
  </tr> 
  <tr> 
   <td> 已准备<br /> </td> 
   <td> 仅用于外部连接器（如移动渠道）的中间状态。 它遵循“挂起”状态，是确定以下状态的外部连接器。<br /> </td> 
  </tr> 
 </tbody> 
</table>

要了解如何优化Adobe Campaign电子邮件的可投放性，请参阅[此部分](about-deliverability.md)。 有关投放能力的更深入探讨，请参阅[Adobe投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans)。

## 待处理状态 {#pending-status}

确认投放后，您可以看到投放状态为&#x200B;**[!UICONTROL Pending]**。 此状态表示执行进程正在等待某些资源的可用性。

**[!UICONTROL Pending]**&#x200B;状态可能首先意味着您的投放已计划并处于待处理状态，直到给定日期为止。 有关更多信息，请参阅[计划投放发送](configure-and-send.md#schedule-delivery-sending)部分。

如果未发送您的投放且其状态仍为&#x200B;**[!UICONTROL Pending]**，则可能是以下原因所致：

* **同时运行的营销活动过多**

  在&#x200B;**[!UICONTROL NmsOperation_LimitConcurrency]**&#x200B;选项中定义了同时营销活动的限制。 默认值为 10。

  作为托管Cloud Services用户，您可以根据需要使用Adobe调整此限制。 请参阅[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html){target="_blank"}以了解有关选项的更多信息。

* **资源可用性问题**

  MTA（邮件传输代理）在处理您的投放之前可能正在等待资源变为可用。

>[!NOTE]
>
>作为Campaign v8托管云服务用户，MTA基础架构由Adobe进行监视和管理。 如果您遇到与待处理投放有关的持续问题，请联系Adobe客户关怀团队。

**相关主题：**

* [发送和监控电子邮件](send.md#email-monitoring)
* [了解投放失败](delivery-failures.md)
* [监控Campaign环境](../start/monitor.md#monitor-deliveries)

