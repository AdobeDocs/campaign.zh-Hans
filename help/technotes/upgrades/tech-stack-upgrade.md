---
product: campaign
title: 技术说明 — Adobe Campaign系统升级
description: Adobe Campaign系统升级
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: f1e963a880e8499dbbb16c44831a4ce1b537601f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---

# Adobe Campaign 2023年环境升级 {#ac-system-upgrade}

Campaign基础架构依赖于第三方系统，必须定期更新最新版本和修复。 这些更新是强制性的，可确保服务的连续性，并保护Campaign环境免受安全风险的影响。 此外，还需要升级Campaign以确保与第三方系统更改兼容。

As a **托管Cloud Services客户**，则Adobe会在需要时通知您这些升级。 您的环境需要根据建议进行升级以确保符合要求。

出于安全考虑，Adobe必须 [安装最新的Campaign内部版本](#ac-upgrade)，然后升级 [操作系统](#os-upgrade) 和/或 [关系数据库管理系统](#pg-upgrade).

>[!NOTE]
>
>有关这些更改的任何问题，请联系 [Adobe 客户关怀](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。

## Campaign内部版本升级 {#ac-upgrade}

**您是否受影响？**

如果您受 [操作系统升级](#os-upgrade) 和/或 [数据库系统升级](#pg-upgrade) 下文详细介绍，Adobe必须将您的Campaign环境升级到 [最新的8.4.3版本](../../v8/start/release-notes.md)，与这些系统兼容。

**如何更新？**

作为受管Cloud Services客户，Adobe将与您联系并升级您的Campaign版本。

## 操作系统升级 {#os-upgrade}

**您是否受影响？**

如果您在Debian操作系统上运行Campaign，要从最新的Debian安全更新中受益，Adobe需要将您的Campaign基础架构移至 **Debian 11**. 请注意，Debian 9的安全支持将在2023年6月30日之前提供。

**如何更新？**

作为受管Cloud Services客户，Adobe将与您联系并升级您的环境。

## 数据库系统升级 {#pg-upgrade}

**您是否受影响？**

如果您的Campaign数据库系统是PostgreSQL，要从最新的PostgreSQL创新和安全更新中受益，Adobe需要升级到 **PostgreSQL 14**. 请注意，PostgreSQL 11的生命周期将于2023年11月9日终止。

**如何更新？**

作为托管Cloud Services客户，Adobe将与您联系，并将数据库系统从PostgreSQL 11升级到PostgreSQL 14。
