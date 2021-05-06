---
solution: Campaign Classic
product: campaign
title: 活动 v8兼容性矩阵
description: 学习与活动 v8兼容的系统和版本
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
translation-type: tm+mt
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 27%

---

# 活动 v8兼容性矩阵

此文档列表支持[**Adobe Campaignv8**&#x200B;的最新版本](release-notes.md)的所有系统和组件。 此列表中未包含的产品和版本与 Adobe Campaign 不兼容。

>[!CAUTION]
>
>* 除非另有说明，否则支持所有次要版本。
>* 由于这些第三方系统和工具的特定版本达到寿命终止(EOL),Adobe Campaign将不再与这些版本兼容，并将从此兼容性矩阵中删除它们。 请确保您使用兼容性矩阵中列出的任何系统的受支持版本，以避免出现任何问题。


## 兼容系统

### CRM 连接器{#CRMconnectors}

* **Salesforcconnector** API版本49
* **Microsoft** Dynamicsconnector， Web API:Dynamics 365内部部署和在线

### 联合数据访问 (FDA){#FederatedDataAccessFDA}

* **Microsoft Azure Synapse Analytics**
* **Amazon Redshift**
* **[!DNL Snowflake]**
* **Oracle**  19c、18c、12c、11G
* **PostgreSQL** 12.x、11.x、10.x、9.6.x、9.5.x、9.4.x
* **Microsoft SQL Server**  2019、2017、2016、2014、2012 SP1和SP2
* **MySQL**  5.7
* **Teradata** 16.20、16、15.10、15.0
* **Netezza** 7.2
* **Sybase IQ** 16,ASE 15.7
* **SAP** HANA版本1 SPS 12
* **Hadoop（通过 HiveSQL）**
   * HortonWorks HDP 2.4.X、2.5.x、2.6.x
   * HDInsight 3.4 (HDP 2.4)、3.5 (HDP 2.5)、3.6 (HDP 2.6
   * Cloudera CDH6.x

### 客户端控制台操作系统{#ClientConsoleoperatingsystems}

* **Microsoft Windows Server**  2016、2012
* **Microsoft Windows**  8、10（建议用于日语实例）

### 移动 SDK{#MobileSDK}

* **Android**  7.x、8.x、9.0（带移动SDK版本1.0.27）。
* **Apple iOS**  9 - 14（带移动SDK版本1.0.26），与32和64位版本兼容。

## 支持的浏览器{#Browsers}

* **Microsoft Edge**、 **Mozilla Firefox**、 **Google Chrome** **** 、Safari（最新版本）

* **Internet Explorer**  11

## 如何检查您的活动版本

通过&#x200B;**帮助>关于……**&#x200B;菜单，您可以访问以下信息：

* 活动 Client Console和应用程序服务器的版本号
* 活动 Client Console和应用程序服务器的内部版本号
* 联系Adobe客户关怀
* 指向Adobe隐私政策、使用条款和Cookie政策的链接
