---
title: Campaign v8 兼容性矩阵
description: 了解与 Campaign v8 兼容的系统和版本
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: ht
source-wordcount: '406'
ht-degree: 100%

---

# Campaign v8 兼容性矩阵 {#compat-matrix}

本文档列出了最新版本的 **Adobe Campaign v8** 客户端控制台支持的所有系统和组件。除非另有说明，否则支持所有次要版本。此列表中未包含的产品和版本与 Adobe Campaign 不兼容。

随着这些第三方系统和工具的特定版本的生命周期结束 (EOL)，Adobe Campaign 将不再与这些版本兼容，并会从兼容性矩阵中移除它们。请确保您使用兼容性矩阵中列出的任何系统的受支持版本，以避免出现任何问题。

>[!NOTE]
>
>Adobe Campaign 服务器和 Campaign 客户端控制台必须是同一版本。[如何检查您的版本](upgrades.md#version)。

## 客户端控制台 {#ClientConsoleoperatingsystems}

要使用 Campaign 客户端控制台，必须配备以下操作系统和浏览器。[了解详情](connect.md)。

### 操作系统 {#op-systems}

* **Microsoft Windows Server** 2019、2016
* **Microsoft Windows** 11、10

>[!NOTE]
>32 位版本的客户端控制台自 8.5 版起已被弃用。从 8.6 开始，客户端控制台仅提供 64 位版本。有关如何升级系统的详细信息，请参阅此[技术说明](../../technotes/upgrades/console.md)。

### Web 浏览器 {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**，最新版本。从 [Microsoft 开发人员网站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_cn){target="_blank"}下载该浏览器。

## CRM 连接器 {#CRMconnectors}

下面列出了与 Adobe Campaign 兼容的客户关系管理 (CRM) 系统。[在此页面中](../connect/crm.md)了解有关 CRM 连接器的详细信息。

* **Salesforce** 连接器 API 版本 49
* **Microsoft Dynamics** 连接器、Web API：Dynamics 365 内部部署版和在线版

## 联合数据访问 (FDA){#FederatedDataAccessFDA}

下面列出了与 Adobe Campaign 联合数据访问 (FDA) 模块兼容的外部数据库。[在此页面中](../connect/fda.md)了解有关 FDA 的详细信息。

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**，从 Campaign v8.5 开始
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 移动 SDK {#MobileSDK}

要使用 Campaign 发送[推送通知](../send/push.md)，您可以通过在“数据收集”UI 中配置 Adobe Campaign 扩展来使用 Adobe Experience Platform Mobile SDK。

[Adobe Developer 文档](https://developer.adobe.com/client-sdks/home/){target="_blank"}中详细介绍了适用于 iOS 和 Android 的兼容版本。

## Web 用户界面 {#web-ui}

以下浏览器与 Campaign Web 用户界面兼容。[在此页面中](campaign-ui.md#ac-web-ui)了解有关 Campaign Web UI 的详细信息。

* **Microsoft Edge**、**Google Chrome**、**Safari**（最新版本）

## Web 访问 {#web-access}

以下浏览器与 Campaign for Web Access 兼容。[在此页面中](connect.md#web-access)了解有关 Campaign Web access 的详细信息。

* **Microsoft Edge**、**Mozilla Firefox**、**Google Chrome**、**Safari**（最新版本）

## 其他资源 {#support}

* [Campaign 版本更新](upgrades.md)
* [检查 Campaign 版本](upgrades.md#version)
* [安装 Campaign 客户端控制台](connect.md)
* [控制面板版本](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans){target="_blank"}

要获悉新的 Experience Cloud 解决方案版本，请订阅 [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target="_blank"}。