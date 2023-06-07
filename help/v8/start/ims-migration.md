---
title: 在开发人员控制台上将技术用户迁移到技术帐户
description: 在开发人员控制台上将技术用户迁移到技术帐户
hide: true
hidefromtoc: true
source-git-commit: 1f9efc0744792c1173e77965ff81eaee0ed2c618
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---

# 将Campaign技术操作员迁移到Adobe Developer控制台 {#migrate-tech-users-to-ims}

从Campaign v8.5开始，改进了Campaign v8的身份验证过程。 技术操作员必须使用 [AdobeIdentity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} 以连接到Campaign。 技术操作员是为API集成明确创建的Campaign用户配置文件。 本文详细介绍了将技术操作员迁移到Adobe Developer控制台上的技术帐户所需的步骤。

## 更改了哪些内容？{#ims-changes}

Campaign常规用户已通过AdobeIdentity Management System (IMS)，使用他们的Adobe ID连接到Adobe Campaign控制台。 作为加强安全和身份验证流程工作的一部分，Adobe Campaign客户端应用程序现在使用IMS技术帐户令牌直接调用Campaign API。

了解中关于新服务器到服务器身份验证过程的更多信息 [Adobe Developer控制台文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

此更改适用于Campaign v8.5，并且将 **必需** 从Campaign v8.6开始。


## 您是否受影响？{#ims-impacts}

如果您使用的是Campaign API，则需要将技术操作员迁移到Adobe Developer控制台，如下所述。

## 如何迁移？{#ims-migration-procedure}

### 先决条件{#ims-migration-prerequisites}

在开始迁移过程之前，您必须联系Adobe代表，以便Adobe技术团队能够将您现有的操作员组和已命名权限迁移到AdobeIdentity Management System (IMS)。

### 步骤1 — 在Adobe Developer控制台中创建/更新Campaign项目{#ims-migration-step-1}

集成是作为的一部分创建的 **项目** 在Adobe Developer控制台中。 了解有关中项目的更多信息 [Adobe Developer控制台文档](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

作为Campaign v8用户，您应已在Adobe Developer Console中拥有项目。 如果不能，则必须创建一个项目。 详细说明创建项目的步骤 [在Adobe Developer Console文档中](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

在访问Campaign项目后，您可以添加包括API、Adobe Campaign和I/O管理API在内的服务。 对于此迁移，您必须在项目中添加以下API： **I/O管理API** 和 **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### 步骤2 — 使用服务器到服务器身份验证将API添加到您的项目中{#ims-migration-step-2}

在Adobe Developer控制台中创建项目后，添加一个使用服务器到服务器身份验证的API。 了解如何在中设置OAuth服务器到服务器凭据 [Adobe Developer控制台文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

成功连接API后，您可以访问新生成的凭据（包括客户端ID和客户端密钥），并生成访问令牌。

### 步骤3 — 将产品配置文件添加到项目{#ims-migration-step-3}

您现在可以将Campaign产品用户档案添加到项目中，如下所述：

1. 打开Adobe Campaign API。
1. 单击 **编辑产品配置文件** 按钮

   ![](assets/do-not-localize/ims-edit-api.png)

1. 将所有相关产品配置文件分配给API（例如“messagecenter”），然后保存更改。
1. 浏览至 **凭据详细信息** 选项卡，并复制 **技术帐户电子邮件** 值。

### 步骤4 — 在客户端控制台中更新技术操作员 {#ims-migration-step-4}

最后一步是更新Adobe Campaign客户端控制台中的技术操作员。

>[!CAUTION]
>
>更新技术操作员的身份验证类型后，与此技术操作员的所有API集成都将停止工作。 您必须 [更新API集成](#ims-migration-step-6).

要将技术操作员身份验证模式更新为IMS，请执行以下步骤：

1. 在Campaign客户端控制台资源管理器中，浏览到 **管理>访问管理>运算符**.
1. 编辑用于API的现有技术操作员。
1. 更换 **名称（登录）** 之前检索到的技术帐户电子邮件发送给该技术操作员的电子邮件。
1. 浏览至 **编辑** 按钮位于旁边的左上方 **文件**，并选择 **编辑XML源**.
1. 将身份验证模式更新为 `ims`，如下所示：

   ```javascript
   <operator 
   ...
       <access authenticationType="ims" ...
       ...
       </access>
   ...
   </operator>
   ```

1. 保存您的更改。

您还可以使用SQL脚本或Campaign API，以编程方式更新技术运算符。 这些模式可帮助您自动执行将操作员的姓名更新为关联的技术帐户电子邮件地址和/或身份验证类型的步骤。

* 使用以下内容 **SQL脚本** 要将操作员姓名替换为相关电子邮件，请执行以下操作：

   ```sql
   UPDATE xtkoperator
   SET sauthenticationtype = 'ims',
           sname = '{email}'
   WHERE sname = '{name}' AND itype = 0;
   ```

* 使用以下内容 `queryDef.ExecuteQuery` **Campaign API** 要为给定的技术操作员获取操作员的id：

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

* 使用以下内容 `session.Write` **Campaign API** 要使用给定的技术帐户电子邮件地址更新名称，请执行以下操作：

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

### 步骤5 — 验证配置 {#ims-migration-step-5}

要尝试连接，请按照 [Adobe Developer Console凭据指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} ，以生成访问令牌并复制提供的示例cURL命令。


### 步骤6 — 更新第三方API集成 {#ims-migration-step-6}

您必须更新API与第三方系统的集成。

有关API集成步骤的更多详细信息（包括顺利集成的示例代码），请参阅 [Adobe Developer Console身份验证文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Soap调用示例{#ims-migration-samples}

完成并验证迁移过程后，Soap调用将更新如下：

* 迁移前

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

* 迁移后

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
