---
product: campaign
title: 配置在线调查
description: 了解如何配置在线调查
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 387bc362-4064-4181-9385-8e0c3423ba3e
TQID: 'https://experienceleague.adobe.com/1BTkZ--FyHkp7u0eya-lmuELDu8AMmeC96eGsonYcVM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: aa436bfd174075f7ed3e144ea0b16832b6b811ff
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%
---
# 配置在线调查{#configuring-surveys}

>[!AVAILABILITY]
>
>调查不适用于[Campaign FFDA部署](../../architecture/enterprise-deployment.md)。



## 调查属性 {#survey-properties}

在线调查是完全可配置和定制的，可满足您的要求。 必须在属性窗口中输入参数。

可用参数在[此文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/designing-content/web-forms/defining-web-forms-properties){target="_blank"}中有详细说明。

![](assets/s_ncs_admin_survey_properties_general.png)

## 调查数据存储 {#survey-data-storage}

默认情况下，Web窗体字段存储在收件人表中。 要使用其他表，请在&#x200B;**[!UICONTROL Document type]**&#x200B;字段中选择它。 **[!UICONTROL Zoom]**&#x200B;图标允许您查看选定表的内容。

由用户提供的调查答案未存储在字段（但存储在局部变量中）中，这些答案存储在&#x200B;**调查答案**&#x200B;表中。 您可以根据&#x200B;**[!UICONTROL Library]**&#x200B;字段更改使用的架构。 此字段仅适用于&#x200B;**调查**。
