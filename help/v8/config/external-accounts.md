---
title: Campaign外部帐户
description: Campaign外部帐户
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 4%

---


# 配置外部帐户 {#config-external-accounts}

Adobe Campaign 提供了一组预定义的外部帐户。要设置与外部系统的连接，您可以创建新的外部帐户。

技术工作流或营销策划工作流等技术流程，会使用外部帐户。例如，在工作流中设置文件传输或与任何其他应用程序(Adobe Target、Experience Manager等)进行数据交换时，您需要选择外部帐户。

您可以从Adobe Campaign **[!UICONTROL Explorer]**&#x200B;访问外部帐户：浏览到&#x200B;**[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**。

![](assets/external-accounts.png)


>[!CAUTION]
>
>* 作为托管Cloud Service用户，外部帐户是按Adobe为您的实例配置的，不得修改。
>
>* 在[企业(FFDA)部署](../architecture/enterprise-deployment.md)的上下文中，特定的&#x200B;**[!UICONTROL Full FDA]** (ffda)外部帐户管理Campaign本地数据库和云数据库([!DNL Snowflake])之间的连接。
>

## Campaign特定的外部帐户 {#ac-external-accounts}

Adobe Campaign使用以下技术帐户来启用和执行特定流程。

### 退回邮件 {#bounce-mails-external-account}

>[!NOTE]
>
>从Campaign v8.3开始，提供了适用于POP3功能的Microsoft Exchange Online OAuth 2.0身份验证。要检查您的版本，请参阅[此部分](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)。
>

**退回邮件**&#x200B;外部帐户指定要用于连接到电子邮件服务的外部POP3帐户。 所有配置为POP3访问的服务器都可以接收回邮。

在[此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html){target="_blank"}中了解有关入站电子邮件的更多信息。

![](assets/bounce_external_1.png)

要配置&#x200B;**[!UICONTROL Bounce mails (defaultPopAccount)]**&#x200B;外部帐户：

* **[!UICONTROL Server]** - POP3服务器的URL。

* **[!UICONTROL Port]** - POP3连接端口号。 默认端口为110。

* **[!UICONTROL Account]** — 用户的名称。

* **[!UICONTROL Password]** — 用户帐户密码。

* **[!UICONTROL Encryption]** - **[!UICONTROL By default]**、**[!UICONTROL POP3 + STARTTLS]**、**[!UICONTROL POP3]**&#x200B;或&#x200B;**[!UICONTROL POP3S]**&#x200B;之间选择的加密类型。

  **退回邮件**&#x200B;外部帐户指定要用于连接到电子邮件服务的外部POP3帐户。 所有配置为POP3访问的服务器都可以接收回邮。

* **[!UICONTROL Function]** — 入站电子邮件或SOAP路由器

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>在使用Microsoft OAuth 2.0配置POP3外部帐户之前，您首先需要在Azure门户中注册应用程序。 有关详细信息，请参阅此[页面](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}。
>

要使用Microsoft OAuth 2.0配置POP3外部连接，请选中&#x200B;**[!UICONTROL Microsoft OAuth 2.0]**&#x200B;选项并填写以下字段：

* **[!UICONTROL Azure tenant]** - Azure ID(或目录（租户）ID)可以在Azure门户的应用程序概述的&#x200B;**Essentials**&#x200B;下拉菜单中找到。

* **[!UICONTROL Azure Client ID]** — 可以在Azure门户中应用程序概述的&#x200B;**Essentials**&#x200B;下拉列表中找到客户端ID(或应用程序（客户端）ID)。

* **[!UICONTROL Azure Client secret]** — 可以在Azure门户中应用程序的&#x200B;**证书和密码**&#x200B;菜单的&#x200B;**客户端密码**&#x200B;列中找到客户端密码ID。

* **[!UICONTROL Azure Redirect URL]** — 可在Azure门户中应用程序的&#x200B;**身份验证**&#x200B;菜单中找到重定向URL。 它应使用以下语法`nl/jsp/oauth.jsp`结束，如`https://redirect.adobe.net/nl/jsp/oauth.jsp`。

  输入其他凭据后，可单击&#x200B;**[!UICONTROL Setup the connection]**&#x200B;以完成外部帐户配置。

### 路由 {#routing}

**[!UICONTROL Routing]**&#x200B;外部帐户允许您根据安装的包配置Adobe Campaign中可用的每个渠道。

### 执行实例 {#execution-instance}

在事务型消息的上下文中，执行实例将链接到控制实例并将它们连接起来。 将事务性消息模板部署到执行实例。 在[此页面](../architecture/architecture.md#transac-msg-archi)中了解有关消息中心架构的更多信息。

## 访问外部系统外部帐户 {#external-syst-external-accounts}

* **外部数据库(FDA)** - **外部数据库**&#x200B;类型的外部帐户用于通过联合数据访问(FDA)连接到外部数据库。 在[本节](../connect/fda.md)中了解联合数据访问(FDA)选项的更多信息。

  与Adobe Campaign v8兼容的外部数据库在[兼容性矩阵](../start/compatibility-matrix.md)中列出

* **X (以前称为Twitter)** - **Twitter**&#x200B;类型的外部帐户用于将Campaign连接到您的X帐户，以代表您发布消息。 在[本节](../connect/ac-tw.md)中了解有关X集成的更多信息。

## Adobe解决方案集成外部帐户 {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - **[!UICONTROL Adobe Experience Cloud]**&#x200B;外部帐户用于实施AdobeIdentity Management服务(IMS)以连接到Adobe Campaign。 在[此部分](../start/connect.md#logon-to-ac)中了解有关AdobeIdentity Management服务(IMS)的更多信息。

* **网站分析** - **[!UICONTROL Web Analytics (Adobe Analytics)]**&#x200B;外部帐户用于配置从Adobe Analytics到Adobe Campaign的数据传输。 在[此页面](../connect/ac-aa.md)中了解有关Adobe Campaign - Adobe Analytics集成的更多信息。

* **Adobe Experience Manager** - **[!UICONTROL AEM]**&#x200B;外部帐户允许您直接在Adobe Experience Manager中管理电子邮件投放的内容以及表单。 在[此页面](../connect/ac-aem.md)中了解有关Adobe Campaign - Adobe Analytics集成的更多信息。


## CRM连接器外部帐户 {#crm-external-accounts}

* **Microsoft Dynamics CRM** - **[!UICONTROL Microsoft Dynamics CRM]**&#x200B;外部帐户允许您将Microsoft Dynamics数据导入和导出到Adobe Campaign。 在[本页](../connect/ac-ms-dyn.md)中了解有关Adobe Campaign - Microsoft Dynamics CRM集成的更多信息。

* **Salesforce.com** - **[!UICONTROL Salesforce CRM]**&#x200B;外部帐户允许您将Salesforce数据导入和导出到Adobe Campaign。 在[此页面](../connect/ac-sfdc.md)中了解有关Adobe Campaign - Salesforce.com CRM集成的更多信息。

## 传输数据外部帐户 {#transfer-data-external-accounts}

这些外部帐户可用于通过&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流活动将数据导入或导出到Adobe Campaign。 在[此页面](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html){target="_blank"}中了解有关工作流中&#x200B;**文件传输**&#x200B;的更多信息。

* **FTP和SFTP** - **FTP**&#x200B;外部帐户允许您配置和测试对Adobe Campaign外部服务器的访问。 要与外部系统（如用于文件传输的SFTP或FTP服务器898）建立连接，您可以创建自己的外部帐户。

  为此，请在此外部帐户中指定用于建立与SFTP或FTP服务器连接的地址和凭据。

  >[!NOTE]
  >
  >从版本8.5开始，您现在可以在配置SFTP外部帐户时使用私钥安全进行身份验证。 [了解有关密钥管理的更多信息](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html){target="_blank"}。

* **Amazon Simple Storage Service (S3)** - **AWS S3**&#x200B;连接器可用于通过&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流活动将数据导入或导出到Adobe Campaign。 在设置此新外部帐户时，您需要提供以下详细信息：

   * **[!UICONTROL AWS S3 Account Server]**：服务器的URL，填充如下：   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**：请参阅[AWS文档](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}以了解如何查找您的Amazon访问密钥ID。

   * **[!UICONTROL Secret access key to AWS]**：请参阅[AWS文档](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}以了解如何查找您的Amazon访问密钥。

   * **[!UICONTROL AWS Region]**：在[AWS文档](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}中了解有关Amazon地区的更多信息。

   * **[!UICONTROL Use server side encryption]**&#x200B;复选框允许您以S3加密模式存储文件。 请参阅[Amazon文档](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}以了解如何查找访问密钥ID和访问密钥。

* **Azure Blob Storage** - **Azure**&#x200B;外部帐户可用于通过&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流活动将数据导入或导出到Adobe Campaign。 要将&#x200B;**Azure**&#x200B;外部帐户配置为与Adobe Campaign配合使用，您需要提供以下详细信息：

   * **[!UICONTROL Server]**： Azure Blob存储服务器的URL。

   * **[!UICONTROL Encryption]**： **[!UICONTROL None]**&#x200B;或&#x200B;**[!UICONTROL SSL]**&#x200B;之间的加密类型。

   * **[!UICONTROL Access key]**：请参阅[Microsoft文档](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}以了解如何查找您的&#x200B;**[!UICONTROL Access key]**。
