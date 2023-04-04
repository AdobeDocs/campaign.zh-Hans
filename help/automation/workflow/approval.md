---
product: campaign
title: 审批
description: 审批
feature: Workflows, Approvals
exl-id: 9e57d21c-ce16-448d-97f1-8c6844acb37b
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# 审批{#approval}



安 **批准** 任务需要操作员的参与。 操作员被分配了一项任务，可以通过电子邮件、使用电子邮件中链接的网页或通过控制台做出响应。

## 任务分配 {#task-assignment}

默认情况下，会为一组运算符分配批准。 此组表示角色，例如“新闻稿内容组”或“新闻稿定位组”。 组中的每个运算符都可以回答，但只考虑第一个回复（多次批准时除外）。

如有必要，您可以将批准任务分配给单个运算符或过滤器定义的一组运算符。

* 要选择单个运算符，请选择 **[!UICONTROL Operator]** 值 **[!UICONTROL Assignment type]** 字段，并在 **[!UICONTROL Assignee]** 字段。

   ![](assets/s_advuser_validation_box_assign.png)

   >[!CAUTION]
   >
   >只有所选的操作员有权批准该任务。

* 您可以定义查询以筛选批准运算符。 为此，请选择 **[!UICONTROL Filter]** 值 **[!UICONTROL Assignment type]** 字段，然后单击 **[!UICONTROL Advanced parameters...]** 链接以定义筛选条件，如以下示例所示：

   ![](assets/s_advuser_validation_box_filter.png)

在单次审批的情况下，激活与操作员选择对应的过渡，完成任务：其他运算符无法回复。

在出现多个批准时，启用与每个运算符的选择相对应的过渡。 当组的所有运算符都已回复或任务过期时，任务即告完成。

此活动不会阻止处理，并且工作流可以在等待回复时执行其他任务。

操作员可以从控制台批准分配给该操作员的任务。 具有管理员权限的操作员可以查看和删除分配给任何操作员的任务，但无法回复这些任务。

修改活动的标题或消息正文不会影响当前任务，但是，修改可能的选项会直接影响当前任务，而当前任务会自动继承新的选项列表。

**批准** 类型任务可从访问 **[!UICONTROL Administration > Production > Objects created automatically > Approvals pending]** 节点：操作员可以通过此视图直接访问批准表单。

![](assets/s_advuser_validation_from_console.png)

## 属性 {#properties}

自定义变量可用于发送给审阅人的消息。 可以将它们插入到消息标题或正文中。

![](assets/edit_validation.png)

此 **[!UICONTROL Title]** 字段包含消息的标题：这是发送的电子邮件的主题。 标题以及消息正文是JavaScript模板，因此可以包含根据工作流上下文计算的值。

通过编辑器的下部分，可定义可能的答案列表。 每个答案都对应一个过渡。 名称是内部标识符，标签是将在选项列表中显示的文本。

单击 **[!UICONTROL Advanced parameters...]** 链接以选择要用于通知操作员的投放模板。 默认模板（内部名称“notifyAssignee”）获取标题和消息，并添加用于应答的网页链接。

可以修改此模板以个性化消息布局，但最好复制。 不得修改定向机制（外部文件、目标映射），因为通知需要该机制才能正确运行。

批准示例如 [定义审批](define-approvals.md).

## 输出参数 {#output-parameters}

* **[!UICONTROL response]**

   与响应相关的注释

* **[!UICONTROL responseOperator]**

   响应的运算符的标识符。 此字段是一个数值，但是 **[!UICONTROL String]** 字段。
