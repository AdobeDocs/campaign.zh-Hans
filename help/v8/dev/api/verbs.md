---
title: GET/POST/PATCH/DELETE动词
description: 进一步了解Campaign Standard API中使用的动词。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: de97a194-d497-4665-906e-53178fd3b119
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---

# GET/POST/PATCH/DELETE动词 {#verbs}

对资源执行操作的可用动词包括：

* `GET`：检索一个元素或元素集合
* `POST`：使用参数创建资源。
* `PATCH`：使用参数更新资源。
* `DELETE`：删除资源。

<!-- ajouter codes retour -->

<br/>

***示例请求***

* 配置文件集合中的GET请求示例。


  ```
  $curl  
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  它会返回一个配置文件数组。


  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "firstName": "Olivia",
              "lastName": "Varney",
              "birthDate": "1977-09-°4",
              "email": "o.varney@mail.com",
          },
          {
              "PKey": "<PKEY>",
              "firstName": "John",
              "lastName": "Doe",
              "birthDate": "1985-08-17",
              "email": "johndoe@mail.com",
          }
      ],
  }
  ```

* 特定配置文件上的GET请求示例。


  ```
  $curl  
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  它会返回请求的配置文件。


  ```
  {
      "PKey": "<PKEY>",
      "firstName": "John",
      "lastName": "Doe",
      "birthDate": "1985-08-17",
      "email": "johndoe@mail.com",
      ...
  }
  ```

* 创建用户档案的示例POST请求。


  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -d '{"lastName":"Doe"}'
  ```

  它会返回包含默认字段的配置文件。

  ```
  {
      "PKey": "<PKEY>",
      "firstName": "John",
      "lastName": "Doe",
      "birthDate": "1985-08-17",
      "email": "johndoe@mail.com",
  }
  ```

* 更新用户档案的PATCH请求示例。

  ```
  -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -d '{"firstName":"Mark"',"lastName":"Smith"}'
  ```

  它会返回PKEY和URL以检索更新的配置文件。

  ```
  {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>"
  }
  ```

* 删除配置文件的示例DELETE请求。

  ```
  -X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  该请求会返回200响应，确认用户档案已被删除。
