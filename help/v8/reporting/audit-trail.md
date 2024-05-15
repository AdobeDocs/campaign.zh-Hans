---
product: campaign
title: 审核记录
description: 了解如何使用Campaign审核记录监控实例
feature: Audit Trail, Monitoring, Workflows
exl-id: 6a937575-42d4-4dc5-8168-43c25bb2cde6
source-git-commit: b4b361a4aabd1b33554166c2638989b99a02baec
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 2%

---

# 审核记录{#audit-trail}

此 **[!UICONTROL Audit trail]** Adobe Campaign中的功能提供了对实例中重要实体所做的所有修改的粒度记录，通常是对实例的顺利操作产生重大影响的修改。 作为实时日志，它可以捕获操作和事件发生的详细列表。

>[!NOTE]
>
>Adobe Campaign不会审核在用户权限、模板、个性化或营销活动中所做的更改。\
>审核记录只能由实例的管理员管理。

+++ 了解有关审核记录可用实体的更多信息

* **架构审核跟踪**：允许您浏览对架构所做的更改，并识别进行这些修改的人和时间。

  有关架构的详细信息，请参阅 [页面](../dev/schemas.md).

* **工作流审核跟踪** 跟踪与您的工作流相关的所有操作，包括：

   * 开始
   * 暂停
   * 停止
   * 重新启动
   * 清除等于操作清除历史记录
   * 模拟在模拟模式下等于操作“开始”的项
   * 唤醒等于操作立即执行待处理任务
   * 无条件停止

  有关工作流的详细信息，请参阅此 [页面](../../automation/workflow/about-workflows.md).

  有关如何监测工作流的详细信息，请参阅 [专用部分](../../automation/workflow/monitor-workflow-execution.md).

* **选项审核跟踪** 用于检查活动以及对选项进行的最后修改。

  有关选项的更多信息，请参阅此 [页面](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options).

* **投放审核跟踪** 用于检查活动以及对投放进行的最后修改。

  有关投放的详细信息，请参阅此 [页面](../start/create-message.md).

* **外部帐户** 允许您检查对外部帐户所做的修改，这些修改由技术流程（如技术工作流或活动工作流）使用。

  有关外部帐户的更多信息，请参阅此 [页面](../config/external-accounts.md).

* **投放映射** 用于监视活动以及最近对投放映射所做的修改。

  有关投放映射的详细信息，请参阅此 [页面](../audiences/target-mappings.md).

* **Web应用程序** 允许您检查Campaign V8中对Web窗体所做的修改，该窗体用于创建包含输入和选择字段的页面，并且可能包含来自数据库的数据。

  有关Web应用程序的详细信息，请参阅此 [页面](../dev/webapps.md).

* **选件** 用于检查活动以及对优惠进行的最后修改。

  有关选件的更多信息，请参阅此 [页面](../interaction/interaction.md).

* **运算符** 用于监视活动以及最近对操作员进行的修改。

  有关操作员的详细信息，请参阅此 [页面](../interaction/interaction-operators.md).

+++

## 访问审核记录 {#accessing-audit-trail}

访问实例的 **[!UICONTROL Audit trail]**：

1. 访问 **[!UICONTROL Explorer]** 实例菜单。

1. 在 **[!UICONTROL Administration]** 菜单，选择 **[!UICONTROL Audit]** 则 **[!UICONTROL Audit Trail]**.

   ![](assets/audit-trail-1.png)

1. 此 **[!UICONTROL Audit trail]** 此时将打开一个窗口，其中包含实体列表。 Adobe Campaign将审核其他实体的创建、编辑和删除操作。

   选择其中一个实体以了解有关上次修改的更多信息。

1. 此 **[!UICONTROL Audit entity]** 窗口提供了有关所选实体的更多详细信息，例如：

   * **[!UICONTROL Type]**：工作流、选项、投放或架构。
   * **[!UICONTROL Entity]**：活动的内部名称。
   * **[!UICONTROL Modified by]**：上次修改此实体的人的用户名。
   * **[!UICONTROL Action]**：对此实体执行的上次操作，即已创建、已修改或已删除。
   * **[!UICONTROL Modification date]**：对此实体执行上次操作的日期。

   ![](assets/audit-trail-2.png)

>[!NOTE]
>
>默认情况下，保留期设置为180天 **[!UICONTROL Audit logs]**. 可以在部署向导中修改此值。

## 启用/禁用审核跟踪 {#enable-disable-audit-trail}

例如，如果您想在数据库上节省一些空间，则可以轻松地为特定活动激活或停用审核跟踪。

为实现此操作，请执行以下步骤：

1. 访问 **[!UICONTROL Explorer]** 实例菜单。

1. 在 **[!UICONTROL Administration]** 菜单，选择 **[!UICONTROL Platform]** 则 **[!UICONTROL Options]**.

1. 根据要激活/取消激活的实体，选择以下选项之一：

   * 对于工作流： **[!UICONTROL XtkAudit_Workflows]**
   * 对于架构： **[!UICONTROL XtkAudit_DataSchema]**
   * 对于选项： **[!UICONTROL XtkAudit_Option]**
   * 对于投放： **[!UICONTROL XtkAudit_Delivery]**
   * 对于外部帐户： **[!UICONTROL XtkAudit_ExtAccount]**
   * 对于投放映射： **[!UICONTROL XtkAudit_DeliveryMapping]**
   * 对于Web应用程序： **[!UICONTROL XtkAudit_WebApp]**
   * 对于选件： **[!UICONTROL XtkAudit_Offer]**
   * 对于运算符： **[!UICONTROL XtkAudit_Operator]**
   * 对于每个实体： **[!UICONTROL XtkAudit_Enable_All]**

   ![](assets/audit-trail-3.png)

1. 更改 **[!UICONTROL Value]** 1表示要启用实体，0表示要禁用实体。

   ![](assets/audit-trail-4.png)

1. 单击 **[!UICONTROL Save]**。
