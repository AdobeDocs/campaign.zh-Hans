---
title: Campaign外部帐户
description: Campaign外部帐户
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 4%

---

# 配置外部帐户

Adobe Campaign 提供了一组预定义的外部帐户。要设置与外部系统的连接，您可以创建新的外部帐户。

技术工作流或营销策划工作流等技术流程，会使用外部帐户。例如，在工作流中设置文件传输或与任何其他应用程序(Adobe Target、Experience Manager等)进行数据交换时，您需要选择外部帐户。

您可以从Adobe Campaign访问外部帐户 **[!UICONTROL Explorer]**:浏览 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>特定 **[!UICONTROL Full FDA]** (ffda)外部帐户管理Campaign本地数据库与云数据库([!DNL Snowflake])。
>
>作为托管Cloud Services用户，此外部帐户是按Adobe为您的实例配置的。 不得修改。


## 特定于促销活动的外部帐户

Adobe Campaign使用以下技术帐户来启用和执行特定进程。

![](../assets/do-not-localize/speech.png)  作为托管Cloud Services用户，Adobe会为您配置所有特定于促销活动的外部帐户。

* **退回邮件(POP3)**

   的 **退回邮件** 外部帐户指定用于连接到电子邮件服务的外部POP3帐户。 为POP3访问配置的所有服务器都可用于接收回信。

   ![](../assets/do-not-localize/book.png) 详细了解 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}

* **路由**

   的 **[!UICONTROL Routing]** 外部帐户允许您根据安装的包配置Adobe Campaign中可用的每个渠道。

   >[!CAUTION]
   >
   >的 **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk)外部帐户 **必须** 在Adobe Campaign v8中启用。

* **执行实例**

   在事务型消息传递的上下文中，执行实例链接到控制实例并连接它们。 事务型消息模板将部署到执行实例。

   ![](../assets/do-not-localize/glass.png) 了解有关 [本页](../dev/architecture.md#transac-msg-archi).

## 访问外部系统外部帐户

* **外部数据库（联合数据访问）**

   使用 **外部数据库** 键入外部帐户以通过FDA连接到外部数据库。

   与Adobe Campaign v8兼容的外部数据库列在 [兼容性矩阵](../start/compatibility-matrix.md)

   ![](../assets/do-not-localize/glass.png) 在 [此部分](../connect/fda.md).

## Adobe解决方案集成外部帐户

* **Adobe Experience Cloud**

   的 **[!UICONTROL Adobe Experience Cloud]** 外部帐户用于实施Adobe IMS以使用Adobe ID连接到Adobe Campaign控制台。

   ![](../assets/do-not-localize/glass.png) 在中了解有关AdobeIdentity Management服务(IMS)的更多信息 [此部分](../start/connect.md#connect-ims).

* **网络分析**

   使用 **[!UICONTROL Web Analytics (Adobe Analytics)]** 外部帐户，用于配置从Adobe Analytics到Adobe Campaign的数据传输。

   ![](../assets/do-not-localize/glass.png) 进一步了解Adobe Campaign - Adobe Analytics集成 [本页](../connect/ac-aa.md).

   ![](../assets/do-not-localize/speech.png)  作为托管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support) 将Adobe Analytics与Campaign集成。

   * **Adobe Experience Manager**
   的 **[!UICONTROL AEM]** 外部帐户允许您直接在Adobe Experience Manager中管理电子邮件投放内容和表单。

   ![](../assets/do-not-localize/glass.png) 进一步了解Adobe Campaign - Adobe Analytics集成 [本页](../connect/ac-aem.md).

   ![](../assets/do-not-localize/speech.png)  作为托管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support) 将Adobe Experience Manager与Adobe Campaign集成。


## CRM连接器外部帐户

* **Microsoft Dynamics CRM**

   的 **[!UICONTROL Microsoft Dynamics CRM]** 外部帐户允许您将Microsoft Dynamics数据导入和导出到Adobe Campaign。

   ![](../assets/do-not-localize/glass.png) 进一步了解Adobe Campaign - Microsoft Dynamics CRM集成 [本页](../connect/crm.md).

   使用 **[!UICONTROL Web API]** 部署类型和 **[!UICONTROL Password credentials]** 身份验证时，您需要提供以下详细信息：

   * **[!UICONTROL Account]**:用于登录到Microsoft CRM的帐户。

   * **[!UICONTROL Server]**:Microsoft CRM服务器的URL。

   * **[!UICONTROL Client identifier]**:客户端ID，可从Microsoft Azure管理门户的 **[!UICONTROL Update your code]** 类别， **[!UICONTROL Client ID]** 字段。

   * **[!UICONTROL CRM version]**:之间的CRM版本 **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** 或 **[!UICONTROL Dynamics CRM 2016]**.
   使用 **[!UICONTROL Web API]** 部署类型和 **[!UICONTROL Certificate]** 身份验证时，您需要提供以下详细信息：

   * **[!UICONTROL Server]**:Microsoft CRM服务器的URL。

   * **[!UICONTROL Private Key (Base64 encoded)]**:已编码为Base64的私钥

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**:客户端ID，可从Microsoft Azure管理门户的 **[!UICONTROL Update your code]** 类别， **[!UICONTROL Client ID]** 字段。

   * **[!UICONTROL CRM version]**:之间的CRM版本 **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** 或 **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   的 **[!UICONTROL Salesforce CRM]** 外部帐户允许您将Salesforce数据导入和导出到Adobe Campaign。

   要配置Salesforce CRM外部帐户以与Adobe Campaign配合使用，您需要提供以下详细信息：

   * **[!UICONTROL Account]**:用于登录到Salesforce CRM的帐户。

   * **[!UICONTROL Password]**:用于登录到Salesforce CRM的密码。

   * **[!UICONTROL Client identifier]**:了解如何在 [本页](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Security token]**:了解如何在 [本页](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL API version]**:选择API的版本。 对于此外部帐户，您需要使用配置向导配置Salesforce CRM。

## 传输数据外部帐户

这些外部帐户可用于使用 **[!UICONTROL Transfer file]** 工作流活动。

![](../assets/do-not-localize/book.png) 了解有关 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;}

* **FTP和SFTP**

   的 **FTP** 外部帐户允许您配置和测试对Adobe Campaign以外服务器的访问权限。 要设置与外部系统（如用于文件传输的SFTP或FTP服务器898）的连接，您可以创建自己的外部帐户。
为此，请在此外部帐户中指定用于建立与SFTP或FTP服务器连接的地址和凭据。

* **Amazon Simple Storage Service(S3)**

   的 **AWS S3** 连接器可用于通过 **[!UICONTROL Transfer file]** 工作流活动。 在设置此新外部帐户时，您需要提供以下详细信息：

   * **[!UICONTROL AWS S3 Account Server]**:服务器的URL，填写如下：   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**:了解如何在 [Amazon文档](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Secret access key to AWS]**:了解如何在 [Amazon文档](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL AWS Region]**:详细了解AWS地区 [Amazon文档](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * 的 **[!UICONTROL Use server side encryption]** 复选框允许您以S3加密模式存储文件。 了解如何在 [Amazon文档](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Azure Blob存储**

   的 **Azure** 外部帐户可用于使用 **[!UICONTROL Transfer file]** 工作流活动。 配置 **Azure** 要与Adobe Campaign配合使用的外部帐户，您需要提供以下详细信息：

   * **[!UICONTROL Server]**:您的Azure Blob存储服务器的URL。

   * **[!UICONTROL Encryption]**:之间的加密类型 **[!UICONTROL None]** 或 **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**:了解如何查找 **[!UICONTROL Access key]** in [Microsoft文档](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).
