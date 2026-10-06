---
title: 使用API创建用户档案
description: 了解有关如何使用API创建用户档案的更多信息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
TQID: 'https://experienceleague.adobe.com/ufHL-Vr8NjFpJVES61uhuTl8Xh3DqUsKmwyDkvm7J-g'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%
---
# 使用API创建用户档案 {#creating-profiles-api}

创建配置文件是通过配置文件资源上的&#x200B;**POST**&#x200B;请求执行的。

>[!CAUTION]
>
>如果要将<b>orgUnit</b>关联到已创建的配置文件，则需要使用此字段扩展配置文件资源，并且在发布扩展后，对<b>ProfileAndServicesExt</b>端点执行POST请求。
>
>有关用户档案资源扩展的更多信息，请参阅<a href="https://helpx.adobe.com/cn/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign文档</a>。

<br/>

***示例请求***

使用电子邮件“john.doe@mail.com”创建用户档案的示例POST请求。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它会返回新创建的配置文件，并带有“john.doe@mail.com”电子邮件地址。

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
