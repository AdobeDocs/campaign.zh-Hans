---
title: Campaign v8 兼容性矩阵
description: 了解与 Campaign v8 兼容的系统和版本
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 83874f4d124d7892f99e973684b1e8ee571f31e0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 78%

---

# Campaign v8 兼容性矩阵

本文档列出了最新版本的 **Adobe Campaign v8** 支持的所有系统和组件。除非另有说明，否则支持所有次要版本。此列表中未包含的产品和版本与 Adobe Campaign 不兼容。

随着这些第三方系统和工具的特定版本的生命周期结束 (EOL)，Adobe Campaign 将不再与这些版本兼容，并会从兼容性矩阵中移除它们。请确保您使用兼容性矩阵中列出的任何系统的受支持版本，以避免出现任何问题。

## 客户端控制台{#ClientConsoleoperatingsystems}

警告：要使用 Campaign 客户端控制台，必须配备以下操作系统和浏览器。[了解详情](connect.md)。

### 操作系统

* **Microsoft Windows Server** 2016、2012
* **Microsoft Windows** 8、10（建议用于日语实例)

### 浏览器

**Microsoft Internet Explorer** 11

>[!NOTE]
>
>Adobe Campaign服务器和客户端控制台必须位于同一版本上。 [了解如何检查您的版本](#version)。

## CRM 连接器{#CRMconnectors}

下面列出了与Adobe Campaign兼容的客户关系管理(CRM)系统。 [了解详情](../connect/crm.md)。

* **Salesforce** connector API 版本 49
* **Microsoft Dynamics** 连接器、Web API：Dynamics 365 内部部署版和在线版

## 联合数据访问 (FDA){#FederatedDataAccessFDA}

下面列出了与Adobe Campaign联合数据访问(FDA)模块兼容的外部数据库。 [了解详情](../connect/fda.md)。

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 移动 SDK{#MobileSDK}

您可以使用Campaign通过关联的Mobile SDK在下面列出的操作系统上发送[推送通知](../send/push.md)。

* **Android** 7.x、8.x、9.0 适用于 Campaign Android SDK 版本 1.1.1。
* **Apple iOS** 9 - 14 适用于 Campaign iOS SDK 版本 1.0.26，与 32 位和 64 位版本兼容。

## Web 访问

以下浏览器与Campaign for [Web Access](connect.md#web-access)兼容。

* **Microsoft Edge**、 **Mozilla Firefox**、**Google Chrome**、**Safari** （最新版本）

* **Internet Explorer** 11

## 如何检查您的 Campaign 版本和版本{#version}

访问 **Help > About…** 菜单检查您的版本。

![](assets/ac-version.png)

您可以访问以下信息：

* Campaign 客户端控制台和应用程序服务器的&#x200B;**版本**&#x200B;编号。在上面的示例中，客户端控制台和应用程序服务器的版本均为 8.1.5。
* 用圆括号括起的 SHA 编号。
* 用于联系 Adobe 客户关怀团队的链接。
* 指向 Adobe 隐私政策、使用条款和 Cookie 政策的链接。
