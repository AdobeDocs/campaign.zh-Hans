---
title: 将技术用户迁移到Adobe Developer控制台
description: 了解如何将用户访问管理从Campaign Standard迁移到Campaign V8
feature: Technote
role: Admin
source-git-commit: ccd60b7ff54bb538ae21693eff41a3943f1c6c88
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 2%

---

# 从Campaign Standard到Campaign V8的用户访问管理 {#user-management-acs}

通过Adobe Campaign Standard和Adobe Campaign V8，用户可以定义和管理不同用户/操作员的权限。 这些权限包括授予用户访问产品各种功能的特定权限。 但是，这两种产品使用不同的方法和实施来管理用户访问权限。

Adobe Campaign Standard和Campaign V8中使用了以下概念来实现用户访问管理：

| Campaign Standard | Campaign V8 |
|---------|----------|
| 用户 | 操作员 |
| 角色 | 已命名权限 |
| 安全组 | 操作员组 |
| 组织实体 | 文件夹权限 |

## 从安全组到操作员组的迁移方法

>[!CAUTION]
>
>这些角色/已命名权限的功能在实施中可能有所不同，这可能会导致授权问题（例如，权限提升或功能中断）。 我们建议用户在转换后查看这些映射，以确保进行正确的访问控制。 [了解有关权限的更多信息](../../v8/start/manage-permissions.md)

下表概述了从Adobe Campaign Standard过渡到Campaign V8时用户角色组的迁移方法。 在Campaign Standard中，使用Campaign V8中称为&#x200B;**操作员组**&#x200B;的&#x200B;**安全组**&#x200B;为用户分配一组角色。 虽然某些安全组/操作员组是现成可用的，但如果需要，用户可以创建新组或修改现有组。

| | **Campaign Standard** | **促销活动V8** |
|---------|----------|---------|
| **术语**  | 安全组 | 操作员组 |

在Adobe Campaign Standard和Campaign V8中，**安全组**&#x200B;和&#x200B;**操作员组**&#x200B;均映射到管理控制台中的产品配置文件。 如果要向用户分配&#x200B;**安全组**&#x200B;或&#x200B;**操作员组**，您可以在管理控制台中链接相应的&#x200B;**产品配置文件**。 此关联在用户登录时同步。 [了解有关产品配置文件的更多信息](../../v8/start/manage-permissions.md)

| **Campaign Standard安全组** | **Campaign V8操作员组** |
|----------|---------|
| 管理员 | 管理员 |
| 投放主管 | 管理员 |
| 工作流监督者 | 工作流监督者  |

## 从用户角色到已命名权限的迁移方法

在Adobe Campaign Standard中，术语&#x200B;**用户角色**&#x200B;在Campaign V8中称为&#x200B;**Named right**。 下表概述了在Campaign V8中用于与Campaign Standard中的&#x200B;**用户角色**&#x200B;对应的&#x200B;**已命名权限**&#x200B;的术语。

| **Campaign Standard用户角色** | **Campaign V8已命名权限** | **描述**  |
|----------|---------|---------|
| 管理 | 管理 | 具有管理权限的用户具有实例的完全访问权限。 |
| 数据模型  | 管理 | 有权运行发布和创建自定义资源。 管理员可以在Campaign V8中使用与架构创建相关的功能。  |
| 可投放性  | 管理  | 有权批准以前分析的投放。  |
| 导出 | 导出 | 导出数据的权限。  |
| 文件访问  | 文件访问  | 有权批准以前分析的投放。  |
| 一般导入  | 导入  | 通用数据导入权限 |
| 准备投放 | 准备投放 | 有权创建、修改、准备和删除投放。  |
| SQL脚本执行 | SQL脚本执行 | 有权直接在数据库上执行任何SQL命令。 |
| 开始投放  | 开始投放  | 有权批准以前分析的投放。  |
| 系统命令执行 | 项目执行 | 有权在服务器上执行系统命令。 |
| 工作流 | 工作流 | 有权管理工作流开始、停止、暂停等的执行。 |

## 组织单位的迁移方法

在Adobe Campaign Standard中，**组织uni** t映射到Campaign V8中的现有&#x200B;**文件夹**&#x200B;层次结构模型，以维护类似的访问控制。 [了解有关文件夹管理的更多信息](../../v8/start/folder-permissions.md)

| | **Campaign Standard** | **促销活动V8** |
|---------|----------|---------|
| **术语**  | 组织实体 | 文件夹 |

## 从计划迁移方法

在Campaign V8中，**程序**&#x200B;表示为&#x200B;**文件夹**。 Campaign V8允许创建文件夹并允许限制对文件夹的访问。

通过使用&#x200B;**组**&#x200B;和&#x200B;**已命名的权限**，**操作员**&#x200B;可以被授予访问导航层次结构中的特定&#x200B;**文件夹**&#x200B;的权限，并且有权分配读取、写入和删除权限。 [了解有关文件夹管理的更多信息](../../v8/start/folder-permissions.md)

由于&#x200B;**项目**&#x200B;在Campaign V8中视为&#x200B;**文件夹**，因此可以采用与任何其他文件夹相同的方式管理其访问权限。 迁移后，Campaign Standard管理员可以执行以下步骤：

1. 在资源管理器中，右键单击任意文件夹并选择&#x200B;**[!UICONTROL Properties...]**。
1. 导航到&#x200B;**[!UICONTROL Security]**&#x200B;选项卡。
1. 根据所需的访问模型修改操作员组权限。 

## 用于访问REST API的产品配置文件映射 

要从Campaign V8中的执行实例访问事务性API，除&#x200B;**管理员**&#x200B;和&#x200B;**消息中心**&#x200B;产品配置文件之外，还需要新的&#x200B;**产品配置文件**。 此新&#x200B;**产品配置文件**&#x200B;将添加到Campaign Standard中的现有或预创建的技术帐户中。

迁移后，如果Campaign Standard用户不希望将其&#x200B;**技术帐户**&#x200B;关联到&#x200B;**管理员**&#x200B;产品配置文件，则应该审查其&#x200B;**产品配置文件映射**&#x200B;并分配适当的&#x200B;**产品配置文件**。 对于未来的集成，我们建议在&#x200B;**REST URL**&#x200B;中使用Campaign V8 **租户ID**，而不是使用以前的Campaign Standard **租户ID**。

## 向Campaign Standard操作员迁移对内置Campaign资源的访问权限

从Campaign Standard迁移的操作员将拥有对Campaign V8中特定内置资源的读取权限。

## 未迁移的安全组和角色 {#non-migrated-groups-roles}

以下是尚未转换的Campaign Standard角色列表：

* 默认中继帐户 

* 消息中心推送 

以下是尚未转换的Campaign Standard安全组映射列表。

* 消息中心代理

* 消息中心推送代理

* Adobe Experience Manager应用程序管理器

* 中继帐户
 


 

 


