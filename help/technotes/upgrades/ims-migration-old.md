---
title: 将技术用户迁移到Adobe Developer控制台
description: 了解如何将Campaign技术操作员迁移到Adobe Developer控制台上的技术帐户
exl-id: 63008b58-4384-4d2b-864a-57f11d701c01
hide: true
hidefromtoc: true
source-git-commit: 41e39e046ec77de8b5e657ba76645898ff1cd2d7
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 0%

---

# 将Campaign技术操作员迁移到Adobe Developer Console {#migrate-tech-users-to-ims}

从Campaign v8.5开始，改进了Campaign v8的身份验证过程。 技术操作员必须使用[Adobe Identity Management System (IMS)](https://helpx.adobe.com/cn/enterprise/using/identity.html){target="_blank"}连接到Campaign。 技术操作员是为API集成明确创建的Campaign用户配置文件。 本文详细介绍了将技术操作员迁移到Adobe Developer控制台上的技术帐户所需的步骤。

## 更改了哪些内容？{#ims-changes}

Campaign常规用户已使用Adobe ID通过Adobe Identity Management System (IMS)连接到Adobe Campaign控制台。 作为加强安全和身份验证过程的一部分，Adobe Campaign客户端应用程序现在使用IMS技术帐户令牌直接调用Campaign API。

在[Adobe Developer Console文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}中了解有关新服务器到服务器身份验证过程的更多信息。

此更改从Campaign v8.5开始适用，从Campaign v8.6开始将是&#x200B;**强制的**。


## 您是否受影响？{#ims-impacts}

如果您使用的是Campaign API，则需要将技术操作员迁移到Adobe Developer Console，如下所述。

## 如何迁移？{#ims-migration-procedure}

每个技术操作员应至少有一个技术帐户。

关键步骤包括：

1. 首先创建与技术操作员对应的技术帐户。 例如，假设为技术操作员(TO1)新建的技术帐户(TA1)。
1. 执行下面技术帐户TA1上详述的步骤
   [步骤4](#ims-migration-step-4)是可选的，仅当技术操作员具有特定的文件夹权限时才需要此步骤。
1. 将所有Campaign API集成实施迁移到新创建的技术帐户TA1。
1. 一旦所有面向客户的API/集成在TA1上完全正常工作，请用技术帐户TA1替换技术操作员TO1。

### 先决条件{#ims-migration-prerequisites}

在开始迁移过程之前，必须联系Adobe过渡经理，以便Adobe技术团队能够将您现有的操作员组和已命名权限迁移到Adobe Identity Management System (IMS)。

### 步骤1 — 在Adobe Developer Console中创建/更新Campaign项目{#ims-migration-step-1}

集成是作为Adobe Developer Console中&#x200B;**项目**&#x200B;的一部分创建的。 请参阅[Adobe Developer Console文档](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}以了解有关项目的更多信息。

您可以使用之前创建的任何项目，也可以创建新项目。 有关创建项目的详细步骤，请参阅[Adobe Developer Console文档](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}。

对于此迁移，您必须在项目中添加以下API： **I/O管理API**&#x200B;和&#x200B;**Adobe Campaign**。

![](assets/do-not-localize/ims-products-and-services.png)


### 步骤2 — 使用服务器到服务器身份验证将API添加到您的项目中{#ims-migration-step-2}

在Adobe Developer Console中创建项目后，添加一个使用服务器到服务器身份验证的API。 请参阅[Adobe Developer Console文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}以了解如何设置OAuth服务器到服务器凭据。

成功连接API后，您可以访问新生成的凭据（包括客户端ID和客户端密钥），并生成访问令牌。

### 步骤3 — 将产品配置文件添加到项目{#ims-migration-step-3}

您现在可以将Campaign产品用户档案添加到项目中，如下所述：

1. 打开Adobe Campaign API。
1. 单击&#x200B;**编辑产品配置文件**&#x200B;按钮

   ![](assets/do-not-localize/ims-edit-api.png)

1. 将所有相关产品配置文件分配给API（例如“messagecenter”），然后保存更改。
1. 浏览到项目的&#x200B;**凭据详细信息**&#x200B;选项卡，并复制&#x200B;**技术帐户电子邮件**&#x200B;值。

### 步骤4 — 在客户端控制台中更新技术操作员 {#ims-migration-step-4}

仅当已为此操作员（而不是通过操作员的组）定义了特定文件夹权限或命名权限时，才需要执行此步骤。

现在，您需要在Adobe Campaign客户端控制台中更新新创建的技术运算符。 您必须将现有的技术操作员文件夹权限应用到新的技术操作员。
要更新此运算符，请执行以下步骤：

1. 从Campaign Client Console资源管理器中，浏览到&#x200B;**管理>访问管理>运算符**。
1. 访问用于API的现有技术操作员。
1. 浏览到文件夹权限并检查权限。
1. 将相同的权限应用到新创建的技术操作员。 此操作员的电子邮件是以前复制的&#x200B;**技术帐户电子邮件**&#x200B;值。
1. 保存您的更改。


>[!CAUTION]
>
>新的技术操作员必须至少进行了一次要添加到Campaign客户端控制台的API调用。
>

<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Edit the existing technical operator used for APIs.
1. Replace the **Name (login)** of this technical operator by the technical account email retrieved earlier.
1. Browse to the **Edit** button on the top left beside **File**, and select **Edit the XML source**.
1. Update the authentication mode to `ims`, as follows:

    ```javascript
    <operator 
    ...
        <access authenticationType="ims" ...
        ...
        </access>
    ...
    </operator>
    ```

1. Save your changes.

You can also update the technical operator programmatically, using SQL scripts or Campaign APIs. These modes help you automate the steps which update operator's name with associated Technical account email address and/or authentication type. 

* Use the following **SQL Script** to replace operator's name with associated email:

    ```sql
    UPDATE xtkoperator
    SET sauthenticationtype = 'ims',
            sname = '{email}'
    WHERE sname = '{name}' AND itype = 0;
    ```

* Use the following `queryDef.ExecuteQuery` **Campaign API** to fetch id of an operator for given technical operator:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <ExecuteQuery xmlns="urn:xtk:queryDef">
                <sessiontoken>{session_token}</sessiontoken>
                <entity>
                    <queryDef schema="xtk:operator" operation="select">
                        <select>
                            <node expr="@id"/>
                        </select>
                        <where>
                            <condition expr="@name='{name}'"/>
                            <condition expr="@type=0"/>
                        </where>
                    </queryDef>
                </entity>
            </ExecuteQuery>
        </soap:Body>
    </soap:Envelope>
    ```

* Use the following `session.Write` **Campaign API** to update name with given technical account email address:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <Write xmlns="urn:xtk:session">
                <sessiontoken>{session_token}</sessiontoken>
                <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                    <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                        <access authenticationType="ims" />
                    </operator>
                </domDoc>
            </Write>
        </soap:Body>
    </soap:Envelope>
    ```
-->

### 步骤5 — 验证配置 {#ims-migration-step-5}

要尝试连接，请按照[Adobe Developer Console凭据指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"}中详述的步骤生成访问令牌并复制提供的示例cURL命令。


### 步骤6 — 更新第三方API集成 {#ims-migration-step-6}

您必须更新API与第三方系统的集成。

有关API集成步骤的更多详细信息，包括用于顺利集成的示例代码，请参阅[Adobe Developer Console身份验证文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}。


### 步骤7 — 删除旧的技术操作员 {#ims-migration-step-7}


在迁移所有API/自定义代码与技术帐户用户的集成后。 您可以从Campaign客户端控制台中删除旧的技术运算符。

### Soap调用示例{#ims-migration-samples}

完成并验证迁移过程后，Soap调用将更新如下：

* 迁移前：不支持技术帐户访问令牌。

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```

* 迁移后：支持技术帐户访问令牌。 访问令牌应在`Authorization`标头中作为持有者令牌提供。 应在此处忽略会话令牌的使用，如以下soap调用示例中所示。

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  Authorization: Bearer <IMS_Technical_Token_Token>
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken></urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```
