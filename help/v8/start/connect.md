---
title: 连接到Campaign v8
description: 了解如何连接到 Adobe Campaign v8 并在您的计算机上安装控制台以便于访问。
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 13%

---

# 连接到Adobe Campaign v8{#gs-ac-connect}

要开始使用Campaign，您必须安装和配置客户端控制台。

Client Console是一个本机应用程序，它通过标准Internet协议(如Adobe Campaign和HTTP)与SOAP应用程序服务器进行通信。 Campaign客户端控制台集中了所有功能和设置，并且由于依赖本地缓存，因此需要的带宽最少。 Campaign客户端控制台专为轻松部署而设计，可从互联网浏览器部署并自动更新，无需任何特定的网络配置，因为它只生成HTTP(S)流量。

在开始之前，您需要：

* 在[兼容性矩阵](compatibility-matrix.md)中检查您的系统和工具与Adobe Campaign的兼容性
* 获取Campaign服务器URL
* 创建您的Adobe ID，或从您的公司获取您的用户凭据
* 在系统上安装Microsoft Edge Webview2运行时。 [了解详情](#webview)

## 安装客户端控制台{#download-ac-console}

### Microsoft Edge Webview2运行时 {#webview}

从Campaign Classic 8.4内部版本开始，任何客户端控制台都需要安装Microsoft Edge Webview 2运行时。

默认情况下，Web View作为Windows 11操作系统的一部分安装。 如果您的系统中不存在该软件包，Campaign Client Console安装程序将提示您从[Microsoft开发人员网站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_cn){target="_blank"}下载它。 请注意，下载链接在Internet Explorer 11浏览器上不起作用，因为Microsoft已弃用其支持。 确保使用其他浏览器来访问该链接。

### 下载控制台{#install-ac-console}

首次使用Campaign时，您需要下载并安装客户端控制台。

有两个选项可用于下载Client Console：

1. 作为Campaign管理员，连接到Adobe [软件分发](https://experience.adobe.com/#/downloads/content/software-distribution/cn/campaign.html){target="_blank"}。

1. 作为最终用户，您的Campaign管理员会为您部署客户端控制台，并通过专用URL提供该控制台。

下载Client Console安装程序后，将其安装到本地计算机上。

请注意，安装客户端控制台语言后，您无法对其进行更改。

## 创建连接{#create-your-connection}

安装Client Console后，请按照以下步骤创建与应用程序服务器的连接：

1. 启动Console并浏览右角的链接以访问连接配置屏幕。

1. 单击&#x200B;**[!UICONTROL Add > Connection]**&#x200B;并输入Adobe Campaign应用程序服务器的标签和URL。

1. 通过URL指定与Adobe Campaign应用程序服务器的连接。 使用计算机的DNS或别名或IP地址。

   例如，您可以使用`https://<machine>.<domain>.com`类型URL。

1. 选中选项&#x200B;**[!UICONTROL Connect with an Adobe ID]**。

1. 单击&#x200B;**[!UICONTROL Ok]**&#x200B;保存您的设置。

例如，您可以根据需要添加任意数量的连接，以连接到测试、暂存和生产环境。

>[!NOTE]
>
>通过&#x200B;**[!UICONTROL Add]**&#x200B;按钮可创建&#x200B;**[!UICONTROL folders]**&#x200B;以组织所有连接。 只需将每个连接拖放到某个文件夹中。

## 登录到Adobe Campaign {#logon-to-ac}

Campaign用户使用其Adobe ID，通过Adobe Identity Management System (IMS)连接到Adobe Campaign控制台。 他们可以在所有Adobe解决方案中使用相同的ID。 将Adobe Campaign与其他解决方案一起使用时，将会保存连接。 在[此页面](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"}中了解有关Adobe IMS的更多信息。

要登录到实例，请执行以下步骤：

1. 启动Console并浏览右角的链接以访问连接配置屏幕。

   ![](assets/connectToCampaign.png)

1. 选择您需要登录的Campaign实例。

1. 单击 **[!UICONTROL Ok]**。

然后，您可以使用您的Adobe ID登录到Campaign。

![](assets/adobeID.png)

>[!NOTE]
>
>由于Microsoft Edge Webview2不保存代理凭据，因此，在首次连接时，控制台可能会要求您进行两次身份验证。

## 升级您的客户端控制台{#upgrade-ac-console}

当您的系统升级到较新版本时，您必须将客户端控制台更新到该版本。 这是最佳实践，对于某些版本，此升级是强制性的。 在这种情况下，它在[发行说明](release-notes.md)中提及。

作为托管云服务用户，Adobe会为您部署客户端控制台。 当您连接到已升级的环境时，系统会提示您在一个弹出窗口中下载最新的Client Console版本。 您必须接受此升级，并根据请求更新客户端控制台。

>[!CAUTION]
>
>Adobe建议取消选择选项&#x200B;**[!UICONTROL No longer ask this question]**，以确保在新版本的Console可用时收到警报。 如果选择此选项，则不会通知用户需要升级Console。
>



## 授予用户访问权限{#grant-access}

Adobe Campaign允许您定义和管理分配给各种操作员的权限。

作为Campaign管理员，您负责创建操作员并与用户共享其凭据。

在[本节](gs-permissions.md)中了解有关用户以及如何定义其权限的详细信息。


## 使用Web浏览器访问Campaign {#connect-web-ac}

### Web 用户界面 {#connect-web-ui}

从 Campaign v8.6 版本开始，您可以访问新的 **Campaign Web 用户界面**，该界面可通过中央 Adobe Experience Cloud 环境使用。Experience Cloud 是 Adobe 的数字营销应用程序、产品和服务的集成系列。通过其直观的界面，您可以快速访问云应用程序、产品功能和服务。

>[!AVAILABILITY]
>
>Campaign Web用户界面仅适用于通过Adobe ID连接到Adobe Campaign的用户。 了解有关[Adobe Identity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"}的更多信息。
>

[在此页面中](campaign-ui.md#ac-web-ui)了解如何连接到 Adobe Experience Cloud 并访问 Adobe Campaign Web 界面。

请参阅[Adobe Campaign Web用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}以了解详情。

### Web 访问 {#web-access}

可以使用HTML用户界面通过Web浏览器访问应用程序的某些部分：报告、投放批准、实例监控等。

Web 访问提供了与控制台类似的界面，但是功能有所减少。

例如，对于给定的运算符，促销活动将在控制台中显示以下选项：

![](assets/campaign-from-console.png)

而使用 Web 访问时，选项主要是查看功能：

![](assets/campaign-from-web.png)

在验证过程中还会使用Web访问：操作员可以单击审批请求电子邮件，并通过其Web浏览器连接到Campaign，以验证或拒绝投放内容或预算。

要从Web访问Campaign实例，URL为： `https://<your adobe campaign server>:<port number>/view/home`。
