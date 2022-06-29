---
title: Campaign v8 兼容性矩阵
description: 了解与 Campaign v8 兼容的系统和版本
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 39edd6c60c220118f34cd476b887194e1e7763e4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Campaign v8 兼容性矩阵

本文档列出了最新版本的 **Adobe Campaign v8** 支持的所有系统和组件。除非另有说明，否则支持所有次要版本。此列表中未包含的产品和版本与 Adobe Campaign 不兼容。

随着这些第三方系统和工具的特定版本的生命周期结束 (EOL)，Adobe Campaign 将不再与这些版本兼容，并会从兼容性矩阵中移除它们。请确保您使用兼容性矩阵中列出的任何系统的受支持版本，以避免出现任何问题。

>[!NOTE]
>
>Adobe Campaign 服务器和客户端控制台必须使用同一版本。[如何检查您的版本](#version)。

## 客户端控制台{#ClientConsoleoperatingsystems}

要使用 Campaign 客户端控制台，必须配备以下操作系统和浏览器。[了解详情](connect.md)。

### 操作系统

* **Microsoft Windows Server** 2019、2016、2012
* **Microsoft Windows** 11（从 Campaign v8.3 开始）、10、8、

>[!NOTE]
>
>建议对日语实例使用 Microsoft Windows 10。

### 浏览器

**Microsoft Internet Explorer** 11

## CRM 连接器{#CRMconnectors}

下面列出了与 Adobe Campaign 兼容的客户关系管理 (CRM) 系统。[了解详情](../connect/crm.md)。

* **Salesforce** connector API 版本 49
* **Microsoft Dynamics** 连接器， Web API:Dynamics 365内部部署版和在线版

## 联合数据访问 (FDA){#FederatedDataAccessFDA}

下面列出了与 Adobe Campaign 联合数据访问 (FDA) 模块兼容的外部数据库。[了解详情](../connect/fda.md)。

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 移动 SDK{#MobileSDK}

您可以使用 Campaign 通过关联的 Mobile SDK 在以下列出的操作系统上发送[推送通知](../send/push.md)。

* **Android** 12（从 Campaign v8.3 开始）、9.0、8.x、7.x，带有 Campaign Android SDK 内部版本 1.1.1。
* **Apple iOS** 9 - 15 适用于 Campaign iOS SDK 内部版本 1.0.26，与 32 位和 64 位版本兼容。从 Campaign v8.3 开始支持 iOS 15。

## Web 访问

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
