---
title: Campaign v8 兼容性矩阵
description: 了解与 Campaign v8 兼容的系统和版本
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 52%

---

# Campaign v8 兼容性矩阵 {#compat-matrix}

本文档列出了最新内部版本支持的所有系统和组件 **Adobe Campaign v8** 客户端控制台。 除非另有说明，否则支持所有次要版本。此列表中未包含的产品和版本与 Adobe Campaign 不兼容。

随着这些第三方系统和工具的特定版本的生命周期结束 (EOL)，Adobe Campaign 将不再与这些版本兼容，并会从兼容性矩阵中移除它们。请确保您使用兼容性矩阵中列出的任何系统的受支持版本，以避免出现任何问题。

>[!NOTE]
>
>Adobe Campaign服务器和Campaign客户端控制台必须使用同一版本。 [如何检查您的版本](upgrades.md#version)。

## 客户端控制台 {#ClientConsoleoperatingsystems}

要使用Campaign客户端控制台，必须配备以下操作系统和浏览器。 [了解详情](connect.md)。

### 操作系统 {#op-systems}

* **Microsoft Windows Server** 2019、2016
* **Microsoft Windows** 11， 10

>[!NOTE]
>客户端控制台的32位版本自8.5版本以来已被弃用。 从8.6开始，客户端控制台仅以64位提供。 有关如何升级系统的详细信息，请参阅此 [技术说明](../../technotes/upgrades/console.md).

### Web 浏览器 {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**，最新版本。从 [Microsoft 开发人员网站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_cn){target="_blank"}下载该浏览器。

## CRM 连接器 {#CRMconnectors}

下面列出了与 Adobe Campaign 兼容的客户关系管理 (CRM) 系统。了解有关CRM连接器的更多信息 [本页内容](../connect/crm.md).

* **Salesforce** 连接器 API 版本 49
* **Microsoft Dynamics** 连接器、Web API：Dynamics 365 内部部署版和在线版

## 联合数据访问 (FDA){#FederatedDataAccessFDA}

下面列出了与 Adobe Campaign 联合数据访问 (FDA) 模块兼容的外部数据库。了解有关FDA的更多信息 [本页内容](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**，从Campaign v8.5开始
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 移动 SDK {#MobileSDK}

要使用 Campaign 发送[推送通知](../send/push.md)，您可以通过在“数据收集”UI 中配置 Adobe Campaign 扩展来使用 Adobe Experience Platform Mobile SDK。

中详细介绍了iOS和Android的兼容版本 [Adobe Developer文档](https://developer.adobe.com/client-sdks/home/){target="_blank"}.

## Web用户界面 {#web-ui}

以下浏览器与Campaign Web用户界面兼容。 了解有关Campaign Web UI的更多信息 [本页内容](campaign-ui.md#ac-web-ui).

* **Microsoft Edge**， **Google Chrome**， **Safari** （最新版本）

## Web 访问 {#web-access}

以下浏览器与Campaign兼容，可用于进行Web访问。 了解有关Campaign Web访问的更多信息 [本页内容](connect.md#web-access).

* **Microsoft Edge**、**Mozilla Firefox**、**Google Chrome**、**Safari**（最新版本）

## 其他资源 {#support}

* [Campaign版本更新](upgrades.md)
* [检查您的Campaign版本](upgrades.md#version)
* [安装Campaign客户端控制台](connect.md)
* [控制面板版本](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans){target="_blank"}

要获悉新的Experience Cloud解决方案版本，请订阅 [Adobe优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target="_blank"}.