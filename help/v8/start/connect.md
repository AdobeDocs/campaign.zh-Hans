---
title: 连接到Campaign v8
description: 了解如何连接到Adobe Campaign v8并在您的计算机上安装控制台，以便更轻松地访问。
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: f381a2ec91b7179a51d91f9b7414ea39db03cd71
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 6%

---

# 连接到Adobe Campaign v8{#gs-ac-connect}

Campaign客户端控制台是一个富客户端，可让您连接到Campaign应用程序服务器。 进一步了解Campaign客户端控制台 [本页](ac-components.md#presentation-layer).

在开始之前，您需要：

* 在 [兼容性矩阵](compatibility-matrix.md)
* 获取Campaign服务器URL
* 创建Adobe ID或从您的公司获取用户凭据
* 在系统上安装Microsoft Edge Webview2运行时(从Campaign Classic8.4内部版本)。 [了解详情](#webview)

## Microsoft Edge Webview2运行时安装 {#webview}

从Campaign Classic8.4内部版本开始，任何控制台安装都需要安装Microsoft Edge Webview 2运行时。

Web View默认作为Windows 11操作系统的一部分安装。 如果系统上尚不存在该服务器，Campaign控制台安装程序将提示您从下载它 [Microsoft开发人员网站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_cn){target=&quot;_blank&quot;}。 请注意，下载链接在Internet Explorer 11浏览器上不起作用，因为Microsoft已弃用其支持。 确保使用其他浏览器访问该链接。

## 下载并安装客户端控制台{#download-ac-console}

首次使用Campaign时，或者如果您需要升级到较新版本，则需要下载客户端控制台并安装它。

有两个选项可用：

1. 作为Campaign管理员，请连接到Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/cn/campaign.html){target=&quot;_blank&quot;}并下载客户端控制台安装程序。 然后，您可以将其安装到本地计算机上。

1. 作为最终用户，Adobe可以为您部署控制台：更新控制台后，系统会在弹出窗口中提示您下载最新的客户端控制台版本。

>[!CAUTION]
>
>Adobe建议将选项保留为 **[!UICONTROL No longer ask this question]** 取消选中，以确保当有新版本的控制台可用时，所有用户都会收到警报。  如果选择此选项，则用户将不会获悉新的可用版本。

## 创建连接{#create-your-connection}

新安装客户端控制台后，请按照以下步骤创建与应用程序服务器的连接：

1. 从窗口启动控制台 **[!UICONTROL Start]** 菜单中 **Adobe Campaign** 项目组。

1. 单击凭据字段右上角的链接以访问连接配置窗口。

1. 单击 **[!UICONTROL Add > Connection]** 并输入Adobe Campaign应用程序服务器的标签和URL。

1. 通过URL指定与Adobe Campaign应用程序服务器的连接。 使用DNS或计算机的别名，或您的IP地址。

   例如，您可以使用 [`https://<machine>.<domain>.com`](https://myserver.adobe.com) 键入URL。

1. 选中选项 **[!UICONTROL Connect with an Adobe ID]**.

1. 单击 **[!UICONTROL Ok]** 来保存设置。

您可以根据需要添加任意数量的连接，以连接到测试、暂存和生产环境等。

>[!NOTE]
>
>的 **[!UICONTROL Add]** 按钮 **[!UICONTROL folders]** 来组织你的所有联系。 只需将每个连接拖放到某个文件夹中。

## 登录Adobe Campaign {#logon-to-ac}

要登录到现有实例，请执行以下步骤：

1. 从窗口启动控制台 **[!UICONTROL Start]** 菜单中 **Adobe Campaign** 项目组。

1. 单击凭据字段右上角的链接以访问连接配置窗口。

   ![](assets/connectToCampaign.png)

1. 选择您需要登录的Campaign实例。

1. 单击 **[!UICONTROL Ok]**。

1. 然后，您可以使用 [您的Adobe ID](#connect-ims).

   ![](assets/adobeID.png)

>[!NOTE]
>
>对于Campaign Classic 8.4内部版本，Adobe Campaign客户端控制台在代理身份验证期间可能两次请求获取代理凭据。 这是因为与Internet Explorer不同，Microsoft Edge Webview2未将代理凭据保存在缓存/密码存储区中。

## 授予用户访问权限{#grant-access}

Adobe Campaign允许您定义和管理分配给各种运算符的权限。

作为Campaign管理员，您负责创建操作员并与用户共享其凭据。

进一步了解用户以及如何在 [此部分](gs-permissions.md).


## 使用Adobe ID连接到Campaign{#connect-ims}

Campaign用户使用其Adobe ID通过AdobeIdentity Management系统(IMS)连接到Adobe Campaign控制台。 他们可以使用相同的ID来处理所有Adobe解决方案。 将Adobe Campaign与其他解决方案结合使用时，会保存连接。

在 [本页](https://helpx.adobe.com/enterprise/using/identity.html){target=&quot;_blank&quot;}。

## Web 访问{#web-access}

应用程序的某些部分可通过Web浏览器使用HTML用户界面访问：报告、投放批准、实例监控等。

Web 访问提供了与控制台类似的界面，但是功能有所减少。

例如，对于给定的运算符，在控制台中将显示具有以下选项的营销活动：

![](assets/campaign-from-console.png)

而使用 Web 访问时，选项主要是查看功能：

![](assets/campaign-from-web.png)

验证过程中也使用Web访问：操作员可以单击批准请求电子邮件，并通过其Web浏览器连接到Campaign，以验证或拒绝投放内容或预算。

要从Web访问Campaign实例，URL为：  `https://<your adobe campaign server>:<port number>/view/home`.
