---
product: campaign
title: 技术说明 — Adobe Campaign中的非对称加密和解密
description: 技术说明 — Adobe Campaign中的非对称加密和解密
hide: true
hidefromtoc: true
source-git-commit: 1d9d4111cde1e230220a04c8fd10a126116339ad
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# 技术说明：Adobe Campaign中的非对称加密和解密 {#asymetric-encryption}

公钥密码学（或称非对称密码学）是使用相关密钥对的密码系统领域。 每个密钥对都包含&#x200B;**公钥**&#x200B;和相应的&#x200B;**私钥**。

* **公钥**&#x200B;是公开共享的，用于加密数据。

* **私钥**&#x200B;是保密的，用于解密数据。

这种方法确保即使有人拥有公钥，他们也无法解密没有私钥的消息。 它提供关键的安全功能，如机密性、身份验证和完整性。

从Adobe Campaign v8.8.3开始，新增了两个用于加密和解密的Javascript函数：

* 使用公钥加密： `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* 使用私钥解密： `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


示例：

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

**其他资源**

* [开始使用 [!DNL Campaign] API](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [Campaign JSAPI文档](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
