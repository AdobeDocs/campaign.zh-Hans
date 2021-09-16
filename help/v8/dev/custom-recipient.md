---
title: 更改默认收件人表
description: 了解如何使用自定义收件人表
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# 使用自定义收件人表格{#gs-ac-custom-recipient}

Adobe Campaign附带一个内置配置文件表：**nmsRecipient**。 此表包含许多可轻松扩展的预定义字段和表。 在[此页面](datamodel.md#ootb-profiles)中了解有关此表的更多信息。

内置表扩展具有灵活性，但不允许删除某些未使用的字段或链接。 因此，当数据模型与Campaign内置收件人表结构存在显着差异，或者您拥有大量用户档案时，使用自定义收件人表是一个不错的选项。  但是，在实施此方法时，需要一定的预防措施。

此功能允许Adobe Campaign处理来自外部数据库的数据：此数据将用作投放的一组用户档案。 实施此过程涉及一些限制，例如：

* 没有Campaign Cloud数据库的更新流和来自该数据库的更新流：此表中的数据可以直接通过托管该表的数据库引擎进行更新。
* 在现有数据库上运行的进程需要是稳定的。
* 使用具有非标准结构的用户档案数据库：可以使用单个实例将保存在具有各种结构的各种表中的用户档案传送到。

本节介绍在Adobe Campaign中映射现有表的要点，以及用于根据任何表执行投放的配置设置。 还介绍了如何为最终用户设计查询界面。

>[!CAUTION]
>
>Adobe Campaign自定义仅保留给专家用户。 它需要在输入表单和模式设计方面的专业知识。

