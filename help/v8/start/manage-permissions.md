---
title: 向Campaign v8授予权限
description: 了解如何向Campaign v8用户授予权限
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 90154f84-b6a7-407c-93b7-9731dc94d9de
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '1632'
ht-degree: 1%

---

# 管理用户权限{#manage-permissions}

## 添加用户 {#add-users}

作为产品管理员，您可以添加用户并授予对Campaign的访问权限。

要添加用户，请执行以下步骤：

1. 在 [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"} 主页，选择 **添加用户**.

   ![](assets/add-a-user.png)

1. 输入用户的电子邮件地址。
1. 使用“+”符号选择要分配给用户的产品配置文件或用户组。

   ![](assets/add-a-product-profile.png)

   中列出了Campaign内置产品配置文件 [本节](#ootb-productprofiles).

   了解如何在中创建用户组 [本节](#user-groups)

1. 单击&#x200B;**保存**。用户即被添加，并显示在“用户”列表中。 如果您为用户分配管理员角色或产品配置文件，则他们会收到电子邮件通知。 用户必须单击该链接才能完成其个人资料。

在中了解有关在Admin Console中创建用户的更多信息 [此页面](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target="_blank"}.

新用户时 [登录Campaign](connect.md) 使用它们的Adobe ID，它们会被添加到客户端控制台的Campaign操作员列表中。 促销活动运算符存储在 **[!UICONTROL Administration > Access management > Operators]** Campaign资源管理器的文件夹。

## 使用产品配置文件{#product-profiles}

使用产品配置文件授予用户使用产品中所含功能的权限。

* 您可以为Admin Console上的每个产品创建一个或多个产品配置文件。
* 在每个产品配置文件中，您都可以分配用户和用户组（在您的组织中）。
* 当用户使用产品配置文件中指定的凭据登录时，将授予他们访问产品配置文件所基于的产品应用程序和服务的权限。

这些产品配置文件与存储在中的运算符组匹配 **[!UICONTROL Administration > Access management > Operator groups]** Campaign资源管理器的文件夹。

在Admin Console中，产品配置文件使用以下语法：

营销活动 —  `<your instance>`  — 操作员组的内部名称

例如，对于 **投放操作员** 组，则Admin Console中的产品配置文件为：

营销活动 — 测试 — 投放

您可以使用默认的产品配置文件或创建新产品配置文件。

### 创建产品配置文件{#create-product-profile}

要向Adobe添加新产品配置文件，您必须首先在Campaign客户端控制台中创建它，然后将其添加到Admin Console中。

例如，要创建“审阅者”产品配置文件，请执行以下步骤。

#### 在Campaign中创建运算符组{#create-op-group}

1. 连接到Campaign，打开资源管理器，然后浏览 **[!UICONTROL Administration > Access management > Operator groups]**.
1. 单击 **[!UICONTROL New]**，并定义操作员组的名称并设置其内部名称（“审阅者”）。
   ![](assets/new-op-group.png)
1. 通过选择已命名权限来定义关联的权限。 有关已命名权限的详情，请参见 [本节](#use-named-rights)
1. 保存新的操作员组。

#### 在Admin Console中创建产品配置文件{#create-profile-in-admin-console}

1. 连接到 [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"}.
1. 从 **产品和服务** 打开促销活动产品。
1. 单击 **新建配置文件** 并输入要创建的产品配置文件的名称，其中应使用正确的确切语法，如前所述 [此处](#product-profiles). 例如，我们输入：campaign - `<your-instance-name>`  — 审阅者

   ![](assets/new-product-profile-ui.png)

1. 保存您的更改。

您现在可以将用户添加到此新产品用户档案，如中所述 [本节](#add-users).

最佳实践为将产品配置文件分配给用户组。 按用户管理权限不是一种可持续的模式。


### 默认产品配置文件和操作员组 {#ootb-productprofiles}

Adobe Campaign附带内置功能 **产品配置文件** 在Adobe启用您的环境时定义。

![](assets/ootb-product-profiles.png)

这些产品配置文件与Campaign匹配 **操作员组**. 默认运算符组及其 [已命名权限](#use-named-rights) 列于下文：

1. **[!UICONTROL Administrator]** （管理员）

   此组中的操作员对此实例具有完全访问权限。 管理员是可以访问用户界面中最技术部分的用户。

   此组包含以下已命名权限：

   * **[!UICONTROL ADMINISTRATION]**：有权执行/创建/编辑/删除任何对象，例如工作流、投放、脚本等

1. **[!UICONTROL Delivery operators]** (投放)

   此组中的操作员负责管理投放：他们可访问创建和准备投放所需的主要资源（活动类型、投放映射、默认模板、个性化块等）。

   此组包含以下已命名权限：

   * **[!UICONTROL PREPARE DELIVERIES]**：有权创建、编辑和开始投放分析，
   * **[!UICONTROL START DELIVERIES]**：有权批准之前分析的投放。

1. **[!UICONTROL Campaign managers]** （操作）

   此组中的操作员可以管理营销活动：通过此组，您可以访问链接到营销活动的对象（计划、项目、工作流、预算等） 在架构内 **[!UICONTROL Campaign]** (可选Adobe Campaign模块)。

   此组包含以下已命名权限：

   * **[!UICONTROL INSERT FOLDERS]**：有权将文件夹插入Adobe Campaign树（前提是您对有关分支具有编辑权限），
   * **[!UICONTROL WORKFLOW]**：使用工作流的权限。

   >[!NOTE]
   >
   >此组不允许操作员开始投放。

1. **[!UICONTROL Content contributors]** （内容）

   此组中的用户可以访问上下文中的内容文件夹 **[!UICONTROL Content management]** 加载项。 此组未授予任何其他权限。

1. **[!UICONTROL Access to reports]** （报告）

   此组是为外部操作员保留的，用于通过 [Web访问](../start/campaign-ui.md#web-browser).

1. **[!UICONTROL Workflow execution]** （工作流）

   此 **[!UICONTROL Workflow execution]** 组允许您控制定位工作流的执行和批准：已命名权限的工作流将映射到此组的操作员。 除了对数据文件的访问权限之外，还需要对工作流执行所有操作。 默认情况下， **[!UICONTROL Workflow execution]** 组对标准定位工作流文件和工作流模板具有只读访问权限。 此组中的操作员还具有对待处理审批文件的读写访问权限。

1. **[!UICONTROL Workflow supervisors]** （工作流主管）

   此组中的用户可管理工作流批准，并在出现与活动工作流相关的警报时收到电子邮件通知。

1. **本地/中央管理** （中央/本地）

   此组中的用户可以使用 **[!UICONTROL Distributed marketing]** 加载项。

1. **[!UICONTROL Offer managers]** (优惠)

   此组中的操作员可以在使用交互加载项时创建和维护优惠。 [了解详情](../interaction/interaction-operators.md)。

   此组包含以下已命名权限：

   * **[!UICONTROL INSERT FOLDERS]**：有权将文件夹插入Adobe Campaign树（前提是您对有关分支具有编辑权限），
   * **[!UICONTROL EDIT FOLDERS]**：更改文件夹属性（如内部名称、标签、关联的图像、子文件夹顺序等）的权利。

   分配给选件管理器的权限允许他们执行以下任务：

   * 修改 **[!UICONTROL Design]** 环境。
   * 视图 **[!UICONTROL Live]** 环境。
   * 配置管理函数（预定义空格和过滤器）。
   * 创建和更新类别。
   * 创建优惠.
   * 配置优惠资格。
   * 批准选件。

   >[!NOTE]
   >
   >**优惠经理** 仅当未指定审阅人，或在优惠模板中已将他们设置为审阅人时，才能批准优惠。

   中提供了每个环境的选件管理器权限矩阵 [此页面](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## 使用用户组{#user-groups}

您可以使用Admin Console创建用户组并向其分配用户。

用户组是必须获得一组共享权限的不同用户的集合。 了解如何在中创建用户组 [本节](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target="_blank"}.

您可以将产品配置文件分配给用户组。 因此，该组中的所有用户都将获得相同的产品权限集。

## 已命名权限{#use-named-rights}

Adobe Campaign提供了一组已命名权限，可让您定义分配给用户和用户组的权限。 这些权限可以从 **[!UICONTROL Administration > Access management > Named rights]** Campaign资源管理器的文件夹。

已命名权限将权限授予：

* 执行操作例如， **分析** 投放编辑器中的按钮已为的成员激活 **投放操作员** 拥有 **准备投放** 已命名权限

* 对文件夹的访问操作员组的成员资格可以通过更改文件夹的安全性设置来授予或限制对文件夹的访问权限。 [了解详情](folder-permissions.md#restrict-access-to-a-folder)。

   例如，它可以影响： **写入权限** 要创建新实体（如投放、用户档案等）， **读取权限** 要使用实体， **删除访问权限** 以删除实体。

Adobe Campaign中的默认命名权限包括：

* **[!UICONTROL ADMINISTRATION]**：运算符和 **[!UICONTROL ADMINISTRATION]** 权限对实例具有完全访问权限。 管理员用户可以执行/创建/编辑/删除任何对象，例如工作流、投放、脚本等。

* **[!UICONTROL APPROVAL ADMINISTRATION]**：您可以在工作流和投放中设置多个批准步骤，以确保当前状态已由分配的操作员或组批准。 具有的用户 **[!UICONTROL APPROVAL ADMINISTRATION]** 权限可以设置批准步骤，还可以分配应批准这些步骤的操作员或操作员组。

* **[!UICONTROL CENTRAL]**：集中管理权限（分布式营销）。

* **[!UICONTROL DELETE FOLDER]**：有权删除文件夹。 凭借此权限，用户可以从资源管理器视图中删除文件夹。

* **[!UICONTROL EDIT FOLDERS]**：更改文件夹属性（如内部名称、标签、关联的图像、子文件夹顺序等）的权利。

* **[!UICONTROL EXPORT]**：用户可以使用将数据从其Adobe Campaign实例导出到服务器或本地计算机上的文件中。 **[!UICONTROL EXPORT]** 工作流活动。

* **[!UICONTROL FILES ACCESS]**：有权通过脚本读取和写入文件，该脚本可以写入 **[!UICONTROL JavaScript]** 用于在服务器上读/写文件的工作流活动。

* **[!UICONTROL IMPORT]**：一般数据导入权限。 **[!UICONTROL IMPORT]** 允许您将数据导入到任何其他表中，而 **[!UICONTROL RECIPIENT IMPORT]** 权限仅允许导入收件人表。

* **[!UICONTROL INSERT FOLDERS]**：有权插入文件夹。 具有的用户 **[!UICONTROL INSERT FOLDERS]** 可在资源管理器视图的文件夹树中创建新文件夹。

* **[!UICONTROL LOCAL]**：本地管理权限（分布式营销）。

* **[!UICONTROL MERGE]**：有权将选定的记录合并为一条记录。 如果收件人作为重复项存在，则 **[!UICONTROL MERGE]** 权限允许用户选择重复项并将它们合并到主收件人中。

* **[!UICONTROL PREPARE DELIVERIES]**：有权创建、编辑和保存投放。 具有的用户 **[!UICONTROL PREPARE DELIVERIES]** 右侧还可以启动投放分析过程。

* **[!UICONTROL PRIVACY DATA RIGHT]**：有权收集和删除隐私数据。 [了解详情](privacy.md)。

* **[!UICONTROL PROGRAM EXECUTION]**：有权执行各种编程语言的命令。

* **[!UICONTROL RECIPIENT IMPORT]**：导入收件人的权限。 具有的用户 **[!UICONTROL RECIPIENT IMPORT]** 权限可以将本地文件导入收件人表。

* **[!UICONTROL SQL SCRIPT EXECUTION]** 有权直接在数据库上执行任何SQL命令。

* **[!UICONTROL START DELIVERIES]**：有权批准之前分析的投放。 投放分析后，投放将在各种批准步骤暂停，并且需要获得批准才能恢复。 具有的用户 **[!UICONTROL START DELIVERIES]** 允许权限审批投放。

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**：有权使用SQL数据管理活动编写自己的SQL脚本，以便创建和填充工作表。 [了解详情](../../automation/workflow/sql-data-management.md)。

* **[!UICONTROL WORKFLOW]**：此已命名权限特定于工作流：它允许您创建、启动和停止工作流。 已命名权限需要工作流文件的读取权限才能适用。 对于定位工作流，请阅读右上 **[!UICONTROL Profiles and Targets]** 文件夹是必需的。


* **[!UICONTROL WEBAPP]**：有权使用Web应用程序。

>[!NOTE]
>
>此列表可能会因环境中安装的加载项而异。



## 其他资源{#additional-res}

* [管理工作流的权限](../../automation/workflow/managing-rights.md)
* [管理分布式营销的权限](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [管理交互模块的权限](../interaction/interaction-operators.md)
* [筛选对架构的访问权限](../dev/filter-schema.md)
* [限制 PI 视图](../dev/restrict-pi-view.md)
