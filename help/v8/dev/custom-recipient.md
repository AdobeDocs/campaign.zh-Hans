---
solution: Campaign Classic
product: campaign
title: 更改默认收件人表
description: 了解如何使用自定义收件人表
feature: 概述
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
translation-type: tm+mt
source-git-commit: 5b9e381c154420c57a66e5b41b25bd4754036c60
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# 使用自定义收件人表{#gs-ac-custom-recipient}

Adobe Campaign附带一个内置的用户档案表：**nmsRecipient**。 此表包含许多可轻松扩展的预定义字段和表。 在[此页](datamodel.md#ootb-profiles)中了解有关此表的详细信息。

内置的表扩展优惠了良好的灵活性，但不允许删除某些未使用的字段或链接。 因此，当收件人模型与活动内置收件人表结构差异很大时，或者如果您有大量用户档案时，使用自定义表是一个不错的选择。  但是，在实现该方法时，需要采取一定的预防措施。

此功能允许Adobe Campaign处理来自外部数据库的数据：此用户档案将用作一组投放。 实施此过程涉及限制，例如：

* 没有与活动 Cloud数据库之间的更新流：此表中的数据可以直接通过承载该表的数据库引擎进行更新。
* 在现有数据库上运行的进程需要稳定。
* 使用非标准结构的用户档案数据库：可能使用单个实例将保存在具有各种结构的各种表中的用户档案传送到。

本节介绍映射Adobe Campaign中现有表的关键点以及应用于基于任何表执行投放的配置设置。 还介绍了如何为最终用户设计查询界面。


>[!CAUTION]
>
>Adobe Campaign自定义仅保留给专家用户。 它需要在输入表单和模式设计方面的专业知识。

