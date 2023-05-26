---
title: 探索Campaign工作区
description: 了解如何浏览和使用Campaign工作区
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 20%

---

# 了解Campaign用户界面

## 访问Campaign UI{#ui-access}

Campaign 工作区可通过[客户端控制台](../architecture/general-architecture.md)使用。

了解如何在中安装和配置Campaign客户端控制台 [本节](../start/connect.md).

![](assets/home-page.png)

您还可以使用Web浏览器访问Campaign。 在此上下文中，仅有一组Campaign功能可用。 [了解详情](#web-browser)

## 浏览UI{#ui-browse}

连接到Campaign后，即可访问主页。 浏览链接以访问功能。 UI中可用的功能集取决于您的选项和权限。

从主页的中心部分，使用链接访问Campaign帮助材料、社区和支持网站。

使用上半部分的选项卡浏览Campaign关键功能：

![](assets/overview-home.png)

>[!NOTE]
>
>您可以访问的核心功能列表取决于您的权限和实施情况。

对于每个功能，您可以访问 **[!UICONTROL Browsing]** 部分。 此 **[!UICONTROL More]** 通过链接，可访问所有其他组件。

例如，在浏览到 **[!UICONTROL Profiles and targets]** 选项卡中，您可以访问收件人列表、订阅服务、现有的定位工作流以及创建所有这些组件的快捷方式。

![](assets/overview-list.png)

在屏幕中选择元素时，该元素将加载到一个新选项卡中，以便您轻松浏览内容。

![](assets/new-tab.png)

## 创建元素 {#create-an-element}

在中使用快捷键 **[!UICONTROL Create]** 部分，以添加新元素。 您还可以使用 **[!UICONTROL Create]** 按钮来向当前列表添加新元素。

例如，在投放页面上，使用 **[!UICONTROL Create]** 按钮创建新的投放。

![](assets/new-recipient.png)

## 使用Web浏览器 {#web-browser}

您还可以通过Web浏览器访问Campaign功能的子集。

Web访问界面类似于控制台界面。 在浏览器中，您可以使用与控制台中相同的导航和显示功能，但您只能在营销策划上执行一组缩减的操作。 例如，您可以查看和取消营销活动，但无法修改营销活动。

![](../assets/do-not-localize/glass.png) [了解有关Campaign Web访问的更多信息](../start/connect.md#web-access).

## 访问Campaign Explorer {#ac-explorer-ui}

浏览Campaign Explorer以访问所有Adobe Campaign功能和设置。

![](assets/explorer.png)

此工作区允许您访问资源管理器树以浏览所有功能和选项。

* 左侧部分显示Campaign Explorer树，并允许您根据权限浏览实例的所有组件和设置。 您可以添加和自定义文件夹，如中所述 [此页面](../audiences/folders-and-views.md).

* 上半部分显示当前文件夹中的记录列表。 这些列表是完全可自定义的。 [了解详情](../config/ui-settings.md)

* 下面的部分显示所选记录的详细信息。

## 语言{#languages}

Campaign v8 用户界面提供以下语言版本：

* 英语（英国）
* 英语（美国）
* 法语
* 德语
* 日语

在安装过程中选择语言。

>[!CAUTION]
>
>创建实例后，无法更改语言。

语言会影响日期和时间格式。

美式英语和英式英语的主要差别如下：

<table> 
 <thead> 
  <tr> 
   <th> 格式<br /> </th> 
   <th> 英语（美国）<br /> </th> 
   <th> 英式英语<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 日期<br /> </td> 
   <td> 一周从星期日开始<br /> </td> 
   <td> 一周从星期一开始<br /> </td> 
  </tr> 
  <tr> 
   <td> 短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>示例：09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>示例：25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> 带时间的短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>例如：2018年9月25日10:47:下午25</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>例如：2018年9月25日22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
