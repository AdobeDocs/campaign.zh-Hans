---
title: 使用 Campaign 和 Microsoft Dynamics
description: 了解如何使用Campaign和Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 3%

---

# 使用Campaign和Microsoft Dynamics 365{#crm-ms-dynamics}

在跨渠道通信上激活您的CRM数据：了解如何从传递联系人 **Microsoft Dynamics 365** 到Adobe Campaign，并将促销活动效果数据（发送、打开、点击和退回）从Adobe Campaign共享回Microsoft Dynamics 365。

完成配置后，系统之间的数据同步将通过专用工作流活动执行。 [了解详情](crm-data-sync.md)。

>[!NOTE]
>
>有关支持的Microsoft Dynamics版本的详情，请参阅Campaign [兼容性矩阵](../start/compatibility-matrix.md).

按照以下步骤配置专用外部帐户，以将Microsoft Dynamics 365数据导入和导出到Adobe Campaign。

对于每个系统，这些步骤需要由管理员执行。

>[!CAUTION]
> 本文档中的步骤将指导您创建涉及分配权限和/或管理员访问权限的集成/注册。 在执行之前，您有责任确保这些步骤符合贵公司的政策，并仔细执行这些政策。

## 配置 Microsoft Dynamics 365 {#config-crm-microsoft}

要连接Microsoft Adobe Campaign Dynamics 365以通过 **Web API**，登录到 [Microsoft Azure目录](https://portal.azure.com) 使用 **全局管理员** 凭据，然后执行以下步骤：

1. 获取Dynamics 365应用程序（客户端）ID。 [了解详情](#get-client-id-microsoft)
1. 生成Microsoft Dynamics证书密钥标识符和密钥ID。 [了解详情](#config-certificate-key-id)
1. 配置权限。 [了解详情](#config-permissions-microsoft)
1. 创建应用程序用户。 [了解详情](#create-app-user-microsoft)
1. 编码私钥。 [了解详情](#configure-acc-for-microsoftt)


### 获取Dynamics 365客户端ID {#get-client-id-microsoft}

要获取应用程序（客户端）ID，您需要在Azure Active Directory中注册应用程序。

1. 浏览到 **Azure Active Directory >应用程序注册**，并选择 **新注册**.
1. 输入有助于标识实例的唯一名称，例如 **adobecampaign`<instance identifier>`**.

保存后，Microsoft Azure Directory会分配一个唯一的 **应用程序（客户端）ID** 到您的应用程序。 稍后在Adobe Campaign中配置Dynamics 365时，您将需要此ID。

了解详情，请参阅 [Microsoft Dynamics 365文档](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}.

### 生成Microsoft Dynamics证书密钥标识符和密钥ID {#config-certificate-key-id}

获取 **证书密钥标识符(customKeyIdentifier)** 和 **密钥ID (keyId)**，您必须上传证书。 证书可用作密钥，以便在请求令牌时证明应用程序的身份。 也可以称为公钥。

按照下面的步骤进行操作：

1. 浏览到 **Azure Active Directory >应用程序注册** 并选择之前创建的应用程序。
1. 选择日期 **证书和密码**.
1. 从 **证书** 选项卡，单击 **上传证书**
1. 上传您的公共证书。
1. 浏览至 **清单** 链接以获取 **证书密钥标识符(customKeyIdentifier)** 和 **密钥ID (keyId)**.

此 **证书密钥标识符(customKeyIdentifier)** 和 **密钥ID (keyId)** 需要在Campaign中使用证书配置Microsoft Dynamics 365 CRM外部帐户 **[!UICONTROL CRM O-Auth type]**.

+++ 如何生成公共证书

要生成证书，您可以使用openssl。

例如：

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>您可以在此处更改天数 `-days 365`，在代码示例中获取较长的证书有效期。

然后，您必须在base64中编码证书。 为此，您可以使用Base64编码器帮助或使用命令行 `base64 -w0 private.key` 适用于Linux的。

+++

### 配置权限 {#config-permissions-microsoft}

**步骤1**：配置 **所需权限** （对于创建的应用程序）。

1. 导航到 **Azure Active Directory >应用程序注册** 并选择之前创建的应用程序。
1. 单击 **设置** 左上角。
1. 日期 **所需权限**，单击 **添加** 和 **选择API > Dynamics CRM Online**.
1. 单击 **选择**，启用 **以组织用户身份访问Dynamics 365** 复选框，然后单击 **选择**.
1. 然后，从应用程序中选择 **清单** 在 **管理** 菜单。
1. 从 **清单** 编辑者，设置 `allowPublicClient` 属性自 `null` 到 `true` 并单击 **保存**.

**步骤2**：授予管理员同意

1. 导航到 **Azure Active Directory >企业应用程序**.
1. 选择要向其授予租户范围管理员同意的应用程序。
1. 从左窗格菜单中，选择 **权限** 下 **安全性**.
1. 单击 **授予管理员同意**.

欲知更多信息，请参见 [Azure文档](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### 创建应用程序用户 {#create-app-user-microsoft}

>[!NOTE]
>
> 此步骤是可选的，用于 **[!UICONTROL Password credentials]** 身份验证。

应用程序用户是上面注册的应用程序将使用的用户。 使用上面注册的应用程序对Microsoft Dynamics所做的任何更改都将通过此用户完成。

**步骤1**：在azure active directory上创建非交互式用户

1. 单击 **Azure Active Directory >用户** 并单击 **新用户**.
1. 提供您想要使用的正确名称，用户名应为电子邮件格式。
1. 选择 **Dynamics 365管理员** 在 **目录角色**.

**步骤2**：为创建的用户分配适当的许可证

1. 起始日期 [Microsoft Azure](https://portal.azure.com)，单击 **管理应用程序**.
1. 转到 **“用户”>“活动用户”** ，然后单击新创建的用户。
1. 单击 **编辑产品许可证** 并选择 **Dynamics 365客户参与计划**.
1. 单击&#x200B;**关闭**。

**步骤3**：在Dynamics CRM上创建应用程序用户

1. 起始日期 [Microsoft Azure](https://portal.azure.com)，导航到 **“设置”>“安全”>“用户”**.
1. 单击下拉列表，选择 **应用程序用户**，然后单击 **新**.
1. 使用与上述在Active Directory上创建的用户相同的用户名。
1. 分配 **应用程序ID** 对象 [您之前创建的应用程序](#get-client-id-microsoft).
1. 单击 **管理角色** 并选择 **系统管理员** 角色到用户。

## 配置 Campaign {#configure-acc-for-microsoft}

### 创建连接{#new-ms-dyn-external-account}

首先，必须创建Microsoft Dynamics 365外部帐户。

1. 浏览 **[!UICONTROL Administration > Platform > External accounts]** 节点，并创建外部帐户。
1. 选择 **[!UICONTROL Microsoft Dynamics CRM]** 中的外部帐户 **类型** 部分。
1. 选择中的身份验证方法 **[!UICONTROL CRM O-Auth type]** 下拉列表。

   ![](assets/ms-dyn-external-account.png)

   1. 要配置Microsoft Dynamics CRM外部帐户以与Adobe Campaign连接，请执行以下操作 **密码凭据**，提供以下详细信息：

      * **服务器**：Microsoft CRM服务器的URL。 要查找您的Microsoft CRM服务器URL，请访问您的Microsoft Dynamics CRM帐户，然后单击Dynamics 365并选择您的应用程序。 然后，您可以在浏览器的地址栏中找到服务器URL，例如https://myserver.crm.dynamics.com/。
      * **帐户**：用于登录到Microsoft CRM的帐户。
      * **密码**：用于登录到Microsoft CRM的帐户。
      * **客户端标识符**：可以在Microsoft Azure管理门户的更新代码类别客户端ID字段中找到应用程序（客户端）ID。
      * **CRM版本**：选择Dynamics CRM 365 CRM版本。
   1. 要将Microsoft Adobe Campaign Dynamics CRM外部帐户配置为使用 **证书**，提供以下详细信息：

      * **服务器**：Microsoft CRM服务器的URL。 要查找您的Microsoft CRM服务器URL，请访问您的Microsoft Dynamics CRM帐户，然后单击Dynamics 365并选择您的应用程序。 然后，您可以在浏览器的地址栏中找到服务器URL，例如https://myserver.crm.dynamics.com/。
      * **私钥**：复制/粘贴私钥（编码为base64），如 [本节](#config-certificate-key-id).
      * **密钥ID**：中可用的键 **清单** 选项卡，如中所述 [本节](#config-certificate-key-id).
      * **自定义密钥标识符**：中可用的标识符 **清单** 选项卡，如中所述 [本节](#config-certificate-key-id).
      * **客户端标识符**：可以从Microsoft Azure管理门户中找到的应用程序（客户端）ID，如中所述 [本节](#get-client-id-microsoft).
      * **CRM版本**：选择Dynamics CRM 365 CRM版本。


1. 选择 **启用** 用于在Campaign中激活帐户的选项。

>[!NOTE]
>
>要批准设置，请注销并重新登录到Adobe Campaign客户端控制台。

### 选择要同步的表{#ms-dyn-create-tables}

您现在可以配置要同步的表。

1. 单击 **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. 选择要同步的表，然后启动进程。
1. 在中检查Adobe Campaign中生成的架构 **[!UICONTROL Administration > Configuration > Data schemas]** 节点。

>[!NOTE]
>
>确保将两个URL添加到允许列表：服务器URL和 `login.microsoftonline.com`. 要执行此操作，请联系您的Adobe代表。

## 同步枚举{#sfdc-enum-sync}

创建架构后，您可以自动将枚举从Dynamics 365同步到Adobe Campaign。

1. 从以下位置打开助手  **[!UICONTROL Synchronizing enumerations...]** 链接。
1. 选择与Dynamics 365枚举匹配的Adobe Campaign枚举。
您可以将Adobe Campaign枚举的所有值替换为CRM的值：要实现此目的，请选择 **[!UICONTROL Yes]** 在 **[!UICONTROL Replace]** 列。
1. 单击 **[!UICONTROL Next]** 然后 **[!UICONTROL Start]** 以开始导入明细列表。
1. 浏览 **[!UICONTROL Administration > Platform > Enumerations]** 节点以检查导入的值。

Adobe Campaign和Microsoft Dynamics 365现已连接。 您可以设置两个系统之间的数据同步。

要在Adobe Campaign数据和Microsoft CRM之间同步数据，请创建工作流并使用 **[!UICONTROL CRM connector]** 活动。

了解有关数据同步的更多信息 [本页内容](crm-data-sync.md).

### 支持的字段数据类型 {#ms-dyn-supported-types}

对于Microsoft Dynamics 365，下面列出了支持/不支持的属性类型：


| 属性类型 | 支持 |
| --------------------------------------------------------------------------------- | --------- |
| 基本类型：boolean、datetime、decimal、float、double、integer、bigint、string | 是 |
| 货币（双倍） | 是 |
| memo、entityname、primarykey、uniqueidentifier（作为字符串） | 是 |
| 状态、选择列表（我们会将可能的值存储在枚举中）、状态（字符串） | 是 |
| 所有者（字符串） | 是 |
| 查找（仅单个实体引用查找） | 是 |
| 客户 | 否 |
| 相关 | 否 |
| PartyList | 否 |
| 托管属性 | 否 |
