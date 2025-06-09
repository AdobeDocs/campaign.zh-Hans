---
title: Campaign API暂存机制
description: Campaign API暂存机制
feature: Configuration, API, FFDA
role: Developer
level: Intermediate
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: 9d500f185a9e706b6558135978c4f8c79d92d0d4
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---

# Campaign API暂存机制

在[企业(FFDA)部署](enterprise-deployment.md)的上下文中，不建议在性能（延迟和并发）方面引发单一调用。 除非您发送的数据量极低，否则必须使用批处理操作&#x200B;****。 为了提高性能，引入API将被重定向到本地数据库。

默认情况下，某些内置架构启用了Campaign暂存功能。 我们也可以在任何自定义架构上启用它。 暂存机制简介：

* 数据架构结构复制到本地暂存表中
* 专门用于数据摄取的新API直接流入本地暂存表。 [了解详情](new-apis.md)
* 计划的工作流每小时触发一次，并将数据同步回云数据库。 [了解详情](replication.md)

默认情况下，某些内置模式处于暂存状态，如nmsSubscriptionRcp、nmsAppSubscriptionRcp、nmsRecipient。

Campaign Classic v7 API仍然可用，但无法从这种新的暂存机制中获益： API调用直接流向云数据库。 Adobe建议尽可能使用新的暂存机制，以减少Campaign Cloud数据库的总体压力和延迟。

>[!CAUTION]
>
>* 通过此新机制，渠道选择退出、订阅、取消订阅或移动注册的数据同步现在为&#x200B;**异步**。
>
>* 暂存仅适用于存储在云数据库中的架构。 请勿在复制的架构上启用暂存。 请勿在本地架构上启用暂存。 不要在暂存方案上启用暂存
>

## 实施步骤 {#implement-staging}

要在特定表上实施Campaign暂存机制，请执行以下步骤：

1. 在Campaign Cloud数据库上创建示例自定义架构。 此步骤未启用暂存。

   ```
   <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

   在[此页面](../dev/create-schema.md)中了解有关自定义架构创建的更多信息。

1. 保存并更新数据库结构。  [了解详情](../dev/update-database-structure.md)

1. 通过添加&#x200B;**autoStg=&quot;true&quot;**&#x200B;参数，在架构定义中启用暂存机制。

   ```
   <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

1. 保存修改。 提供了一个新的暂存架构，它是初始架构的本地副本。

   ![](assets/staging-mechanism.png)

1. 更新数据库结构。 将在Campaign本地数据库上创建临时表。
