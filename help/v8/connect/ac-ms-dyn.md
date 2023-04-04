---
title: 使用 Campaign 和 Microsoft Dynamics
description: 了解如何使用Campaign和Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 3%

---

# 使用Campaign和Microsoft Dynamics 365{#crm-ms-dynamics}

在跨渠道通信中激活CRM数据：了解如何通过 **Microsoft Dynamics 365** ，并将促销活动效果数据（发送、打开、点击和退回）从Adobe Campaign共享回Microsoft Dynamics 365。

完成配置后，系统之间的数据同步将通过专用的工作流活动进行。 [了解详情](crm-data-sync.md)。

>[!NOTE]
>
>Campaign中详细介绍了支持的Microsoft Dynamics版本 [兼容性矩阵](../start/compatibility-matrix.md).

请按照以下步骤配置专用的外部帐户，以将Microsoft Dynamics 365数据导入和导出到Adobe Campaign。

对于每个系统，这些步骤都需由管理员执行。

>[!CAUTION]
> 本文档中的步骤将指导您完成创建涉及分配权限和/或管理员访问权限的集成/注册。 您有责任确保这些步骤在执行之前符合您的公司政策，并认真执行这些步骤。

## 配置 Microsoft Dynamics 365 {#config-crm-microsoft}

要连接Microsoft Dynamics 365以通过与Adobe Campaign配合使用，请执行以下操作 **Web API**，登录到 [Microsoft Azure目录](https://portal.azure.com) 使用 **全局管理员** 凭据，并执行以下步骤：

1. 获取您的Dynamics 365应用程序（客户端）ID。 [了解详情](#get-client-id-microsoft)
1. 生成Microsoft Dynamics证书密钥标识符和密钥ID。 [了解详情](#config-certificate-key-id)
1. 配置权限。 [了解详情](#config-permissions-microsoft)
1. 创建应用程序用户。 [了解详情](#create-app-user-microsoft)
1. 对私钥进行编码。 [了解详情](#configure-acc-for-microsoftt)


### 获取Dynamics 365客户端ID {#get-client-id-microsoft}

要获取应用程序（客户端）ID，您需要在Azure Active Directory中注册应用程序。

1. 浏览到 **Azure Active Directory >应用程序注册**，然后选择 **新注册**.
1. 输入可帮助标识实例的唯一名称，例如 **adobecampaign`<instance identifier>`**.

保存后，Microsoft Azure目录将分配一个唯一 **应用程序（客户端）ID** 到您的应用程序。 您稍后在Adobe Campaign中配置Dynamics 365时将需要此ID。

在 [Microsoft Dynamics 365文档](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}.

### 生成Microsoft Dynamics证书密钥标识符和密钥ID {#config-certificate-key-id}

要获取 **证书密钥标识符(customKeyIdentifier)** 和 **键ID(keyId)**，则必须上传证书。 在请求令牌时，证书可用作密钥来证明应用程序的身份。 也可称为公钥。

按照下面的步骤进行操作：

1. 浏览到 **Azure Active Directory >应用程序注册** 并选择之前创建的应用程序。
1. 选择开启 **证书和密钥**.
1. 从 **证书** ，单击 **上传证书**
1. 上传您的公共证书。
1. 浏览到 **清单** 链接以获取 **证书密钥标识符(customKeyIdentifier)** 和 **键ID(keyId)**.

的 **证书密钥标识符(customKeyIdentifier)** 和 **键ID(keyId)** 需要在Campaign中使用证书配置Microsoft Dynamics 365 CRM外部帐户 **[!UICONTROL CRM O-Auth type]**.

+++ 如何生成公共证书

要生成证书，您可以使用openssl。

例如：

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>您可以在此处更改天数 `-days 365`，在证书有效期较长的代码示例中。

然后，您必须以base64编码证书。 要实现此目的，您可以使用Base64编码器的帮助或使用命令行 `base64 -w0 private.key` 的URL。

+++

### 配置权限 {#config-permissions-microsoft}

**步骤1**:配置 **所需权限** ，用于创建的应用程序。

1. 导航到 **Azure Active Directory >应用程序注册** 并选择之前创建的应用程序。
1. 单击 **设置** 左上角。
1. 开 **所需权限**，单击 **添加** 和 **选择API > Dynamics CRM Online**.
1. 单击 **选择**，启用 **以组织用户身份访问Dynamics 365** 复选框，单击 **选择**.
1. 然后，从您的应用程序中，选择 **清单** 下 **管理** 菜单。
1. 从 **清单** 编辑器中，设置 `allowPublicClient` 属性自 `null` to `true` 单击 **保存**.

**步骤2**:授予管理员同意

1. 导航到 **Azure Active Directory >企业应用程序**.
1. 选择要向其授予租户范围管理员同意的应用程序。
1. 从左窗格菜单中，选择 **权限** 在 **安全性**.
1. 单击 **授予管理员同意**.

有关此内容的详细信息，请参阅 [Azure文档](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### 创建应用程序用户 {#create-app-user-microsoft}

>[!NOTE]
>
> 此步骤是可选的 **[!UICONTROL Password credentials]** 身份验证。

应用程序用户是上述注册的应用程序将使用的用户。 使用上述注册的应用程序对Microsoft Dynamics所做的任何更改都将通过此用户完成。

**步骤1**:在azure active directory上创建非交互式用户

1. 单击 **Azure Active Directory >用户** 单击 **新用户**.
1. 为要使用的名称指定正确的名称，用户名应为电子邮件格式。
1. 选择 **Dynamics 365管理员** 在 **目录角色**.

**步骤2**:为创建的用户分配适当的许可证

1. 从 [Microsoft Azure](https://portal.azure.com)，单击 **管理员应用程序**.
1. 转到 **“用户”>“活动用户”** 并单击新创建的用户。
1. 单击 **编辑产品许可证** ，然后选择 **Dynamics 365客户参与计划**.
1. 单击&#x200B;**关闭**。

**步骤3**:在Dynamics CRM上创建应用程序用户

1. 从 [Microsoft Azure](https://portal.azure.com)，导航到 **设置>安全>用户**.
1. 单击下拉菜单，选择 **应用程序用户**，然后单击 **新建**.
1. 使用与上面在active directory上创建的用户相同的用户名。
1. 分配 **应用程序ID** 表示 [您之前创建的应用程序](#get-client-id-microsoft).
1. 单击 **管理角色** 然后选择 **系统管理员** 角色。

## 配置 Campaign {#configure-acc-for-microsoft}

### 创建连接{#new-ms-dyn-external-account}

首先，必须创建Microsoft Dynamics 365外部帐户。

1. 浏览 **[!UICONTROL Administration > Platform > External accounts]** 节点，并创建外部帐户。
1. 选择 **[!UICONTROL Microsoft Dynamics CRM]** 外部帐户(位于 **类型** 中。
1. 在 **[!UICONTROL CRM O-Auth type]** 下拉列表。

   ![](assets/ms-dyn-external-account.png)

   1. 要配置Microsoft Dynamics CRM外部帐户以与Adobe Campaign连接，请执行以下操作 **密码凭据**，请提供以下详细信息：

      * **服务器**:Microsoft CRM服务器的URL。 要查找Microsoft CRM服务器URL，请访问您的Microsoft Dynamics CRM帐户，然后单击Dynamics 365并选择您的应用程序。 然后，您可以在浏览器的地址栏中找到您的服务器URL，如https://myserver.crm.dynamics.com/。
      * **帐户**:用于登录到Microsoft CRM的帐户。
      * **密码**:用于登录到Microsoft CRM的帐户。
      * **客户端标识符**:应用程序（客户端）ID，可从Microsoft Azure管理门户的更新代码类别“客户端ID”字段中找到。
      * **CRM版本**:选择Dynamics CRM 365 CRM版本。
   1. 要配置Microsoft Dynamics CRM外部帐户以通过 **证书**，请提供以下详细信息：

      * **服务器**:Microsoft CRM服务器的URL。 要查找Microsoft CRM服务器URL，请访问您的Microsoft Dynamics CRM帐户，然后单击Dynamics 365并选择您的应用程序。 然后，您可以在浏览器的地址栏中找到您的服务器URL，如https://myserver.crm.dynamics.com/。
      * **私钥**:复制/粘贴私钥，编码为base64，如 [此部分](#config-certificate-key-id).
      * **密钥ID**:中可用的键 **清单** 的 [此部分](#config-certificate-key-id).
      * **自定义密钥标识符**:中可用的标识符 **清单** 的 [此部分](#config-certificate-key-id).
      * **客户端标识符**:应用程序（客户端）ID，可从Microsoft Azure管理门户中找到，如 [此部分](#get-client-id-microsoft).
      * **CRM版本**:选择Dynamics CRM 365 CRM版本。


1. 选择 **启用** 选项在Campaign中激活帐户。

>[!NOTE]
>
>要批准该设置，请注销，然后重新登录到Adobe Campaign控制台。

### 选择要同步的表{#ms-dyn-create-tables}

您现在可以配置表以进行同步。

1. 单击 **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. 选择要同步并启动进程的表。
1. 检查在Adobe Campaign中生成的架构(位于 **[!UICONTROL Administration > Configuration > Data schemas]** 节点。

>[!NOTE]
>
>确保将添加到允许列表两个URL:服务器URL和 `login.microsoftonline.com`. 要执行此操作，请联系您的Adobe代表。

## 同步枚举{#sfdc-enum-sync}

创建架构后，可以自动将枚举从Dynamics 365同步到Adobe Campaign。

1. 从  **[!UICONTROL Synchronizing enumerations...]** 链接。
1. 选择与Dynamics 365枚举匹配的Adobe Campaign枚举。
您可以将Adobe Campaign枚举的所有值替换为CRM的值：要执行此操作，请选择 **[!UICONTROL Yes]** 在 **[!UICONTROL Replace]** 列。
1. 单击 **[!UICONTROL Next]** 然后 **[!UICONTROL Start]** 开始导入枚举。
1. 浏览 **[!UICONTROL Administration > Platform > Enumerations]** 用于检查导入值的节点。

Adobe Campaign和Microsoft Dynamics 365现已连接。 您可以在两个系统之间设置数据同步。

要在Adobe Campaign数据与Microsoft CRM之间同步数据，请创建工作流并使用 **[!UICONTROL CRM connector]** 活动。

了解有关数据同步的更多信息 [本页](crm-data-sync.md).

### 支持的字段数据类型 {#ms-dyn-supported-types}

对于Microsoft Dynamics 365，以下列出了受支持/不受支持的属性类型：


| 属性类型 | 支持 |
| --------------------------------------------------------------------------------- | --------- |
| 基本类型：布尔，日期时间，小数，浮点，双精度，整数， bigint，字符串 | 是 |
| 货币（双倍） | 是 |
| memo， entityname， primarykey， uniqueidentifier（作为字符串） | 是 |
| 状态、选取列表（我们在枚举中存储可能的值）、状态（字符串） | 是 |
| 所有者（字符串） | 是 |
| 查找（仅单个实体引用查找） | 是 |
| 客户 | 否 |
| 关于 | 否 |
| PartyList | 否 |
| ManagedProperty | 否 |
