---
product: Adobe Campaign
title: Campaign v8 兼容性矩阵
description: 了解与 Campaign v8 兼容的系统和版本
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 619edce939b39430832fd950ece734f817f9dce3
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 68%

---

# Campaign v8 兼容性矩阵

本文档列出了最新版本的 **Adobe Campaign v8** 支持的所有系统和组件。此列表中未包含的产品和版本与 Adobe Campaign 不兼容。

>[!CAUTION]
>
>* 除非另有说明，否则支持所有次要版本。
>* 随着这些第三方系统和工具的特定版本的生命周期结束 (EOL)，Adobe Campaign 将不再与这些版本兼容，并会从兼容性矩阵中移除它们。请确保您使用兼容性矩阵中列出的任何系统的受支持版本，以避免出现任何问题。


## 兼容系统

### 客户端控制台{#ClientConsoleoperatingsystems}

警告：要使用 Campaign 客户端控制台，必须配备以下操作系统和浏览器。

**操作系统**

* **Microsoft Windows Server** 2016、2012
* **Microsoft Windows** 8、10（建议用于日语实例)

**浏览器**

**Microsoft Internet Explorer**  11

### CRM 连接器{#CRMconnectors}

* **Salesforce** connector API 版本 49
* **Microsoft Dynamics** 连接器、Web API：Dynamics 365 内部部署版和在线版

### 联合数据访问 (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

### 移动 SDK{#MobileSDK}

* **Android** 7.x、8.x、9.0（带有Campaign Android SDK内部版本1.1.1）。
* **Apple iOS**  9 - 14，带有Campaign iOS SDK内部版本1.0.26，与32位和64位版本兼容。

### 支持的浏览器 {#Browsers}

以下浏览器与 Campaign 兼容，可用于进行 Web 访问。

* **Microsoft Edge**、 **Mozilla Firefox**、**Google Chrome**、**Safari** （最新版本）

* **Internet Explorer** 11

## 如何检查您的 Campaign 版本 构建

使用&#x200B;**Help > About...**&#x200B;菜单检查您的版本。

![](assets/ac-version.png)

您可以访问以下信息：

* 客户端控制台和应用程序服务器的&#x200B;**版本**&#x200B;编号。 在上面的示例中，客户端控制台和应用程序服务器的版本均为8.1.5。
* SHA号，在圆括号中。
* 联系Adobe客户关怀的链接。
* Adobe隐私政策、使用条款和Cookie政策的链接。
