---
title: CRM连接器数据同步
description: 管理Campaign和您的CRM之间的数据
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin
level: Beginner
exl-id: 2a7ae88e-d47f-416b-84cd-986ab9be6aef
source-git-commit: e45799f0f3849d53d2c5f593bc02954b3a55fc28
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 1%

---

# 在Campaign和您的CRM之间同步数据 {#data-synchronization}

Adobe Campaign与CRM之间的数据同步由&#x200B;**CRM Connector**&#x200B;工作流活动管理。

例如，要将Microsoft Dynamics数据导入Adobe Campaign，请创建以下类型的工作流：

![](assets/ms-dyn-wf.png)

此工作流通过Microsoft Dynamics导入联系人，将其与现有Adobe Campaign数据同步，删除重复联系人，并更新Adobe Campaign数据库。

需要配置&#x200B;**[!UICONTROL CRM Connector]**&#x200B;活动以同步数据。

![](assets/crm-connector-ms-dyn.png)

通过此活动，您可以：

* 从CRM导入 — [了解详情](#importing-from-the-crm)
* 导出到CRM - [了解详情](#exporting-to-the-crm)
* 导入CRM中删除的对象 — [了解更多](#importing-objects-deleted-in-the-crm)
* 删除CRM中的对象 — [了解更多](#deleting-objects-in-the-crm)

![](assets/crm-remote-op.png)

选择与要配置同步的CRM匹配的外部帐户，然后选择要同步的对象：帐户、商机、潜在客户、联系人等。

![](assets/crm-remote-obj.png)

此活动的配置取决于执行的流程。 各种配置详见下文。

## 从CRM导入 {#importing-from-the-crm}

要通过Adobe Campaign中的CRM导入数据，您需要创建以下类型的工作流：

![](assets/crm-wf-import.png)

1. 选择&#x200B;**[!UICONTROL Import from the CRM]**&#x200B;操作。
1. 在&#x200B;**[!UICONTROL Remote object]**&#x200B;下拉列表中，选择要导入的对象。 此对象与连接器配置期间在Adobe Campaign中创建的表之一匹配。
1. 在&#x200B;**[!UICONTROL Remote fields]**&#x200B;部分中，输入要导入的字段。

   要添加字段，请单击工具栏中的&#x200B;**[!UICONTROL Add]**&#x200B;按钮，然后单击&#x200B;**[!UICONTROL Edit expression]**&#x200B;图标。

   如有必要，请使用&#x200B;**[!UICONTROL Conversion]**&#x200B;列的下拉列表更改数据格式。 在[此部分](#data-format)中详细介绍了可能的转换类型。

   >[!CAUTION]
   >
   >CRM中记录的标识符对于链接CRM和Adobe Campaign中的对象是必需的。 该复选框在获得批准时自动添加。
   >
   >对于增量数据导入，CRM端的上次修改日期也是强制性的。

1. 您可以根据需要筛选要导入的数据。 为此，请单击&#x200B;**[!UICONTROL Edit the filter...]**&#x200B;链接。

   在以下示例中，Adobe Campaign将仅导入自2021年11月1日以来记录了一些活动的联系人。

   ![](assets/crm-task-import-filter.png)

   >[!CAUTION]
   >
   >[此部分](#filtering-data)中详细介绍了与数据过滤模式相关的限制。

1. 选择&#x200B;**[!UICONTROL Use automatic index...]**&#x200B;选项以根据日期及其上次修改自动管理CRM和Adobe Campaign之间的增量对象同步。

   如需详细信息，请参阅[此小节](#variable-management)。

### 管理变量 {#variable-management}

激活&#x200B;**[!UICONTROL Automatic index]**&#x200B;选项以仅收集自上次导入以来修改的对象。

![](assets/use-auto-index.png)

上次同步的日期存储在配置窗口中指定的选项中，默认情况下为： **LASTIMPORT_&lt;%=instance.internalName%>_&lt;%=activityName%>**。

>[!NOTE]
>
>此注释仅适用于通用&#x200B;**[!UICONTROL CRM Connector]**&#x200B;活动。 对于其他CRM活动，该流程是自动的。
>
>必须在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**&#x200B;下手动创建并填充此选项。 它必须是文本选项，其值需要匹配以下格式： **`yyyy/MM/dd hh:mm:ss`**。
> 
>您需要手动更新此选项以进行任何进一步的导入。

您可以指定要考虑的远程CRM字段以标识最新更改。

默认情况下，使用以下字段（按指定顺序）：

* 对于Microsoft Dynamics： **modifiedon**，
* 对于Salesforce.com： **LastModifiedDate**，**SystemModstamp**。

激活&#x200B;**[!UICONTROL Automatic index]**&#x200B;选项会生成三个变量，它们可以通过&#x200B;**[!UICONTROL JavaScript code]**&#x200B;类型活动在同步工作流中使用。 这些活动包括：

* **vars.crmOptionName**：包含上次导入日期的选项的名称。
* **vars.crmStartImport**：上次数据导入的开始日期（包含）。
* **vars.crmEndDate**：上次数据导入的结束日期（已排除）。

  >[!NOTE]
  >
  >这些日期以下列格式显示： **`yyyy/MM/dd hh:mm:ss`**。

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

为此，请单击&#x200B;**[!UICONTROL Order by]**&#x200B;链接并将列添加到列表中。

列表中的列顺序是排序顺序：

![](assets/crm-import-order.png)

### 记录标识 {#record-identification}

您可以使用工作流中预先计算的群体，而不是导入CRM中包含（并可能经过筛选）的元素。

为此，请选择&#x200B;**[!UICONTROL Use the population calculated upstream]**&#x200B;选项并指定包含远程标识符的字段。

然后，选择要导入的集客群体的字段，如下所示：

![](assets/use-population-calc-upstream.png)

## 导出到CRM {#exporting-to-the-crm}

将Adobe Campaign数据导出到您的CRM中，以将其整个内容复制到CRM数据库中。

要将数据导出到CRM，请创建以下类型的工作流：

![](assets/crm-export-diagram.png)

1. 选择&#x200B;**[!UICONTROL Export to CRM]**&#x200B;操作。
1. 转到&#x200B;**[!UICONTROL Remote object]**&#x200B;下拉列表并选择要导出的对象。 此对象与连接器配置期间在Adobe Campaign中创建的表之一匹配。

   >[!CAUTION]
   >
   >**[!UICONTROL CRM Connector]**&#x200B;活动的导出函数可以在您的CRM上插入或更新字段。 要在CRM中启用字段更新，请指定远程表的主键。 如果缺少键，将插入数据，而不是更新数据。

1. 如果您需要执行更快的导出，请选中&#x200B;**[!UICONTROL Export in Batches]**&#x200B;选项。

   ![](assets/crm-export-batch.png)

1. 在&#x200B;**[!UICONTROL Mapping]**&#x200B;部分中，单击&#x200B;**[!UICONTROL New]**&#x200B;以指定要导出的字段及其在CRM中的映射。

   要添加字段，请单击工具栏中的&#x200B;**[!UICONTROL Add]**&#x200B;按钮，然后单击&#x200B;**[!UICONTROL Edit expression]**&#x200B;图标。

   >[!NOTE]
   >
   >如果没有为字段定义匹配项，则无法更新值：这些值将直接插入您的CRM。

   如有必要，请使用&#x200B;**[!UICONTROL Conversion]**&#x200B;列的下拉列表更改数据格式。 在[此部分](#data-format)中详细介绍了可能的转换类型。

   >[!NOTE]
   >
   >要导出的记录列表和导出结果将保存在临时文件中，在工作流完成或重新启动之前，该文件将保持可访问状态。 这样，您便可以在出现错误时安全地启动进程。

## 其他配置 {#additional-configurations}

### 数据格式 {#data-format}

将数据格式导入或从CRM导入时，您可以动态转换数据格式。

要实现此目的，请选择要应用于匹配列的转换。

![](assets/crm-task-import.png)

**[!UICONTROL Default]**&#x200B;模式应用自动数据转换，在大多数情况下相当于数据的复制/粘贴。 但是，会应用时区管理。

其他可能的转换包括：

* **[!UICONTROL Date only]**：删除日期+时间类型字段。
* **[!UICONTROL Without time offset]**：取消在默认模式下应用的时区管理。
* **[!UICONTROL Copy/Paste]**：使用原始数据，如字符串（无转换）。

### 错误处理 {#error-processing}

在数据导入或导出的框架中，您可以将特定进程应用于错误和拒绝。 为此，请在&#x200B;**[!UICONTROL Behavior]**&#x200B;选项卡中选择&#x200B;**[!UICONTROL Keep the rejections in a file]**&#x200B;和&#x200B;**[!UICONTROL Process errors]**&#x200B;选项。

![](assets/crm-export-options.png)

这些选项可添加相关的输出过渡。

![](assets/crm-export-transitions.png)

然后插入相关活动以处理数据。 例如，添加&#x200B;**等待**&#x200B;活动并安排错误重试。

通过&#x200B;**[!UICONTROL Reject]**&#x200B;输出转换，可访问包含与错误消息和代码相关的特定列的输出架构。 对于Salesforce.com，此列为&#x200B;**errorSymbol** （错误符号，不同于错误代码）、**errorMessage** （错误上下文的说明）。

## 导入CRM中删除的对象 {#importing-objects-deleted-in-the-crm}

您可以将CRM中删除的对象导入Adobe Campaign。

1. 选择&#x200B;**[!UICONTROL Import objects deleted in the CRM]**&#x200B;操作。
1. 转到&#x200B;**[!UICONTROL Remote object]**&#x200B;下拉列表并选择进程涉及的对象。 此对象与连接器配置期间在Adobe Campaign中创建的表之一匹配。
1. 指定要在&#x200B;**[!UICONTROL Start date]**&#x200B;和&#x200B;**[!UICONTROL End date]**&#x200B;字段中考虑的删除时段（包含日期）。

   >[!CAUTION]
   >
   >删除期限必须与您的CRM特定限制一致。 例如，对于Salesforce.com ，超过30天前删除的元素将无法恢复。

## 删除 CRM 中的对象 {#deleting-objects-in-the-crm}

要删除CRM上的对象，请指定要删除的远程元素的主键。

**[!UICONTROL Behavior]**&#x200B;选项卡允许您启用拒绝处理。 此选项为&#x200B;**[!UICONTROL CRM connector]**&#x200B;活动生成第二个输出转换。 有关详情，请参阅[处理](#error-processing)时出错。
