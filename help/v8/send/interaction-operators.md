---
title: Campaign互动运算符
description: 创建选件管理运算符
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 391eac2f5e4d4c8c5d4dadd3394798361640e1d8
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# 操作员配置文件 {#operator-profiles}

两种类型的运算符可以使用Campaign交互：**选件管理器**&#x200B;和&#x200B;**投放管理器**。 每个权限和限制都是特定的。 在[此页面](../start/permissions.md)中了解有关Campaign操作员和权限的更多信息。

* **[!UICONTROL Offer manager]**&#x200B;会创建并维护选件。
* **[!UICONTROL Delivery manager]**&#x200B;批准并使用选件

## 创建选件管理器运算符{#offer-manager}

1. 创建运算符。

   ![](../assets/do-not-localize/book.png) 有关在Campaign中创建运算符的详细步骤，请参 [阅Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 转到&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，单击&#x200B;**[!UICONTROL Add]**&#x200B;并选择&#x200B;**[!UICONTROL Offer manager]**&#x200B;组。

分配给选件管理器的权限使他们能够执行以下任务：

* 修改&#x200B;**[!UICONTROL Design]**&#x200B;环境。
* 查看&#x200B;**[!UICONTROL Live]**&#x200B;环境。
* 配置管理功能（预定义空格和过滤器）。
* 创建和更改类别。
* 创建选件。
* 配置选件资格。
* 批准选件。

如果在工作流中使用选件，则必须将运算符添加到&#x200B;**[!UICONTROL Administrator]**&#x200B;或&#x200B;**[!UICONTROL Offer managers]**&#x200B;运算符组中才能执行工作流。

>[!NOTE]
>
>**选件** 管理器仅在未指定审核者或在选件模板中声明为审核者时才批准选件。

## 创建投放管理器运算符 {#delivery-manager}

1. 创建运算符。

   ![](../assets/do-not-localize/book.png) 有关在Campaign中创建运算符的详细步骤，请参 [阅Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 转到&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，单击&#x200B;**[!UICONTROL Add]**&#x200B;并选择&#x200B;**[!UICONTROL Delivery manager]**&#x200B;组。

分配给投放管理器的权限使他们能够执行以下任务：

* 显示&#x200B;**[!UICONTROL Live]**&#x200B;环境。
* 显示和修改选件类别。
* 审核选件（如果它们是审核者）。

   >[!NOTE]
   >
   >**只有** 在选件配置中声明为审核者时，交付管理者才能批准选件。

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
   <td> 正在编辑的选件/ Live选件<br /> </td> 
   <td> 读/写<br /> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> Recipient - Environment<br /> </td> 
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
   <td> 预定义选件过滤器<br /> </td> 
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
   <td> 选件目录<br /> </td> 
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
   <td> 正在编辑的选件/ Live选件<br /> </td> 
   <td> </td> 
   <td> 读取<br /> </td> 
  </tr> 
  <tr> 
   <td> Recipient - Environment<br /> </td> 
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
   <td> 预定义选件过滤器<br /> </td> 
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
   <td> 选件目录<br /> </td> 
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
