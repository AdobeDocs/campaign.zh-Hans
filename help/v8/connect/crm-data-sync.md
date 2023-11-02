---
title: CRM连接器数据同步
description: 管理Campaign和您的CRM之间的数据
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin
level: Beginner
exl-id: 2a7ae88e-d47f-416b-84cd-986ab9be6aef
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 1%

---

# 在Campaign和您的CRM之间同步数据 {#data-synchronization}

Adobe Campaign与您的CRM之间的数据同步由管理 **CRM连接器** 工作流活动。

例如，要将Microsoft Dynamics数据导入Adobe Campaign，请创建以下类型的工作流：

![](assets/ms-dyn-wf.png)

此工作流通过Microsoft Dynamics导入联系人，将其与现有Adobe Campaign数据同步，删除重复联系人，并更新Adobe Campaign数据库。

此 **[!UICONTROL CRM Connector]** 需要配置活动才能同步数据。

![](assets/crm-connector-ms-dyn.png)

通过此活动，您可以：

* 从CRM导入 —  [了解详情](#importing-from-the-crm)
* 导出到CRM - [了解详情](#exporting-to-the-crm)
* 导入CRM中删除的对象 —  [了解详情](#importing-objects-deleted-in-the-crm)
* 删除CRM中的对象 —  [了解详情](#deleting-objects-in-the-crm)

![](assets/crm-remote-op.png)

选择与要配置同步的CRM匹配的外部帐户，然后选择要同步的对象：帐户、商机、潜在客户、联系人等。

![](assets/crm-remote-obj.png)

此活动的配置取决于执行的流程。 各种配置详见下文。

## 从CRM导入 {#importing-from-the-crm}

要通过Adobe Campaign中的CRM导入数据，您需要创建以下类型的工作流：

![](assets/crm-wf-import.png)

1. 选择 **[!UICONTROL Import from the CRM]** 操作。
1. 在 **[!UICONTROL Remote object]** 下拉列表，选择要导入的对象。 此对象与连接器配置期间在Adobe Campaign中创建的表之一匹配。
1. 在 **[!UICONTROL Remote fields]** 部分，输入要导入的字段。

   要添加字段，请单击 **[!UICONTROL Add]** 按钮，然后单击 **[!UICONTROL Edit expression]** 图标。

   如有必要，请使用 **[!UICONTROL Conversion]** 列。 中详细介绍了可能的转换类型 [本节](#data-format).

   >[!CAUTION]
   >
   >CRM中记录的标识符对于链接CRM和Adobe Campaign中的对象是必需的。 该复选框在获得批准时自动添加。
   >
   >对于增量数据导入，CRM端的上次修改日期也是强制性的。

1. 您可以根据需要筛选要导入的数据。 要执行此操作，请单击 **[!UICONTROL Edit the filter...]** 链接。

   在以下示例中，Adobe Campaign将仅导入自2021年11月1日以来记录了一些活动的联系人。

   ![](assets/crm-task-import-filter.png)

   >[!CAUTION]
   >
   >与数据过滤模式相关的限制详见 [本节](#filtering-data).

1. 选择 **[!UICONTROL Use automatic index...]** 选项，用于根据日期和上次修改情况自动管理CRM和Adobe Campaign之间的增量对象同步。

   如需详细信息，请参阅[此部分](#variable-management)。

### 管理变量 {#variable-management}

激活 **[!UICONTROL Automatic index]** 选项，用于仅收集自上次导入以来修改的对象。

![](assets/use-auto-index.png)

缺省情况下，上次同步的日期存储在配置窗口中指定的选项中： **LASTIMPORT_&lt;%=instance.internalName%>_&lt;%=activityName%>**.

>[!NOTE]
>
>此注释仅适用于通用部件 **[!UICONTROL CRM Connector]** 活动。 对于其他CRM活动，该流程是自动的。
>
>此选项必须手动创建并填充到 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. 它必须是文本选项，其值需要匹配以下格式： **yyyy/MM/dd hh:mm:ss**.
> 
>您需要手动更新此选项以进行任何进一步的导入。

您可以指定要考虑的远程CRM字段以标识最新更改。

默认情况下，使用以下字段（按指定顺序）：

* 对于Microsoft Dynamics： **修改**，
* 对于Salesforce.com ： **LastModifiedDate**， **SystemModstamp**.

激活 **[!UICONTROL Automatic index]** 选项生成三个变量，这些变量可通过在同步工作流中使用 **[!UICONTROL JavaScript code]** 键入activity。 这些活动包括：

* **vars.crmOptionName**：包含上次导入日期的选项的名称。
* **vars.crmStartImport**：上次数据导入的开始日期（包括）。
* **vars.crmEndDate**：上次数据导入的结束日期（已排除）。

  >[!NOTE]
  >
  >这些日期按以下格式显示： **yyyy/MM/dd hh:mm:ss**.

### 筛选数据 {#filtering-data}

要确保各种CRM的高效运行，需要使用以下规则创建过滤器：

* 每个过滤级别只能使用一种类型的运算符。
* 不支持AND NOT运算符。
* 比较可能只涉及null值（“为空”/“不为空”类型）或数字。 这意味着将对值（右侧列）进行评估，且此评估的结果必须是数字。 因此，不支持JOIN类型比较。
* 右侧列中包含的值是在JavaScript中进行评估的。
* 不支持联接比较。
* 左侧列中的表达式必须为字段。 它不能是多个表达式、数字等的组合。

### 排序方式 {#order-by}

在Microsoft Dynamics和Salesforce.com中，您可以按升序或降序对要导入的远程字段进行排序。

要执行此操作，请单击 **[!UICONTROL Order by]** 链接并将列添加到列表中。

列表中的列顺序是排序顺序：

![](assets/crm-import-order.png)

### 记录标识 {#record-identification}

您可以使用工作流中预先计算的群体，而不是导入CRM中包含（并可能经过筛选）的元素。

要执行此操作，请选择 **[!UICONTROL Use the population calculated upstream]** 选项并指定包含远程标识符的字段。

然后，选择要导入的集客群体的字段，如下所示：

![](assets/use-population-calc-upstream.png)

## 导出到CRM {#exporting-to-the-crm}

将Adobe Campaign数据导出到您的CRM中，以将其整个内容复制到CRM数据库中。

要将数据导出到CRM，请创建以下类型的工作流：

![](assets/crm-export-diagram.png)

1. 选择 **[!UICONTROL Export to CRM]** 操作。
1. 转到 **[!UICONTROL Remote object]** 下拉列表并选择要导出的对象。 此对象与连接器配置期间在Adobe Campaign中创建的表之一匹配。

   >[!CAUTION]
   >
   >的导出函数 **[!UICONTROL CRM Connector]** 活动可以在您的CRM上插入或更新字段。 要在CRM中启用字段更新，请指定远程表的主键。 如果缺少键，将插入数据，而不是更新数据。

1. 如果您需要执行更快的导出，请查看  **[!UICONTROL Export in Batches]** 选项。

   ![](assets/crm-export-batch.png)

1. 在 **[!UICONTROL Mapping]** 部分，单击 **[!UICONTROL New]** 以指定要导出的字段及其在CRM中的映射。

   要添加字段，请单击 **[!UICONTROL Add]** 按钮，然后单击 **[!UICONTROL Edit expression]** 图标。

   >[!NOTE]
   >
   >如果没有为字段定义匹配项，则无法更新值：这些值将直接插入您的CRM。

   如有必要，请使用 **[!UICONTROL Conversion]** 列。 中详细介绍了可能的转换类型 [本节](#data-format).

   >[!NOTE]
   >
   >要导出的记录列表和导出结果将保存在临时文件中，在工作流完成或重新启动之前，该文件将保持可访问状态。 这样，您便可以在出现错误时安全地启动进程。

## 其他配置 {#additional-configurations}

### 数据格式 {#data-format}

将数据格式导入或从CRM导入时，您可以动态转换数据格式。

要实现此目的，请选择要应用于匹配列的转换。

![](assets/crm-task-import.png)

此 **[!UICONTROL Default]** 模式应用自动数据转换，在大多数情况下，转换等同于数据的复制/粘贴。 但是，会应用时区管理。

其他可能的转换包括：

* **[!UICONTROL Date only]**：删除日期+时间类型字段。
* **[!UICONTROL Without time offset]**：取消在默认模式下应用的时区管理。
* **[!UICONTROL Copy/Paste]**：使用原始数据，例如字符串（无转化）。

### 错误处理 {#error-processing}

在数据导入或导出的框架中，您可以将特定进程应用于错误和拒绝。 要执行此操作，请选择 **[!UICONTROL Keep the rejections in a file]** 和 **[!UICONTROL Process errors]** 中的选项 **[!UICONTROL Behavior]** 选项卡。

![](assets/crm-export-options.png)

这些选项可添加相关的输出过渡。

![](assets/crm-export-transitions.png)

然后插入相关活动以处理数据。 例如，添加 **等待** 活动和计划错误重试。

此 **[!UICONTROL Reject]** 利用输出过渡，可访问包含与错误消息和代码相关的特定列的输出架构。 对于Salesforce.com ，此列为 **errorSymbol** （错误符号，不同于错误代码）， **错误消息** （错误上下文的描述）。

## 导入CRM中删除的对象 {#importing-objects-deleted-in-the-crm}

您可以将CRM中删除的对象导入Adobe Campaign。

1. 选择 **[!UICONTROL Import objects deleted in the CRM]** 操作。
1. 转到 **[!UICONTROL Remote object]** 下拉列表并选择进程涉及的对象。 此对象与连接器配置期间在Adobe Campaign中创建的表之一匹配。
1. 指定要在中考虑的删除时段 **[!UICONTROL Start date]** 和 **[!UICONTROL End date]** 字段（包含日期）。

   >[!CAUTION]
   >
   >删除期限必须与您的CRM特定限制一致。 例如，对于Salesforce.com ，超过30天前删除的元素将无法恢复。

## 删除 CRM 中的对象 {#deleting-objects-in-the-crm}

要删除CRM上的对象，请指定要删除的远程元素的主键。

此 **[!UICONTROL Behavior]** 选项卡允许您启用拒绝处理。 此选项为生成第二个输出转换 **[!UICONTROL CRM connector]** 活动。 有关详细信息，请参见 [处理时出错](#error-processing).
