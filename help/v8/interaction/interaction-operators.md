---
title: 操作员配置文件
description: 创建选件管理运算符
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: eed3396584940f99a865eef2358887b6bf5c4936
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 8%

---

# 操作员配置文件 {#operator-profiles}

两种类型的运算符可以使用Campaign交互： **选件经理** 和 **投放管理器**. 每个权限和限制都是特定的。 进一步了解Campaign操作员和 [本页](../start/gs-permissions.md).

* 的 **[!UICONTROL Offer manager]** 创建和维护选件。
* 的 **[!UICONTROL Delivery manager]** 批准和使用选件

## 创建选件管理器运算符{#offer-manager}

1. 创建运算符。 [了解详情](../start/manage-permissions.md#add-users)
1. 浏览到 **[!UICONTROL Groups and named rights]** 窗口，单击 **[!UICONTROL Add]** ，然后选择 **[!UICONTROL Offer manager]** 群组。

描述了与选件管理器关联的权限 [此处](../start/manage-permissions.md#ootb-productprofiles)

## 创建投放管理器运算符 {#delivery-manager}

1. 创建运算符。 [了解详情](../start/manage-permissions.md#add-users)
1. 浏览到 **[!UICONTROL Groups and named rights]** ，单击 **[!UICONTROL Add]** ，然后选择 **[!UICONTROL Delivery manager]** 群组。

分配给投放管理器的权限使他们能够执行以下任务：

* 显示 **[!UICONTROL Live]** 环境。
* 显示和修改选件类别。
* 审核选件（如果它们是审核者）。

   >[!NOTE]
   >
   >**投放管理器** 只有在选件配置中声明为审阅人时，才能批准选件。

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
   <td> 正在编辑的选件/实时选件<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> Recipient — 环境<br /> </td> 
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
   <td> 预定义的选件过滤器<br /> </td> 
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
   <td> <strong>投放管理器（实时环境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>树结构级别</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在编辑的选件/实时选件<br /> </td> 
   <td> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> Recipient — 环境<br /> </td> 
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
   <td> 预定义的选件过滤器<br /> </td> 
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
