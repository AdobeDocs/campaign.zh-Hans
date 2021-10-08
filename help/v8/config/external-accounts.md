---
title: Campaign外部帐户
description: Campaign外部帐户
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 4%

---

# 配置外部帐户

Adobe Campaign 提供了一组预定义的外部帐户。要设置与外部系统的连接，您可以创建新的外部帐户。

技术工作流或营销策划工作流等技术流程，会使用外部帐户。例如，在工作流中设置文件传输或与任何其他应用程序(Adobe Target、Experience Manager等)进行数据交换时，您需要选择外部帐户。

您可以从Adobe Campaign **[!UICONTROL Explorer]**&#x200B;访问外部帐户：浏览至&#x200B;**[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**。

![](assets/external-accounts.png)


>[!CAUTION]
>
>特定的&#x200B;**[!UICONTROL Full FDA]**(ffda)外部帐户管理Campaign本地数据库与云数据库([!DNL Snowflake])之间的连接。
>
>作为托管Cloud Services用户，此外部帐户是按Adobe为您的实例配置的。 不得修改。


## 特定于促销活动的外部帐户

Adobe Campaign使用以下技术帐户来启用和执行特定进程。

??作为托管Cloud Services用户，Adobe会为您配置所有特定于促销活动的外部帐户。

* **退回邮件(POP3)**

   **退回邮件**&#x200B;外部帐户指定用于连接到电子邮件服务的外部POP3帐户。 为POP3访问配置的所有服务器都可用于接收回信。

   ![](../assets/do-not-localize/book.png) 在Campaign Classicv7文档中了解有 [关入站电子邮件的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}

* **路由**

   **[!UICONTROL Routing]**&#x200B;外部帐户允许您根据所安装的包配置Adobe Campaign中可用的每个渠道。

   >[!CAUTION]
   >
   >**[!UICONTROL Internal email delivery routing]**(defaultEmailBulk)外部帐户&#x200B;**不能**&#x200B;在Adobe Campaign v8中启用。

* **执行实例**

   在事务型消息传递的上下文中，执行实例链接到控制实例并连接它们。 事务型消息模板将部署到执行实例。

   ![](../assets/do-not-localize/glass.png) 在本页中了解有关消息中心架构 [的更多信息](../dev/architecture.md#transac-msg-archi)。

## 访问外部系统外部帐户

* **外部数据库（联合数据访问）**

   使用&#x200B;**External database**&#x200B;键入外部帐户以通过FDA连接到外部数据库。

   [兼容性矩阵](../start/compatibility-matrix.md)中列出了与Adobe Campaign v8兼容的外部数据库

   ![](../assets/do-not-localize/glass.png) 在此部分中了解有关联合数据访问(FDA)选项的 [更多信息](../connect/fda.md)。

## Adobe解决方案集成外部帐户

* **Adobe Experience Cloud**

   **[!UICONTROL Adobe Experience Cloud]**&#x200B;外部帐户用于实施Adobe IMS以使用Adobe ID连接到Adobe Campaign控制台。

   ![](../assets/do-not-localize/glass.png) 在此部分中了解有关AdobeIdentity Management服务(IMS)的 [更多信息](../start/connect.md#connect-ims)。

* **网络分析**

   使用&#x200B;**[!UICONTROL Web Analytics (Adobe Analytics)]**&#x200B;外部帐户配置从Adobe Analytics到Adobe Campaign的数据传输。

   ![](../assets/do-not-localize/glass.png) 在此页面中了解有关Adobe Campaign - Adobe Analytics集 [成的更多信息](../connect/ac-aa.md)。

   ??作为受管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support)以将Adobe Analytics与Campaign集成。

   * **Adobe Experience Manager**
   **[!UICONTROL AEM]**&#x200B;外部帐户允许您直接在Adobe Experience Manager中管理电子邮件投放内容和表单。

   ![](../assets/do-not-localize/glass.png) 在此页面中了解有关Adobe Campaign - Adobe Analytics集 [成的更多信息](../connect/ac-aem.md)。

   ??作为受管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support)以将Adobe Experience Manager与Adobe Campaign集成。


## CRM连接器外部帐户

* **Microsoft Dynamics CRM**

   **[!UICONTROL Microsoft Dynamics CRM]**&#x200B;外部帐户允许您将Microsoft Dynamics数据导入和导出到Adobe Campaign。

   ![](../assets/do-not-localize/glass.png) 在此页面中了解有关Adobe Campaign - Microsoft Dynamics CRM集成的 [更多信息](../connect/crm.md)。

   通过&#x200B;**[!UICONTROL Web API]**&#x200B;部署类型和&#x200B;**[!UICONTROL Password credentials]**&#x200B;身份验证，您需要提供以下详细信息：

   * **[!UICONTROL Account]**:用于登录到Microsoft CRM的帐户。

   * **[!UICONTROL Server]**:Microsoft CRM服务器的URL。

   * **[!UICONTROL Client identifier]**:客户端ID，可从Microsoft Azure管理门户的类别字 **[!UICONTROL Update your code]** 段中找 **[!UICONTROL Client ID]** 到。

   * **[!UICONTROL CRM version]**:或之间的CRM **[!UICONTROL Dynamics CRM 2007]**&#x200B;版 **[!UICONTROL Dynamics CRM 2015]** 本 **[!UICONTROL Dynamics CRM 2016]**。
   通过&#x200B;**[!UICONTROL Web API]**&#x200B;部署类型和&#x200B;**[!UICONTROL Certificate]**&#x200B;身份验证，您需要提供以下详细信息：

   * **[!UICONTROL Server]**:Microsoft CRM服务器的URL。

   * **[!UICONTROL Private Key (Base64 encoded)]**:已编码为Base64的私钥

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**:客户端ID，可从Microsoft Azure管理门户的类别字 **[!UICONTROL Update your code]** 段中找 **[!UICONTROL Client ID]** 到。

   * **[!UICONTROL CRM version]**:或之间的CRM **[!UICONTROL Dynamics CRM 2007]**&#x200B;版 **[!UICONTROL Dynamics CRM 2015]** 本 **[!UICONTROL Dynamics CRM 2016]**。


* **Salesforce.com**

   利用&#x200B;**[!UICONTROL Salesforce CRM]**&#x200B;外部帐户，可将Salesforce数据导入和导出到Adobe Campaign。

   要配置Salesforce CRM外部帐户以与Adobe Campaign配合使用，您需要提供以下详细信息：

   * **[!UICONTROL Account]**:用于登录到Salesforce CRM的帐户。

   * **[!UICONTROL Password]**:用于登录到Salesforce CRM的密码。

   * **[!UICONTROL Client identifier]**:在此页面中了解如何查找您的客户 [端标识符](https://help.salesforce.com/articleView?id=000205876&amp;type=1)。

   * **[!UICONTROL Security token]**:在此页面中了解如何查找您的安 [全令牌](https://help.salesforce.com/articleView?id=000205876&amp;type=1)。

   * **[!UICONTROL API version]**:选择API的版本。对于此外部帐户，您需要使用配置向导配置Salesforce CRM。

## 传输数据外部帐户

这些外部帐户可用于使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流活动将数据导入或导出到Adobe Campaign。

![](../assets/do-not-localize/book.png) 在Campaign Classicv7文档中了解有关工作流中 [文件传输的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;}

* **FTP和SFTP**

   通过&#x200B;**FTP**外部帐户，您可以配置和测试对Adobe Campaign以外服务器的访问。 要设置与外部系统（如用于文件传输的SFTP或FTP服务器898）的连接，您可以创建自己的外部帐户。
为此，请在此外部帐户中指定用于建立与SFTP或FTP服务器连接的地址和凭据。

* **Amazon Simple Storage Service(S3)**

   **AWS S3**&#x200B;连接器可用于使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流活动将数据导入或导出到Adobe Campaign。 在设置此新外部帐户时，您需要提供以下详细信息：

   * **[!UICONTROL AWS S3 Account Server]**:服务器的URL，填写如下：    ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**:了解如何在AWS文档中查找Amazon访问 [密钥ID](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) 。

   * **[!UICONTROL Secret access key to AWS]**:在AWS文档中了解如何查找Amazon的秘密访 [问密钥](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/)。

   * **[!UICONTROL AWS Region]**:在AWS文档中了解有关Amazon地区的 [更多信息](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)。

   * **[!UICONTROL Use server side encryption]**&#x200B;复选框允许您以S3加密模式存储文件。 了解如何在[Amazon文档](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys)中查找访问密钥ID和密钥访问密钥。

* **Azure Blob存储**

   **Azure**&#x200B;外部帐户可用于使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;工作流活动将数据导入或导出到Adobe Campaign。 要配置&#x200B;**Azure**&#x200B;外部帐户以与Adobe Campaign配合使用，您需要提供以下详细信息：

   * **[!UICONTROL Server]**:您的Azure Blob存储服务器的URL。

   * **[!UICONTROL Encryption]**:或之间的加密 **[!UICONTROL None]** 类 **[!UICONTROL SSL]**&#x200B;型。

   * **[!UICONTROL Access key]**:了解如何在Microsoft文 **[!UICONTROL Access key]** 档 [中查找](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)。
