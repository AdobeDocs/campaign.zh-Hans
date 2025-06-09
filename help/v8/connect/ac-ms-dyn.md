---
title: 使用 Campaign 和 Microsoft Dynamics
description: 了解如何使用Campaign和Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: d80a39d7f0df939d0e9e3f782d5d9aef3d459a32
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 2%

---

# 使用Campaign和Microsoft Dynamics 365{#crm-ms-dynamics}

在跨渠道通信上激活您的CRM数据：了解如何将联系人从&#x200B;**Microsoft Dynamics 365**&#x200B;传递到Adobe Campaign，并将营销活动效果数据（发送、打开、点击和退回）从Adobe Campaign共享回Microsoft Dynamics 365。

完成配置后，通过专用工作流活动在系统之间执行数据同步。 [了解详情](crm-data-sync.md)。

>[!NOTE]
>
>Campaign [兼容性矩阵](../start/compatibility-matrix.md)中详细介绍了支持的Microsoft Dynamics版本。

请按照以下步骤配置专用外部帐户，以将Microsoft Dynamics 365数据导入和导出到Adobe Campaign。

对于每个系统，这些步骤需要由管理员执行。

>[!CAUTION]
> 本文档中的步骤将指导您创建涉及分配权限和/或管理员访问权限的集成/注册。 在执行之前，您有责任确保这些步骤符合贵公司的政策，并仔细执行这些政策。

## 配置 Microsoft Dynamics 365 {#config-crm-microsoft}

若要通过&#x200B;**Web API**&#x200B;连接Microsoft Dynamics 365以与Adobe Campaign配合使用，请使用&#x200B;**全局管理员**&#x200B;凭据登录到[Microsoft Azure目录](https://portal.azure.com)，然后执行以下步骤：

1. 获取Dynamics 365应用程序（客户端）ID。 [了解详情](#get-client-id-microsoft)
1. 生成Microsoft Dynamics证书密钥标识符和密钥ID。 [了解详情](#config-certificate-key-id)
1. 配置权限。 [了解详情](#config-permissions-microsoft)
1. 创建应用程序用户。 [了解详情](#create-app-user-microsoft)
1. 对私钥进行编码。 [了解详情](#configure-acc-for-microsoftt)


### 获取Dynamics 365客户端标识 {#get-client-id-microsoft}

要获取应用程序（客户端）ID，您需要在Azure Active Directory中注册应用程序。

1. 浏览到&#x200B;**Azure Active Directory >应用程序注册**，然后选择&#x200B;**新注册**。
1. 输入有助于识别实例的唯一名称，如&#x200B;**adobecampaign`<instance identifier>`**。

保存后，Microsoft Azure Directory将为您的应用程序分配唯一的&#x200B;**应用程序（客户端）ID**。 稍后在Adobe Campaign中配置Dynamics 365时，您将需要此ID。

请参阅[Microsoft Dynamics 365文档](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}以了解详情。

### 生成Microsoft Dynamics证书密钥标识符和密钥ID {#config-certificate-key-id}

要获取&#x200B;**证书密钥标识符(customKeyIdentifier)**&#x200B;和&#x200B;**密钥ID (keyId)**，您必须上载证书。 证书可用作密钥，以便在请求令牌时证明应用程序的身份。 也可以称为公钥。

按照下面的步骤进行操作：

1. 浏览到&#x200B;**Azure Active Directory >应用程序注册**，然后选择之前创建的应用程序。
1. 在&#x200B;**证书和密钥**&#x200B;上选择。
1. 在&#x200B;**证书**&#x200B;选项卡中，单击&#x200B;**上载证书**
1. 上载您的公共证书。
1. 浏览到&#x200B;**清单**&#x200B;链接以获取&#x200B;**证书密钥标识符(customKeyIdentifier)**&#x200B;和&#x200B;**密钥ID (keyId)**。

在Campaign中需要&#x200B;**证书密钥标识符(customKeyIdentifier)**&#x200B;和&#x200B;**密钥ID (keyId)**，才能使用证书&#x200B;**[!UICONTROL CRM O-Auth type]**&#x200B;配置您的Microsoft Dynamics 365 CRM外部帐户。

+++ 如何生成公共证书

要生成证书，您可以使用openssl。

例如：

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>您可以更改代码示例中的天数（此处`-days 365`），以获得更长的证书有效期。

然后，您必须在base64中编码证书。 为此，您可以使用Base64编码器帮助或使用适用于Linux的命令行`base64 -w0 private.key`。

+++

### 配置权限 {#config-permissions-microsoft}

**步骤1**：为创建的应用程序配置&#x200B;**所需权限**。

1. 导航到&#x200B;**Azure Active Directory >应用程序注册**，然后选择之前创建的应用程序。
1. 单击左上方的&#x200B;**设置**。
1. 在&#x200B;**所需权限**&#x200B;上，单击&#x200B;**添加**&#x200B;和&#x200B;**选择API > Dynamics CRM Online**。
1. 单击&#x200B;**选择**，启用&#x200B;**以组织用户身份访问Dynamics 365**&#x200B;复选框，然后单击&#x200B;**选择**。
1. 然后，从应用程序的&#x200B;**管理**&#x200B;菜单下选择&#x200B;**清单**。
1. 在&#x200B;**清单**&#x200B;编辑器中，将`allowPublicClient`属性从`null`设置为`true`，然后单击&#x200B;**保存**。

**步骤2**：授予管理员同意

1. 导航到&#x200B;**Azure Active Directory >企业应用程序**。
1. 选择要向其授予租户范围管理员同意的应用程序。
1. 从左窗格菜单中选择&#x200B;**安全性**&#x200B;下的&#x200B;**权限**。
1. 单击&#x200B;**授予管理员同意**。

有关此内容的详细信息，请参阅[Azure文档](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal)。

### 创建应用程序用户 {#create-app-user-microsoft}

>[!NOTE]
>
> 此步骤对于&#x200B;**[!UICONTROL Password credentials]**&#x200B;身份验证是可选的。

应用程序用户是上面注册的应用程序将使用的用户。 使用上面注册的应用程序对Microsoft Dynamics所做的任何更改都将通过此用户完成。

**步骤1**：在azure active directory上创建非交互式用户

1. 单击&#x200B;**Azure Active Directory >用户**，然后单击&#x200B;**新建用户**。
1. 提供您想要使用的正确名称，用户名应为电子邮件格式。
1. 在&#x200B;**目录角色**&#x200B;中选择&#x200B;**Dynamics 365管理员**。

**步骤2**：为创建的用户分配适当的许可证

1. 从[Microsoft Azure](https://portal.azure.com)，单击&#x200B;**管理员应用**。
1. 转到&#x200B;**用户>活动用户**，然后单击新创建的用户。
1. 单击&#x200B;**编辑产品许可证**&#x200B;并选择&#x200B;**Dynamics 365客户参与计划**。
1. 单击&#x200B;**关闭**。

**步骤3**：在Dynamics CRM上创建应用程序用户

1. 从[Microsoft Azure](https://portal.azure.com)，导航到&#x200B;**设置>安全>用户**。
1. 单击下拉列表，选择&#x200B;**应用程序用户**，然后单击&#x200B;**新建**。
1. 使用与上述在Active Directory上创建的用户相同的用户名。
1. 为您之前创建的[应用程序](#get-client-id-microsoft)分配&#x200B;**应用程序ID**。
1. 单击&#x200B;**管理角色**&#x200B;并为用户选择&#x200B;**系统管理员**&#x200B;角色。

## 配置营销活动 {#configure-acc-for-microsoft}

### 创建连接{#new-ms-dyn-external-account}

首先，您必须创建Microsoft Dynamics 365外部帐户。

1. 浏览Campaign资源管理器的&#x200B;**[!UICONTROL Administration > Platform > External accounts]**&#x200B;节点并创建外部帐户。
1. 在&#x200B;**类型**&#x200B;部分中选择&#x200B;**[!UICONTROL Microsoft Dynamics CRM]**&#x200B;外部帐户。
1. 在&#x200B;**[!UICONTROL CRM O-Auth type]**&#x200B;下拉列表中选择身份验证方法。

   ![](assets/ms-dyn-external-account.png)

   1. 要将Microsoft Dynamics CRM外部帐户配置为使用&#x200B;**密码凭据**&#x200B;与Adobe Campaign连接，请提供以下详细信息：

      * **服务器**： Microsoft CRM服务器的URL。 要查找您的Microsoft CRM服务器URL，请访问您的Microsoft Dynamics CRM帐户，然后单击Dynamics 365并选择您的应用程序。 然后，您可以在浏览器的地址栏中找到服务器URL，例如https://myserver.crm.dynamics.com/。
      * **帐户**：用于登录到Microsoft CRM的帐户。
      * **密码**：用于登录Microsoft CRM的帐户。
      * **客户端标识符**：可以在“更新代码”类别的“客户端ID”字段中从Microsoft Azure管理门户找到的应用程序（客户端）ID。
      * **CRM版本**：选择Dynamics CRM 365 CRM版本。

   1. 要将Microsoft Dynamics CRM外部帐户配置为使用&#x200B;**证书**&#x200B;与Adobe Campaign连接，请提供以下详细信息：

      * **服务器**： Microsoft CRM服务器的URL。 要查找您的Microsoft CRM服务器URL，请访问您的Microsoft Dynamics CRM帐户，然后单击Dynamics 365并选择您的应用程序。 然后，您可以在浏览器的地址栏中找到服务器URL，例如https://myserver.crm.dynamics.com/。
      * **私钥**：复制/粘贴私钥，以base64编码，如[此部分](#config-certificate-key-id)中所述。
      * **密钥ID**：在应用程序的&#x200B;**清单**&#x200B;选项卡中可用的密钥，如[此部分](#config-certificate-key-id)中所述。
      * **自定义密钥标识符**：在应用程序的&#x200B;**清单**&#x200B;选项卡中可用的标识符，如[此部分](#config-certificate-key-id)中所述。
      * **客户端标识符**：可以从Microsoft Azure管理门户中找到的应用程序（客户端）ID，如[此部分](#get-client-id-microsoft)中所述。
      * **CRM版本**：选择Dynamics CRM 365 CRM版本。

1. 选择&#x200B;**启用**&#x200B;选项以在Campaign中激活帐户。

>[!NOTE]
>
>要批准设置，请注销并重新登录到Adobe Campaign客户端控制台。

### 选择要同步的表{#ms-dyn-create-tables}

您现在可以配置要同步的表。

1. 单击&#x200B;**[!UICONTROL Microsoft CRM configuration wizard...]**。
1. 选择要同步的表，然后启动进程。
1. 在&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;节点中检查Adobe Campaign中生成的架构。

>[!NOTE]
>
>确保将两个URL添加到允许列表：服务器URL和`login.microsoftonline.com`。 要执行此操作，请联系您的Adobe代表。

## 同步枚举{#sfdc-enum-sync}

创建架构后，您可以自动将枚举从Dynamics 365同步到Adobe Campaign。

1. 从&#x200B;**[!UICONTROL Synchronizing enumerations...]**&#x200B;链接打开助手。
1. 选择与Dynamics 365枚举匹配的Adobe Campaign枚举。
您可以将Adobe Campaign枚举的所有值替换为CRM的值：要实现此目的，请在**[!UICONTROL Replace]**&#x200B;列中选择&#x200B;**[!UICONTROL Yes]**。
1. 单击&#x200B;**[!UICONTROL Next]**，然后单击&#x200B;**[!UICONTROL Start]**&#x200B;以开始导入枚举。
1. 浏览&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;节点以检查导入的值。

Adobe Campaign和Microsoft Dynamics 365现已连接。 您可以设置两个系统之间的数据同步。

要在Adobe Campaign数据和Microsoft CRM之间同步数据，请创建工作流并使用&#x200B;**[!UICONTROL CRM connector]**&#x200B;活动。

在此页面](crm-data-sync.md)中了解有关数据同步[的更多信息。

### 支持的字段数据类型 {#ms-dyn-supported-types}

对于Microsoft Dynamics 365，下面列出了支持/不支持的属性类型：


| 属性类型 | 支持 |
| --------------------------------------------------------------------------------- | --------- |
| 基本类型：boolean、datetime、decimal、float、double、integer、bigint、string | 是 |
| 货币（双精度浮点数） | 是 |
| memo， entityname， primarykey， uniqueidentifier（作为字符串） | 是 |
| 状态、选取列表（我们以枚举形式存储可能的值）、状态（字符串） | 是 |
| 所有者（字符串） | 是 |
| 查找（仅单个实体引用查找） | 是 |
| 客户 | 否 |
| 相关 | 否 |
| PartyList | 否 |
| 托管属性 | 否 |
