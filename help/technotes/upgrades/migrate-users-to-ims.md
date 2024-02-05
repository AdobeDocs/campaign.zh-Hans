---
title: 将Campaign操作员迁移到AdobeIdentity Management System (IMS)
description: 了解如何将Campaign操作员迁移到AdobeIdentity Management System (IMS)
exl-id: 58c130d8-8ba8-42ce-9ab4-a697125d3f85
source-git-commit: 1cdb21533138623fc603424503063cf3dbc2d94c
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 2%

---

# 将Campaign操作员迁移到AdobeIdentity Management System (IMS) {#migrate-users-to-ims}

从Campaign v8.6开始，改进了Campaign v8的身份验证过程。 所有操作员将使用 [AdobeIdentity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"} **仅限** 以连接到Campaign。 不再允许使用用户/密码（又称本机身份验证）连接。 Adobe建议在Campaign v8.5.2中执行此迁移，以便能够顺利迁移到Campaign v8.6。

作为Campaign Classicv7 Managed Services客户，如果您要迁移到Campaign v8，此过程也适用于您。

本文详细介绍了将技术操作员迁移到Adobe Developer控制台上的技术帐户所需的步骤。

## 更改了哪些内容？{#move-to-ims-changes}

使用Campaign v8时，所有常规用户都应已通过AdobeAdobe Campaign System (IMS)，使用其Adobe ID连接到Identity Management客户端控制台。 但是，对于某些较旧的配置，用户/密码连接仍然可用。 **从Campaign v8.6开始将不再允许这样做。**

此外，作为加强安全和身份验证过程的一部分，Adobe Campaign客户端应用程序现在使用IMS技术帐户令牌直接调用Campaign API。 有关技术操作员的迁移详情，请参阅中提供的专门文章 [此页面](ims-migration.md).

此更改适用于Campaign v8.5.2，并且将 **必需** 从Campaign v8.6开始。

## 您是否受影响？{#migrate-ims-impacts}

如果贵组织中的操作员正在使用其登录/密码（也称为）连接到Campaign客户端控制台。 受影响，必须将这些运算符迁移到Adobe IMS，如下所述。

迁移至 [AdobeIdentity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"} 安全是确保环境安全和标准化的必要条件，因为大多数其他Adobe Experience Cloud解决方案和应用程序已在IMS上。

## 如何迁移？{#ims-migration-procedure}

### 先决条件{#ims-migration-prerequisites}

在开始迁移过程之前，您必须联系Adobe代表（过渡经理），以便Adobe技术团队能够将您现有的操作员组和已命名权限迁移到AdobeIdentity Management System (IMS)。

### 关键步骤 {#ims-migration-steps}

下面列出了此迁移的关键步骤：

1. Adobe将您的环境升级到Campaign v8.5.2。
1. 升级后，您仍然可以使用这两种方法创建新用户，即作为本机用户或者使用IMS。
1. 您的内部Campaign管理员必须向Campaign客户端控制台上的所有本地Adobe添加唯一的电子邮件，并在完成后向用户过渡经理确认。 此步骤详见 [本节](#ims-migration-id).
1. 与Adobe合作，确定Adobe运行非技术用户（操作员）和产品配置文件的自动迁移的日期。 此步骤需要一个小时窗口，您的任何实例都不会出现停机。
1. 您的内部Campaign管理员会验证这些更改并提供注销。 进行此迁移后，不能再创建任何进一步的操作员使用其登录名和密码进行身份验证。

您现在可以将技术操作员迁移到Adobe Developer控制台，如中所述 [此技术说明](ims-migration.md). 如果您使用的是Campaign API，则必须执行此步骤。

完成此迁移后，请向您的Adobe过渡管理器确认：Adobe，然后将迁移标记为完成，并阻止创建新的本机用户和本机用户登录。 然后，您的环境将得到保护和标准化。

## 常见问题解答 {#ims-migration-faq}

### 我何时可以开始迁移？ {#ims-migration-start}

迁移到的先决条件 [AdobeIdentity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"} 是将您的环境升级到Campaign v8.5.2。

升级到Campaign v8.5.2后，您可以在暂存环境中启动IMS迁移，并相应地规划生产环境。

### 内部版本升级到Campaign v8.5.2后会发生什么？ {#ims-migration-after-upgrade}

将环境升级到Campaign v8.5.2后，您可以开始过渡到 [AdobeIdentity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"}.

在IMS迁移完成之前，仍允许创建新的本机用户。

### 迁移何时完成？ {#ims-migration-end}

最终用户迁移和将技术用户迁移到AdobeIdentity Management System (IMS)后，您必须联系Adobe过渡经理，以便Adobe将您的迁移标记为完成，阻止从客户端控制台创建用户并禁用本机用户登录。


### 如何在迁移后创建用户？ {#ims-migration-native}

完成完整IMS迁移后，Adobe将应用将阻止创建新本机用户的限制。 在IMS迁移完成之前，不会应用这些限制。

对于新客户 — 不允许从头开始创建新的本机用户。

作为Campaign管理员，您可以通过Adobe Admin Console和Campaign Client Console向组织用户授予权限。 用户使用其Adobe ID登录到Adobe Campaign。 了解详情，请参阅 [本文档](../../v8/start/gs-permissions.md).

### 如何为当前本机用户添加电子邮件？ {#ims-migration-id}

作为Campaign管理员，您必须从客户端控制台向所有本机用户添加电子邮件ID。 要执行此操作，请按照以下步骤进行：

1. 连接到客户端控制台并浏览到 **管理>访问管理>运算符**.
1. 在运算符列表中选择要更新的运算符。
1. 输入操作员的电子邮件 **联系方式** 操作员表单的部分。
1. 保存您的更改。

<!--You can also import a CSV file to update all your operator profiles with their email.-->


### 如何通过IMS登录Campaign？ {#ims-migration-log}

了解如何在中使用Adobe ID连接到Campaign [本节](../../v8/start/connect.md).

### 此迁移期间是否会发生停机？ {#ims-migration-downtime}

要完成迁移（迁移用户和产品配置文件），Adobe需要一小时的时间，任何实例（工作流等）无需停机。

在此时间范围内，所有Campaign用户都需要注销，并在完成向IMS的迁移后使用其Adobe ID重新登录。

### 在IMS用户迁移期间登录的用户会发生什么情况？ {#ims-migration-log-off}

Adobe强烈建议在迁移时段注销所有用户。

### 我组织中的用户已在使用IMS，我仍然需要执行IMS迁移吗？{#ims-migration-needed}

此迁移包括两个方面：最终用户迁移和技术用户迁移（在自定义代码的API中使用）。

如果您的所有用户（Campaign操作员）都在IMS上，则无需执行此迁移。 但是，您仍需要迁移可能在自定义代码中使用的技术用户。 请参阅[此页面](ims-migration.md)以了解详情。

完成此迁移后，必须联系Adobe过渡经理，以便Adobe完成迁移。

### 如何查看操作员的身份验证类型？

了解如何在Campaign中查看操作员的身份验证类型：

1. 从 **资源管理器**，访问 **管理** `>` **访问管理** `>` **运算符**.

1. 右键单击标题行并选择 **配置列表** 菜单。

   ![](assets/ims_2.png)

1. 添加 **帐户已禁用** 和 **身份验证类型** 作为 **输出列**.

   ![](assets/ims_1.png)

您现在可以看到您的 **运算符** 和他们的 **身份验证类型**.

![](assets/ims_3.png)

## 有用的链接 {#ims-useful-links}

* [将技术用户迁移到Adobe Developer控制台](ims-migration.md)
* [如何连接到Adobe Campaign v8](../../v8/start/connect.md)
* [Adobe Campaign v8中的访问和权限](../../v8/start/gs-permissions.md)
* [Adobe Campaign v8发行说明](../../v8/start/release-notes.md)
* [什么是AdobeIdentity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"}
