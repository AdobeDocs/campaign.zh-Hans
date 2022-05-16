---
title: 操作员配置文件
description: 创建选件管理运算符
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# 操作员配置文件 {#operator-profiles}

两种类型的运算符可以使用Campaign交互： **选件经理** 和 **投放管理器**. 每个权限和限制都是特定的。 进一步了解Campaign操作员和 [本页](../start/permissions.md).

* 的 **[!UICONTROL Offer manager]** 创建和维护选件。
* 的 **[!UICONTROL Delivery manager]** 批准和使用选件

## 创建选件管理器运算符{#offer-manager}

1. 创建运算符。

   ![](../assets/do-not-localize/book.png) 有关在Campaign中创建运算符的详细步骤，请参见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 转到 **[!UICONTROL Groups and named rights]** 窗口，单击 **[!UICONTROL Add]** ，然后选择 **[!UICONTROL Offer manager]** 群组。

分配给选件管理器的权限使他们能够执行以下任务：

* 修改 **[!UICONTROL Design]** 环境。
* 查看 **[!UICONTROL Live]** 环境。
* 配置管理功能（预定义的空格和过滤器）。
* 创建和更改类别。
* 创建选件。
* 配置选件资格。
* 批准选件。

如果在工作流中使用选件，则必须将运算符添加到 **[!UICONTROL Administrator]** 或 **[!UICONTROL Offer managers]** 操作员组。

>[!NOTE]
>
>**选件经理** 只有未指定审核者，或在选件模板中声明为审核者时，才能批准选件。

## 创建投放管理器运算符 {#delivery-manager}

1. 创建运算符。

   ![](../assets/do-not-localize/book.png) 有关在Campaign中创建运算符的详细步骤，请参见 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 转到 **[!UICONTROL Groups and named rights]** 窗口，单击 **[!UICONTROL Add]** ，然后选择 **[!UICONTROL Delivery manager]** 群组。

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
   <td> 分类<br /> </td> 
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
   <td> 选件类别<br /> </td> 
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
   <td> 分类<br /> </td> 
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
   <td> 选件类别<br /> </td> 
   <td> </td> 
   <td> 读取<br /> </td> 
  </tr> 
 </tbody> 
</table>
