---
title: Campaign v8 兼容性矩阵
description: 了解与 Campaign v8 兼容的系统和版本
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: b4593dd9fbb3e4742183719281ff0e5a78b9e6c8
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 90%

---

# Campaign v8 兼容性矩阵

本文档列出了最新版本的 **Adobe Campaign v8** 支持的所有系统和组件。除非另有说明，否则支持所有次要版本。此列表中未包含的产品和版本与 Adobe Campaign 不兼容。

随着这些第三方系统和工具的特定版本的生命周期结束 (EOL)，Adobe Campaign 将不再与这些版本兼容，并会从兼容性矩阵中移除它们。请确保您使用兼容性矩阵中列出的任何系统的受支持版本，以避免出现任何问题。

>[!NOTE]
>
>Adobe Campaign 服务器和客户端控制台必须使用同一版本。[如何检查您的版本](#version)。

## 客户端控制台{#ClientConsoleoperatingsystems}

要使用 Campaign 客户端控制台，必须配备以下操作系统和浏览器。[了解详情](connect.md)。

### 操作系统{#op-systems}

* **Microsoft Windows Server** 2019、2016、2012
* **Microsoft Windows** 11、10、8

### Web 浏览器{#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**，最新版本。从 [Microsoft 开发人员网站](http://www.adobe.com/go/acc-ms-webview2-runtime-download_cn){target="_blank"}下载该浏览器。

## CRM 连接器{#CRMconnectors}

下面列出了与 Adobe Campaign 兼容的客户关系管理 (CRM) 系统。[了解详情](../connect/crm.md)。

* **Salesforce** 连接器 API 版本 49
* **Microsoft Dynamics** 连接器、Web API：Dynamics 365 内部部署版和在线版

## 联合数据访问 (FDA){#FederatedDataAccessFDA}

下面列出了与 Adobe Campaign 联合数据访问 (FDA) 模块兼容的外部数据库。[了解详情](../connect/fda.md)。

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 移动 SDK{#MobileSDK}

发送 [推送通知](../send/push.md) 通过Campaign，您可以通过在数据收集UI中配置Adobe Experience Platform Mobile SDK。 您还可以使用下面列出的Campaign SDK:

* **Android** 12、9.0、8.x、7.x 适用于 Campaign Android SDK 版本 1.1.1。
* **Apple iOS** 9 - 16 适用于 Campaign iOS SDK 版本 1.0.26，与 32 位和 64 位版本兼容。Campaign v8.4 及更高版本支持 Apple iOS 16。


## Web 访问{#web-access}

以下浏览器与 Campaign 兼容，可用于[进行 Web 访问](connect.md#web-access)。

* **Microsoft Edge**、**Mozilla Firefox**、**Google Chrome**、**Safari**（最新版本）

## 如何检查您的 Campaign 版本和内部版本{#version}

访问 **Help > About…** 菜单检查您的版本。

![](assets/ac-version.png)

您可以访问以下信息：

* Campaign 客户端控制台和应用程序服务器的&#x200B;**版本**&#x200B;编号。在上面的示例中，客户端控制台和应用程序服务器的版本均为 8.1.5。
* 用圆括号括起的 SHA 编号。
* 用于联系 Adobe 客户关怀团队的链接。
* 指向 Adobe 隐私政策、使用条款和 Cookie 政策的链接。
