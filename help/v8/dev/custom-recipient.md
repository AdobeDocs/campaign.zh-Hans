---
title: 更改您的默认收件人表
description: 了解如何使用自定义收件人表
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 3%

---

# 使用自定义收件人表格{#gs-ac-custom-recipient}

Adobe Campaign附带内置配置文件表： **nmsRecipient**。 此表有许多可以轻松扩展的预定义字段和表。 在[此页面](datamodel.md#ootb-profiles)中了解有关此表的更多信息。

内置的表扩展提供了灵活性，但它不允许删除某些未使用的字段或链接。 因此，当数据模型与Campaign内置的收件人表结构存在很大差异，或者您拥有大量用户档案时，使用自定义收件人表可能是一个不错的选择。  但是，此方法在实施时需要遵循一定的预防措施。

请参阅[Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html?lang=zh-Hans){target="_blank"}以了解如何配置实例以使用自定义收件人表。