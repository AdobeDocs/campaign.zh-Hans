---
title: 操作员配置文件
description: 创建选件管理操作员
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# 操作员配置文件 {#operator-profiles}

两种类型的操作员可以使用Campaign交互： **优惠经理**&#x200B;和&#x200B;**投放经理**。 每个用户都有特定的权限和限制。 在[此页面](../start/gs-permissions.md)中了解有关Campaign操作员和权限的更多信息。

* **[!UICONTROL Offer manager]**&#x200B;创建和维护选件。
* **[!UICONTROL Delivery manager]**&#x200B;批准和使用优惠

## 创建优惠管理器运算符{#offer-manager}

1. 创建运算符。 [了解详情](../start/manage-permissions.md#add-users)
1. 浏览到&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，单击&#x200B;**[!UICONTROL Add]**&#x200B;并选择&#x200B;**[!UICONTROL Offer manager]**&#x200B;组。

[此处](../start/manage-permissions.md#ootb-productprofiles)介绍了与选件管理器关联的权限

## 创建投放管理器操作员 {#delivery-manager}

1. 创建运算符。 [了解详情](../start/manage-permissions.md#add-users)
1. 浏览到&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;选项卡，单击&#x200B;**[!UICONTROL Add]**&#x200B;并选择&#x200B;**[!UICONTROL Delivery manager]**&#x200B;组。

分配给投放经理的权限允许他们执行以下任务：

* 显示&#x200B;**[!UICONTROL Live]**&#x200B;环境。
* 显示和修改优惠类别。
* 批准选件（如果选件是审阅者）。

  >[!NOTE]
  >
  >**投放经理**&#x200B;只能在优惠配置中声明为审阅者时批准优惠。

## 每个交互运算符的权限矩阵 {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>选件管理器（设计环境）</strong><br /> </td> 
   <td> <strong>选件管理器（实时环境）</strong><br /> </td> 
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
   <td> 收件人 — 环境<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 空间<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 预定义优惠过滤器<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 类型<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 类型规则<br /> </td> 
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
   <td> <strong>投放管理器（正式启用）</strong><br /> </td> 
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
   <td> 收件人 — 环境<br /> </td> 
   <td> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 空间<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 预定义优惠过滤器<br /> </td> 
   <td> 读取<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 类型<br /> </td> 
   <td> 读取<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> 类型规则<br /> </td> 
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
