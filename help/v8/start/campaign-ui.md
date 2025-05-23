---
title: 了解Campaign用户界面
description: 了解如何浏览和使用Campaign用户界面
feature: Overview
role: User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 9d5a2ca1e9858a727377b8afa6bdd7e3761c1b56
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 8%

---

# 探索用户界面 {#ui-client-console}

您可以通过客户端控制台或Web用户界面访问Adobe Campaign。 您还可以使用API在Campaign平台中管理数据和执行任务。

>[!CAUTION]
>
>本文档重点介绍Campaign客户端控制台用法。 如果您使用的是Campaign Web用户界面，请参阅[本文档](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=zh-Hans){target="_blank"}。

* **客户端控制台** - Campaign客户端控制台是一个本机应用程序，它通过标准Internet协议(如SOAP和HTTP)与Adobe Campaign应用程序服务器进行通信。 Campaign客户端控制台集中了所有功能和设置，并且由于依赖本地缓存，因此需要的带宽最少。 Campaign客户端控制台专为轻松部署而设计，可从互联网浏览器部署并自动更新，无需任何特定的网络配置，因为它只生成HTTP(S)流量。 [了解详情](#ui-access)

  在[本节](../start/connect.md)中了解如何安装和配置Campaign客户端控制台。

* **Web用户界面** — 作为Campaign v8用户，从v8.6.1版本开始，您现在可以通过Adobe Experience Cloud中央用户界面访问Web环境。 然后，您可以从Web浏览器连接到Adobe Campaign。 通过这个新的界面，您可以创建、管理和执行重要的营销行动。 但是，并非所有Campaign功能都可用。 [了解详情](#ac-web-ui)。

  >[!AVAILABILITY]
  >
  >Campaign Web用户界面仅适用于通过Adobe ID连接到Adobe Campaign的用户。 了解有关[AdobeIdentity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"}的更多信息。
  >

* **Web访问** - Adobe Campaign Web访问功能允许您使用HTML用户界面通过Web浏览器访问Campaign功能的子集。 使用此Web界面可访问报告、控制和验证消息、访问监控功能板等。  在本节[&#128279;](../start/connect.md#web-access)中了解有关Campaign Web Access 的更多信息。

* **API** — 为了解决更多用例，可以使用通过SOAP协议公开的Web服务API从外部应用程序调用系统。 在此页面[&#128279;](../dev/api.md)中了解有关Campaign API 的更多信息。


## 使用客户端控制台 {#ui-access}

Campaign客户端控制台是一个本机应用程序，它通过标准Internet协议(如SOAP和HTTP)与Adobe Campaign应用程序服务器进行通信。 Campaign客户端控制台集中了所有功能和设置，并且由于依赖本地缓存，因此需要的带宽最少。 Campaign客户端控制台专为轻松部署而设计，可从互联网浏览器部署并自动更新，无需任何特定的网络配置，因为它只生成HTTP(S)流量。  [了解有关Campaign客户端控制台的更多信息](../start/connect.md)。 您可以从客户端控制台主页的专用卡切换到Campaign Web用户界面。

![](assets/web-ui.png)


>[!NOTE]
>
>如果未显示新的访问卡，请确保您的Adobe Experience Cloud外部帐户中的以下字段不留空： **服务器**、**租户**、**回拨服务器**&#x200B;和&#x200B;**关联标记**。


您还可以使用Web浏览器访问Campaign。 在这种情况下，仅有一组Campaign功能可用。 [了解详情](#web-browser)

### 浏览界面 {#ui-browse}

连接到Campaign客户端控制台后，即可访问主页。 浏览链接以访问功能。 界面中可用的功能集取决于您的选项和权限。

从主页的中心部分，使用链接访问Campaign帮助材料、社区和支持网站。 使用中心卡浏览新的Campaign Web用户界面和Campaign控制面板。

浏览上方部分的选项卡以访问Campaign关键功能：

![](assets/overview-home.png)

>[!NOTE]
>
>您可以访问的核心功能列表取决于您的权限和实施情况。

对于每个功能，您都可以访问&#x200B;**[!UICONTROL Browsing]**&#x200B;部分中的一组关键功能。 通过&#x200B;**[!UICONTROL More]**&#x200B;链接，可访问所有其他组件。

例如，在浏览到&#x200B;**[!UICONTROL Profiles and targets]**&#x200B;选项卡时，您可以访问收件人列表、订阅服务、现有的定位工作流以及创建所有这些组件的快捷方式。

![](assets/overview-list.png)

在屏幕中选择元素时，该元素将加载到新选项卡中，以便您轻松浏览内容。

![](assets/new-tab.png)

### 创建元素 {#create-an-element}

使用屏幕左侧&#x200B;**[!UICONTROL Create]**&#x200B;部分中的快捷方式添加新元素。 您还可以使用列表上方的&#x200B;**[!UICONTROL Create]**&#x200B;按钮向当前列表添加新元素。

例如，在投放页面上，使用&#x200B;**[!UICONTROL Create]**&#x200B;按钮创建新投放。

![](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

[Learn more about Campaign web access](../start/connect.md#web-access).-->

### 访问Campaign资源管理器 {#ac-explorer-ui}

浏览Campaign Explorer以访问所有Adobe Campaign功能和设置。

![](assets/explorer.png)

此工作区允许您访问资源管理器树以浏览所有功能和选项。

* 左侧部分显示Campaign Explorer树，并允许您根据权限浏览实例的所有组件和设置。 您可以添加和自定义文件夹，如[此页面](../audiences/folders-and-views.md)中所述。

* 上半部分显示当前文件夹中的记录列表。 这些列表是完全可自定义的。 [了解详情](../config/ui-settings.md)

* 下面的部分显示所选记录的详细信息。


## Campaign Web用户界面 {#ac-web-ui}

作为Campaign v8客户端控制台用户，从v8.6.1版本开始，您现在可以通过Adobe Experience Cloud中央用户界面访问Web环境。 Experience Cloud 是 Adobe 的数字营销应用程序、产品和服务的集成系列。通过其直观的界面，您可以快速访问云应用程序、产品功能和服务。

![Adobe Campaign Web用户界面主页](assets/ac-web-home.png)

>[!AVAILABILITY]
>
>Campaign Web用户界面仅适用于通过Adobe ID连接到Adobe Campaign的用户。 了解有关[AdobeIdentity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"}的更多信息。
>

在[本文档](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=zh-Hans){target="_blank"}中进一步了解新的Campaign Web用户界面。 您还可以访问Campaign Web用户界面文档中的[常见问题解答页面](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/start/faq){target="_blank"}。

其他高级功能、配置和设置仅在客户端控制台中可用。 在Campaign Web用户界面文档[&#128279;](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html?lang=zh-Hans){target="_blank"}中了解有关两种用户界面中可用功能的更多信息。


## 支持的语言 {#languages}

支持的语言取决于用户界面。

* 对于Campaign v8客户端控制台界面，支持的语言包括：

   * 英语（英国）
   * 英语（美国）
   * 法语
   * 德语
   * 日语


  >[!CAUTION]
  >
  >语言在安装过程中选择，此后无法更改。

* 有关Campaign Web用户界面支持的语言，[请参阅此页面](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html?lang=zh-Hans#language-pref){target="_blank"}。


语言会影响日期和时间格式。

美式英语和英式英语的主要差别如下：

<table> 
 <thead> 
  <tr> 
   <th> 格式<br /> </th> 
   <th> 英语（美国）<br /> </th> 
   <th> 英语(EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 日期<br /> </td> 
   <td> 星期从星期日开始<br /> </td> 
   <td> 星期从星期一<br />开始 </td> 
  </tr> 
  <tr> 
   <td> 简短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>示例：09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>示例：25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> 具有时间的简短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>例如：2018年9月25日10:47:25下午</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>例如： 2018年9月25日22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
