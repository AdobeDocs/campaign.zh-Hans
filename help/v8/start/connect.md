---
title: 连接到 Campaign v8
description: 了解如何连接到 Adobe Campaign v8 并在您的计算机上安装控制台以便于访问。
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: ht
source-wordcount: '1006'
ht-degree: 100%

---

# 连接到 Adobe Campaign v8{#gs-ac-connect}

要开始使用 Campaign，您必须安装和配置客户端控制台。

客户端控制台是一个原生应用程序，它通过标准 Internet 协议（如 SOAP 和 HTTP）与 Adobe Campaign 应用程序服务器进行通信。Campaign 客户端控制台集中了所有功能和设置，并且由于依赖本地缓存，需要的带宽很少。Campaign 客户端控制台旨在实现轻松部署，可以从 Internet 浏览器部署，可以自动更新，并且不需要任何特定的网络配置，因为它只生成 HTTP(S) 流量。

在开始之前，您需要：

* 在[兼容性矩阵](compatibility-matrix.md)中检查系统和工具与 Adobe Campaign 的兼容性
* 获取 Campaign 服务器 URL
* 创建 Adobe ID，或从您的公司获取用户凭据
* 在系统上安装 Microsoft Edge Webview2 运行时。[了解详情](#webview)

## 安装客户端控制台{#download-ac-console}

### Microsoft Edge WebView2 运行时 {#webview}

从 Campaign Classic 8.4 内部版本开始，安装客户端控制台时，都需要有 Microsoft Edge Webview 2 运行时。

默认情况下，Web View 作为 Windows 11 操作系统的一部分安装。如果您的系统中没有 Web View，Campaign 客户端控制台安装程序将提示您从 [Microsoft 开发人员网站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_cn){target="_blank"}下载它。请注意，下载链接在 Internet Explorer 11 浏览器上不起作用，因为 Microsoft 已停止为其提供支持。确保使用其他浏览器来访问该链接。

### 下载控制台{#install-ac-console}

首次使用 Campaign 时，您需要下载并安装客户端控制台。

下载客户端控制台的方式有两种：

1. 作为 Campaign 管理员，连接到 Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/zh-hans/campaign.html){target="_blank"}。

1. 作为最终用户，Campaign 管理员会为您部署客户端控制台，并通过专用 URL 提供给您。

下载客户端控制台安装程序后，将其安装到本地计算机上。

请注意，安装客户端控制台后，您无法更改其语言。

## 创建您的连接{#create-your-connection}

安装客户端控制台后，请按照以下步骤创建与应用程序服务器的连接：

1. 启动控制台并浏览右边角的链接以访问连接配置屏幕。

1. 单击 **[!UICONTROL Add > Connection]** 并输入 Adobe Campaign 应用程序服务器的标签和 URL。

1. 通过 URL 指定与 Adobe Campaign 应用程序服务器的连接。使用计算机的 DNS 或别名，或您的 IP 地址。

   例如，您可以使用 `https://<machine>.<domain>.com` 类型 URL。

1. 勾选 **[!UICONTROL Connect with an Adobe ID]** 选项。

1. 单击 **[!UICONTROL Ok]** 以保存您的设置。

例如，您可以根据需要添加任意数量的连接，以连接到测试、暂存和生产环境。

>[!NOTE]
>
>使用 **[!UICONTROL Add]** 按钮可创建 **[!UICONTROL folders]**，以用于组织所有连接。只需将每个连接拖放到某个文件夹中。

## 登录到 Adobe Campaign {#logon-to-ac}

Campaign 用户使用其 Adobe ID，通过 Adobe 身份管理系统 (IMS) 连接到 Adobe Campaign 控制台。他们可以在所有 Adobe 解决方案中使用相同的 ID。将 Adobe Campaign 与其他解决方案配合使用时，可以保存该连接。要了解有关 Adobe IMS 的更多信息，请参阅[此页面](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"}。

要登录到某个实例，请执行以下步骤：

1. 启动控制台并浏览右边角的链接以访问连接配置屏幕。

   ![](assets/connectToCampaign.png)

1. 选择您需要登录到的 Campaign 实例。

1. 单击 **[!UICONTROL Ok]**。

然后，您可以使用 Adobe ID 登录到 Campaign。

![](assets/adobeID.png)

>[!NOTE]
>
>由于 Microsoft Edge Webview2 不保存代理凭据，因此在首次连接时，控制台可能会要求您进行两次身份验证。

## 升级客户端控制台{#upgrade-ac-console}

当系统升级到较新版本时，您必须将客户端控制台更新到相同的版本。这是最佳做法，对于某些版本，此升级是强制性的。在这种情况下，它在[发行说明](release-notes.md)中有所提及。

作为 Managed Cloud Services 用户，Adobe 会为您部署客户端控制台。当您连接到已升级的环境时，系统会提示您在一个弹出窗口中下载最新的客户端控制台版本。您必须接受此升级，并根据请求更新客户端控制台。

>[!CAUTION]
>
>Adobe 建议取消选择 **[!UICONTROL No longer ask this question]** 选项，以确保在新版本的控制台可用时收到提醒。如果选择此选项，则不会通知用户需要升级控制台。
>



## 向用户授予访问权限{#grant-access}

Adobe Campaign 允许您定义和管理分配给各种操作员的权限。

作为 Campaign 管理员，您负责创建操作员并与用户共享其凭据。

要了解有关用户以及如何定义其权限的更多信息，请参阅[本节](gs-permissions.md)。


## 使用 Web 浏览器访问 Campaign {#connect-web-ac}

### Web 用户界面 {#connect-web-ui}

从 Campaign v8.6 版本开始，您可以访问新的 **Campaign Web 用户界面**，该界面可通过中央 Adobe Experience Cloud 环境使用。Experience Cloud 是 Adobe 的数字营销应用程序、产品和服务的集成系列。通过其直观的界面，您可以快速访问云应用程序、产品功能和服务。

>[!AVAILABILITY]
>
>Campaign Web 用户界面仅供通过 Adobe ID 连接到 Adobe Campaign 的用户使用。了解有关 [Adobe 身份管理系统 (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"} 的更多信息。
>

[在此页面中](campaign-ui.md#ac-web-ui)了解如何连接到 Adobe Experience Cloud 并访问 Adobe Campaign Web 界面。

请参阅 [Adobe Campaign Web 用户界面文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-web/v8/campaign-web-home){target="_blank"}以了解详情。

### Web 访问 {#web-access}

可以使用 HTML 用户界面通过 Web 浏览器访问应用程序的某些部分：报告、投放审批、实例监控等。

Web 访问提供了与控制台类似的界面，但是功能有所减少。

例如，针对指定的操作员，控制台中会显示营销活动及以下选项：

![](assets/campaign-from-console.png)

而使用 Web 访问时，选项主要是用于查看：

![](assets/campaign-from-web.png)

在验证过程中也会使用 Web 访问：操作员可以单击审批请求电子邮件，并通过 Web 浏览器连接到 Campaign，以验证或拒绝投放内容或预算。

要从 Web 访问 Campaign 实例，URL 为：`https://<your adobe campaign server>:<port number>/view/home`。
