---
title: 授予Campaign v8的权限
description: 了解如何向Campaign v8用户授予权限
feature: Permissions
role: User, Admin
level: Beginner
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '1640'
ht-degree: 1%

---

# 管理用户权限{#manage-permissions}

## 添加用户 {#add-users}

作为产品管理员，您可以添加用户并授予对Campaign的访问权限。

要添加用户，请执行以下步骤：

1. 在 [Admin Console](https://adminconsole.adobe.com/enterprise){target=&quot;_blank&quot;}主页，选择 **添加用户**.

   ![](assets/add-a-user.png)

1. 输入用户的电子邮件地址。
1. 使用“+”符号选择要分配给用户的产品配置文件或用户组。

   ![](assets/add-a-product-profile.png)

   Campaign内置产品配置文件列在 [此部分](#ootb-productprofiles).

   了解如何在 [此部分](#user-groups)

1. 单击&#x200B;**保存**。用户即会添加，并显示在用户列表中。 如果您向用户分配管理员角色或产品配置文件，则用户会收到电子邮件通知。 用户必须单击该链接才能完成其配置文件。

了解有关在Admin Console中创建用户的更多信息，请参阅 [本页](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target=&quot;_blank&quot;}。

新用户时 [登录到Campaign](connect.md) 使用其Adobe ID，可将其添加到客户端控制台的Campaign运算符列表。 促销活动运算符存储在 **[!UICONTROL Administration > Access management > Operators]** Campaign资源管理器的文件夹。

## 使用产品配置文件{#product-profiles}

使用产品配置文件为用户提供产品中包含的功能。

* 对于Admin Console上的每个产品，您可以创建一个或多个产品配置文件。
* 在每个产品配置文件中，分配用户和用户组（在您的组织中）。
* 当用户使用在产品配置文件中指定的凭据登录时，将授予他们访问产品配置文件所基于产品的应用程序和服务的权限。

这些产品配置文件与存储在 **[!UICONTROL Administration > Access management > Operator groups]** Campaign资源管理器的文件夹。

在Admin Console中，产品配置文件使用以下语法：

营销活动 —  `<your instance>`  — 操作员组的内部名称

例如，对于 **投放运算符** 组，则Admin Console中的产品用户档案为：

营销活动 — 测试 — 投放

您可以使用默认的产品配置文件或创建新产品配置文件。

### 创建产品配置文件{#create-product-profile}

要向Adobe添加新的产品用户档案，您必须先在Campaign客户端控制台中创建该用户档案，然后将其添加到Admin Console中。

例如，要创建“审阅人”产品用户档案，请执行以下步骤。

#### 在Campaign中创建运算符组{#create-op-group}

1. 连接到Campaign，打开资源管理器，然后浏览 **[!UICONTROL Administration > Access management > Operator groups]**.
1. 单击 **[!UICONTROL New]**，并定义运算符组的名称并设置其内部名称（“审阅者”）。
   ![](assets/new-op-group.png)
1. 通过选择命名权限定义关联的权限。 有关命名权限的详细信息，请参阅 [此部分](#use-named-rights)
1. 保存新的运算符组。

#### 在Admin Console中创建产品配置文件{#create-profile-in-admin-console}

1. 连接到 [Admin Console](https://adminconsole.adobe.com/enterprise){target=&quot;_blank&quot;}。
1. 从 **产品和服务** 打开Campaign产品。
1. 单击 **新建用户档案** 并输入要创建的产品配置文件的名称，其语法完全正确，如所述 [此处](#product-profiles). 在示例中，我们输入：营销活动 —  `<your-instance-name>`  — 审阅人

   ![](assets/new-product-profile-ui.png)

1. 保存更改。

您现在可以将用户添加到此新产品配置文件，如 [此部分](#add-users).

最佳做法是将产品配置文件分配给用户组。 按用户管理权限不是一种可持续的模式。


### 默认产品配置文件和运算符组 {#ootb-productprofiles}

Adobe Campaign内置 **产品配置文件** 在Adobe启用环境时定义。

![](assets/ootb-product-profiles.png)

这些产品配置文件与Campaign匹配 **运算符组**. 默认运算符组及其 [已命名权限](#use-named-rights) 如下所示：

1. **[!UICONTROL Administrator]** （管理员）

   此组中的运算符对实例具有完全访问权限。 管理员可以访问用户界面中技术含量最高的部分。

   此组包含以下命名权限：

   * **[!UICONTROL ADMINISTRATION]**:有权执行/创建/编辑/删除任何对象，如工作流、交付、脚本等。

1. **[!UICONTROL Delivery operators]** (投放)

   此组中的运算符负责管理投放：利用这些资源，可访问创建和准备投放所需的主要资源（营销活动分类、投放映射、默认模板、个性化块等）。

   此组包含以下命名权限：

   * **[!UICONTROL PREPARE DELIVERIES]**:有权创建、编辑和启动投放分析，
   * **[!UICONTROL START DELIVERIES]**:有权批准之前分析的投放。

1. **[!UICONTROL Campaign managers]** （操作）

   此组中的操作员可以管理营销活动：它允许您访问链接到营销策划的对象（计划、项目、工作流、预算等） 在 **[!UICONTROL Campaign]** (可选的Adobe Campaign模块)。

   此组包含以下命名权限：

   * **[!UICONTROL INSERT FOLDERS]**:将文件夹插入Adobe Campaign树的权限（前提是您拥有相关分支的编辑权限），
   * **[!UICONTROL WORKFLOW]**:有权使用工作流。

   >[!NOTE]
   >
   >此组不允许运算符开始投放。

1. **[!UICONTROL Content contributors]** （内容）

   此组中的用户可以在 **[!UICONTROL Content management]** 附加组件。 此组不会授予任何其他权限。

1. **[!UICONTROL Access to reports]** （报告）

   此组为外部操作员保留，用于通过 [Web访问](../start/campaign-ui.md#web-browser).

1. **[!UICONTROL Workflow execution]** （工作流）

   的 **[!UICONTROL Workflow execution]** 群组允许您控制定位工作流的执行和批准：名为权限的工作流已映射到此组的运算符。 除了对数据文件的访问权限之外，工作流上的所有操作都需要此参数。 默认情况下， **[!UICONTROL Workflow execution]** 群组对标准定位工作流文件和工作流模板具有只读访问权限。 此组中的操作员也具有对待批准文件的读写权限。

1. **[!UICONTROL Workflow supervisors]** (workflowSupervisor)

   此组中的用户管理工作流批准，并在收到与促销活动工作流有关的警报时收到电子邮件通知。

1. **本地/中央管理** （中央/本地）

   此群组中的用户可以使用 **[!UICONTROL Distributed marketing]** 附加组件。

1. **[!UICONTROL Offer managers]** (优惠)

   使用交互加载项时，此组中的运算符可以创建和维护选件。 [了解详情](../interaction/interaction-operators.md)。

   此组包含以下命名权限：

   * **[!UICONTROL INSERT FOLDERS]**:将文件夹插入Adobe Campaign树的权限（前提是您拥有相关分支的编辑权限），
   * **[!UICONTROL EDIT FOLDERS]**:有权更改文件夹属性，如内部名称、标签、关联图像、子文件夹顺序等。

   分配给选件管理器的权限允许他们执行以下任务：

   * 修改 **[!UICONTROL Design]** 环境。
   * 查看 **[!UICONTROL Live]** 环境。
   * 配置管理功能（预定义的空格和过滤器）。
   * 创建和更新类别。
   * 创建优惠.
   * 配置选件资格。
   * 批准选件。

   >[!NOTE]
   >
   >**选件经理** 只有未指定审核者，或者在选件模板中将他们设置为审核者时，才能批准选件。

   每个环境的选件管理器权限列表在 [本页](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## 使用用户组{#user-groups}

您可以使用Admin Console创建用户组并为其分配用户。

用户组是不同用户的集合，这些用户必须获得一组共享权限。 了解如何在 [此部分](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target=&quot;_blank&quot;}。

您可以将产品配置文件分配给用户组。 因此，该组中的所有用户都将收到相同的产品权限集。

## 已命名权限{#use-named-rights}

Adobe Campaign附带一组命名权限，通过该权限可定义分配给用户和组的权限。 这些权限可从 **[!UICONTROL Administration > Access management > Named rights]** Campaign资源管理器的文件夹。

命名权限授予以下用户权限：

* 执行操作例如， **分析** 按钮 **投放运算符** 具有 **准备投放** 已命名右侧

* 对文件夹的访问权限操作员组的成员资格可以通过更改文件夹的安全设置，授予或限制对文件夹的访问权限。 [了解详情](folder-permissions.md#restrict-access-to-a-folder)。

   例如，它会影响： **写入访问** 创建新实体（如投放、用户档案等）， **读取访问** 使用实体， **删除访问权限** 删除实体。

Adobe Campaign中的默认命名权限包括：

* **[!UICONTROL ADMINISTRATION]**:运算符 **[!UICONTROL ADMINISTRATION]** 权限对实例具有完全访问权限。 管理员用户可以执行/创建/编辑/删除任何对象，如工作流、交付、脚本等。

* **[!UICONTROL APPROVAL ADMINISTRATION]**:您可以在工作流和投放中设置多个批准步骤，以确保已分配的操作员或组批准当前状态。 具有 **[!UICONTROL APPROVAL ADMINISTRATION]** 权限可以设置批准步骤，还可以分配应批准这些步骤的操作员或操作员组。

* **[!UICONTROL CENTRAL]**:中央管理权（分布式营销）。

* **[!UICONTROL DELETE FOLDER]**:有权删除文件夹。 在此权限下，允许用户从资源管理器视图中删除文件夹。

* **[!UICONTROL EDIT FOLDERS]**:有权更改文件夹属性，如内部名称、标签、关联图像、子文件夹顺序等。

* **[!UICONTROL EXPORT]**:用户可以使用将其Adobe Campaign实例中的数据导出到服务器或本地计算机上的文件 **[!UICONTROL EXPORT]** 工作流活动。

* **[!UICONTROL FILES ACCESS]**:有权通过脚本读取和写入文件，该脚本可在 **[!UICONTROL JavaScript]** 工作流活动，用于在服务器上读/写文件。

* **[!UICONTROL IMPORT]**:通用数据导入的权限。 **[!UICONTROL IMPORT]** 允许您将数据导入任何其他表，而 **[!UICONTROL RECIPIENT IMPORT]** right仅允许导入到收件人表中。

* **[!UICONTROL INSERT FOLDERS]**:有权插入文件夹。 具有 **[!UICONTROL INSERT FOLDERS]** 在“资源管理器”视图的文件夹树中，右侧可以创建新文件夹。

* **[!UICONTROL LOCAL]**:本地管理权（分布式营销）。

* **[!UICONTROL MERGE]**:有权将选定的记录合并到一个记录中。 如果收件人存在为重复项，则 **[!UICONTROL MERGE]** 右侧允许用户选择重复项并将其合并到主收件人中。

* **[!UICONTROL PREPARE DELIVERIES]**:有权创建、编辑和保存投放。 具有 **[!UICONTROL PREPARE DELIVERIES]** 右侧还可以启动投放分析流程。

* **[!UICONTROL PRIVACY DATA RIGHT]**:收集和删除隐私数据的权利。 [了解详情](privacy.md)。

* **[!UICONTROL PROGRAM EXECUTION]**:以各种编程语言执行命令的权利。

* **[!UICONTROL RECIPIENT IMPORT]**:有权导入收件人。 具有 **[!UICONTROL RECIPIENT IMPORT]** 权限可以将本地文件导入收件人表。

* **[!UICONTROL SQL SCRIPT EXECUTION]** 有权直接在数据库上执行任何SQL命令。

* **[!UICONTROL START DELIVERIES]**:有权批准之前分析的投放。 投放分析后，投放将在各个批准步骤中暂停，并需要获得批准才能继续。 具有 **[!UICONTROL START DELIVERIES]** 允许批准投放。

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**:有权使用SQL数据管理活动编写您自己的SQL脚本，以创建和填充工作表。 [了解详情](../../automation/workflow/sql-data-management.md)。

* **[!UICONTROL WORKFLOW]**:此命名权限专用于工作流：它允许您创建、启动和停止工作流。 需要具有工作流文件的读取权限，才能适用命名权限。 对于定位工作流，请阅读 **[!UICONTROL Profiles and Targets]** 文件夹。


* **[!UICONTROL WEBAPP]**:有权使用Web应用程序。

>[!NOTE]
>
>此列表可能因环境中安装的加载项而异。



## 其他资源{#additional-res}

* [管理工作流的权限](../../automation/workflow/managing-rights.md)
* [管理分布式营销的权限](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [管理交互模块的权限](../interaction/interaction-operators.md)
* [筛选对架构的访问](../dev/filter-schema.md)
* [限制 PI 视图](../dev/restrict-pi-view.md)
