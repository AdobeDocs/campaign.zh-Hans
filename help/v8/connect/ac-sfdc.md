---
title: 使用 Campaign 和 SFDC
description: 了解如何使用Campaign和Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 3%

---

# 使用 Campaign 和 SFDC{#crm-sfdc}

了解如何配置Campaign CRM连接器以将Campaign v8连接到 **Salesforce.com**.

完成配置后，系统之间的数据同步将通过专用工作流活动执行。 [了解详情](crm-data-sync.md)。

>[!NOTE]
>
>有关支持的SFDC版本的详情，请参见Campaign [兼容性矩阵](../start/compatibility-matrix.md).

按照以下步骤配置专用外部帐户，以将Salesforce数据导入和导出到Adobe Campaign。

## 创建连接{#new-sfdc-external-account}

首先，必须创建Salesforce外部帐户。

1. 浏览 **[!UICONTROL Administration > Platform > External accounts]** 节点，并创建外部帐户。
1. 选择 **[!UICONTROL Salesforce.com]** 中的外部帐户 **类型** 部分。
1. 输入设置以启用连接。

   ![](assets/sfdc-external-account.png)

   要将Salesforce CRM外部帐户配置为与Adobe Campaign配合使用，您需要提供以下详细信息：

   * 在中输入Salesforce登录名 **[!UICONTROL Account]** 字段。
   * 输入您的Salesforce密码。
   * 您可以忽略 **[!UICONTROL Client identifier]** 字段。
   * 复制/粘贴您的Salesforce **[!UICONTROL Security token]**
   * 选择您的 **[!UICONTROL API version]**. Campaign中列出了支持的SFDC API版本 [兼容性矩阵](../start/compatibility-matrix.md).

1. 选择 **启用** 用于在Campaign中激活帐户的选项。

>[!NOTE]
>
>要批准设置，您需要注销并重新登录到Adobe Campaign控制台。

## 选择要同步的表{#sfdc-create-tables}

您现在可以配置要同步的表。

1. 单击 **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. 选择要同步的表，然后启动进程。
1. 在中检查Adobe Campaign中生成的架构 **[!UICONTROL Administration > Configuration > Data schemas]** 节点。

   示例 **Salesforce** 在Campaign中导入的架构：

   ![](assets/sfdc-schemas.png)

## 同步枚举{#sfdc-enum-sync}

创建架构后，您可以自动将枚举从Salesforce同步到Adobe Campaign。

1. 从以下位置打开助手  **[!UICONTROL Synchronizing enumerations...]** 链接。
1. 选择与Salesforce枚举匹配的Adobe Campaign枚举。
您可以将Adobe Campaign枚举的所有值替换为CRM的值：要实现此目的，请选择 **[!UICONTROL Yes]** 在 **[!UICONTROL Replace]** 列。

   ![](assets/sfdc-enum.png)

1. 单击 **[!UICONTROL Next]** 然后 **[!UICONTROL Start]** 以开始导入明细列表。

1. 浏览 **[!UICONTROL Administration > Platform > Enumerations]** 节点以检查导入的值。 要了解有关明细列表的详细信息，请参阅 [此页面](../config/ui-settings.md#enumerations).

Adobe Campaign和Salesforce.com现已连接。 您可以设置两个系统之间的数据同步。

要在Adobe Campaign数据和SFDC之间同步数据，请创建工作流并使用 **[!UICONTROL CRM connector]** 活动。

了解有关数据同步的更多信息 [本页内容](crm-data-sync.md).
