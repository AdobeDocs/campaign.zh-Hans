---
solution: Campaign
product: Adobe Campaign
title: 活动 Interaction运算符
description: 创建优惠管理运营商
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---


# 运算符用户档案{#operator-profiles}

两种类型的运算符可以使用活动交互：**优惠管理器**&#x200B;和&#x200B;**投放管理器**。 每个应用程序都具有特定权限和限制。 了解有关[本页](../start/permissions.md)中活动运算符和权限的更多信息。

* **[!UICONTROL Offer manager]**&#x200B;创建并维护优惠。
* **[!UICONTROL Delivery manager]**&#x200B;批准并使用优惠

## 创建优惠管理器运算符{#offer-manager}

1. 创建新运算符。

:arrow_upper_right:在活动中创建运算符的步骤详见[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 转到&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，单击&#x200B;**[!UICONTROL Add]**&#x200B;并选择&#x200B;**[!UICONTROL Offer manager]**&#x200B;组。

分配给优惠经理的权限使他们能够执行以下任务:

* 修改&#x200B;**[!UICONTROL Design]**&#x200B;环境。
* 视图&#x200B;**[!UICONTROL Live]**&#x200B;环境。
* 配置管理功能(预定义的空格和过滤器)。
* 创建和更改类别。
* 创建优惠。
* 配置优惠资格。
* 批准优惠。

请注意，如果工作流中使用了优惠，则需要将运算符添加到&#x200B;**[!UICONTROL Administrator]**&#x200B;或&#x200B;**[!UICONTROL Offer managers]**&#x200B;运算符组以执行工作流。

>[!NOTE]
>
>**优惠管理器**&#x200B;只能在未指定审阅者时批准优惠，或者在优惠所基于的优惠模板中声明为审阅者时批准。

## 创建投放管理器运算符{#delivery-manager}

1. 创建新运算符。

:arrow_upper_right:在活动中创建运算符的步骤详见[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 转到&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，单击&#x200B;**[!UICONTROL Add]**&#x200B;并选择&#x200B;**[!UICONTROL Delivery manager]**&#x200B;组。

分配给投放经理的权限可以/允许他们执行以下任务:

* 显示&#x200B;**[!UICONTROL Live]**&#x200B;环境。
* 显示和修改优惠类别。
* 如果指定优惠为审核者之一，则批准审核。

   >[!NOTE]
   >
   >**投放管理器**&#x200B;只有在优惠配置期间被声明为审阅者时才能批准优惠。

## 每个Interaction运算符的权限矩阵{#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>优惠管理器（设计环境）</strong><br /> </td> 
   <td> <strong>优惠管理器（实时环境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>树结构级别</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在编辑的优惠/实时优惠<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人 - 环境<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 空格<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 预定义的优惠过滤器<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 类型学<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 分类规则<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠目录<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠类别<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>投放管理器（设计环境）</strong><br /> </td> 
   <td> <strong>投放管理器(Live env.)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>树结构级别</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在编辑的优惠/实时优惠<br /> </td> 
   <td> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人 - 环境<br /> </td> 
   <td> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 空格<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 预定义的优惠过滤器<br /> </td> 
   <td> 读取<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 类型学<br /> </td> 
   <td> 读取<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 分类规则<br /> </td> 
   <td> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠目录<br /> </td> 
   <td> 读取<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 优惠类别<br /> </td> 
   <td> </td> 
   <td> 读取<br /> </td> 
  </tr> 
 </tbody> 
</table>
