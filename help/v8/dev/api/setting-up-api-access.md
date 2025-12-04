---
title: 设置API访问
description: 了解如何设置对Campaign Standard API的访问权限。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 6%

---

# 设置 API 访问 {#setting-up-api-access}

Adobe Campaign Standard API访问可通过以下步骤进行设置。 [Adobe Developer文档](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中详细介绍了这些步骤。

>[!IMPORTANT]
>
>要在[Adobe Developer](https://developer.adobe.com/)中管理证书，请确保您对该组织具有&#x200B;**系统管理员**&#x200B;权限，或者在Admin Console中具有[开发人员帐户](https://helpx.adobe.com/cn/enterprise/using/manage-developers.html)。

1. **检查您是否拥有数字证书**，或者在必要时创建一个数字证书。 以下步骤需要随证书一起提供的公钥和私钥。
1. **在** Adobe Developer[中创建与Adobe Campaign服务](https://developer.adobe.com/)的新集成并进行配置。 随后将生成您的凭据（API密钥、客户端密钥……）。
1. **按照以下**&#x200B;实施步骤创建OAuth服务器到服务器[凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)

   >[!IMPORTANT]
   >
   >JWT（JSON Web 令牌）目前正在被逐步停用，它将被 OAuth 取代。此过渡将在Campaign即将发布的版本中逐步执行。 服务帐户(JWT)凭据已标记为已弃用，在2025年1月27日之前将继续工作。 因此，您必须在2025年1月27日之前迁移应用程序或集成，才能使用新的OAuth服务器到服务器凭据。 首选OAuth身份验证。 您将在以下页面上找到要从JWT身份验证迁移到OAuth身份验证的所有元素：
   >* [迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [实施](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [弃用JWT常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

要建立安全的服务到服务Adobe I/O API会话，对Adobe服务的每个请求都必须在Authorization标头中包含以下信息。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;组织>**：这是您的个人组织ID，Adobe会为您每个实例提供一个组织ID：

   * &lt;ORGANIZATION> ：您的生产实例，
   * &lt;ORGANIZATION-mkt-stage>：您的阶段实例。

  要获取您的组织ID值，请联系管理员或Adobe技术联系人。 您还可以在创建新集成时，在许可证列表中将其检索到Adobe I/O(请参阅<a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer文档</a>)。

* **&lt;ACCESS_TOKEN>**：通过POST请求交换您的JSON Web令牌时检索到了您的个人访问令牌。

* **&lt;API_KEY>**：您的个人API密钥。 在创建了与Adobe I/O服务的新集成后，Adobe Campaign中会提供此服务。

  ![替换文本](assets/tenant.png)

## 故障排除

在AdobeIO集成期间，如果出现以下错误：

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


请咨询您的管理员或Adobe技术联系人，以检查CNAME参数是否正确创建。
