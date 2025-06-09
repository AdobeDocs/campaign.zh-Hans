---
title: 使用 Campaign 和 SFDC
description: 了解如何使用Campaign和Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 41e39e046ec77de8b5e657ba76645898ff1cd2d7
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 3%

---

# 使用 Campaign 和 SFDC{#crm-sfdc}

了解如何配置Campaign CRM连接器以将Campaign v8连接到&#x200B;**Salesforce.com**。

完成配置后，通过专用工作流活动在系统之间执行数据同步。 [了解详情](crm-data-sync.md)。

>[!NOTE]
>
>Campaign [兼容性矩阵](../start/compatibility-matrix.md)中详细介绍了支持的SFDC版本。

请按照以下步骤配置专用外部帐户，以将Salesforce数据导入和导出到Adobe Campaign。

## 创建连接{#new-sfdc-external-account}

首先，您必须创建Salesforce外部帐户。

1. 浏览Campaign资源管理器的&#x200B;**[!UICONTROL Administration > Platform > External accounts]**&#x200B;节点并创建外部帐户。
1. 在&#x200B;**类型**&#x200B;部分中选择&#x200B;**[!UICONTROL Salesforce.com]**&#x200B;外部帐户。
1. 输入设置以启用连接。

   ![](assets/sfdc-external-account.png)

   要将Salesforce CRM外部帐户配置为与Adobe Campaign配合使用，您需要提供以下详细信息：

   * 在&#x200B;**[!UICONTROL Account]**&#x200B;字段中输入您的Salesforce登录名。
   * 输入您的Salesforce密码。
   * 您可以忽略&#x200B;**[!UICONTROL Client identifier]**&#x200B;字段。
   * 复制/粘贴您的Salesforce **[!UICONTROL Security token]**
   * 选择您的&#x200B;**[!UICONTROL API version]**。 Campaign [兼容性矩阵](../start/compatibility-matrix.md)中列出了支持的SFDC API版本。

1. 选择&#x200B;**启用**&#x200B;选项以在Campaign中激活帐户。

>[!NOTE]
>
>要批准设置，您需要注销并重新登录到Adobe Campaign客户端控制台。

## 选择要同步的表{#sfdc-create-tables}

您现在可以配置要同步的表。

1. 单击&#x200B;**[!UICONTROL Salesforce CRM configuration wizard...]**。
1. 选择要同步的表，然后启动进程。
1. 在&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;节点中检查Adobe Campaign中生成的架构。

   在Campaign中导入的&#x200B;**Salesforce**&#x200B;架构示例：

   ![](assets/sfdc-schemas.png)

## 同步枚举{#sfdc-enum-sync}

创建架构后，您可以自动将枚举从Salesforce同步到Adobe Campaign。

1. 从&#x200B;**[!UICONTROL Synchronizing enumerations...]**&#x200B;链接打开助手。
1. 选择与Adobe Campaign枚举匹配的Salesforce枚举。
您可以将Adobe Campaign枚举的所有值替换为CRM的值：要实现此目的，请在**[!UICONTROL Replace]**&#x200B;列中选择&#x200B;**[!UICONTROL Yes]**。

   ![](assets/sfdc-enum.png)

1. 单击&#x200B;**[!UICONTROL Next]**，然后单击&#x200B;**[!UICONTROL Start]**&#x200B;以开始导入枚举。

1. 浏览&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;节点以检查导入的值。 在[此页面](../config/ui-settings.md#enumerations)中了解有关枚举的更多信息。

Adobe Campaign和Salesforce.com现已连接。 您可以设置两个系统之间的数据同步。

要在Adobe Campaign数据和SFDC之间同步数据，请创建工作流并使用&#x200B;**[!UICONTROL CRM connector]**&#x200B;活动。

在此页面](crm-data-sync.md)中了解有关数据同步[的更多信息。
