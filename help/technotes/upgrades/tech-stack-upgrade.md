---
product: campaign
title: 技术说明 — Adobe Campaign系统升级
description: Adobe Campaign系统升级
hide: true
hidefromtoc: true
exl-id: cc64cce1-2473-4136-aadc-8b13e89ef7f9
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Adobe Campaign 2023环境升级 {#ac-system-upgrade}

Campaign基础架构依赖于第三方系统，这些系统必须定期使用最新版本和修复进行更新。 必须执行这些更新，以确保服务的连续性，并确保Campaign环境免受安全风险的影响。 此外，需要升级Campaign，以确保与第三方系统更改兼容。

作为&#x200B;**托管Cloud Service客户**，Adobe会在需要这些升级时通知您。 需要根据建议升级您的环境以确保法规遵从性。

出于安全原因，Adobe必须[安装最新的Campaign内部版本](#ac-upgrade)，然后升级[操作系统](#os-upgrade)和/或[关系数据库管理系统(RDBMS)](#pg-upgrade)。

>[!NOTE]
>
>有关这些更改的任何问题，请联系 [Adobe 客户关怀](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。
>

## Campaign内部版本升级 {#ac-upgrade}

**您是否受影响？**

如果您受到下面详细介绍的[操作系统升级](#os-upgrade)和/或[数据库系统升级](#pg-upgrade)的影响，Adobe必须将您的Campaign环境升级到与这些系统兼容的[最新的8.4.3版本](../../v8/start/release-notes.md)。

**如何更新？**

作为托管Cloud Service客户，Adobe将与您联系并升级您的Campaign版本。

## 操作系统升级 {#os-upgrade}

**您是否受影响？**

如果您在Debian操作系统上运行Campaign，以便从最新的Debian安全更新中获益，则Adobe需要将您的Campaign基础架构移动到&#x200B;**Debian 11**。 请注意，Debian 9的安全支持将持续到2023年6月30日。

**如何更新？**

作为托管Cloud Service客户，Adobe将与您联系并升级您的环境。

## 数据库系统升级 {#pg-upgrade}

**您是否受影响？**

如果用于Campaign的数据库系统是PostgreSQL，则为了从最新的PostgreSQL创新和安全更新中获益，Adobe需要升级到&#x200B;**PostgreSQL 14**。 请注意，PostgreSQL 11将于2023年11月9日终止生命周期。

**如何更新？**

作为托管Cloud Service客户，Adobe将与您联系，并将您的数据库系统从PostgreSQL 11升级到PostgreSQL 14。
