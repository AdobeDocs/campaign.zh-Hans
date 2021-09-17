---
title: Campaign API暂存机制
description: Campaign API暂存机制
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# Campaign API暂存机制

使用Campaign Cloud数据库，不建议对性能（延迟和并发）进行单一的爆破调用。 批量处理操作始终首选。 为了提高性能，摄取API会被重定向到本地数据库。

默认情况下，某些内置架构上启用了营销活动暂存功能。 我们还可以在任何自定义架构上启用它。 一言以蔽之：

* 数据架构结构会复制到本地暂存表中
* 专门用于数据摄取的新API会直接流入本地测试表。 [了解详情](new-apis.md)
* 计划工作流每小时触发一次，并将数据同步回云数据库。 [了解详情](../config/replication.md)

默认情况下，会暂存一些内置架构，例如nmsSubscriptionRcp、nmsAppSubscriptionRcp、nmsRecipient。

Campaign Classicv7 API仍然可用，但无法从此新的暂存机制中受益：API调用会直接流向云数据库。 Adobe建议尽可能使用新的暂存机制，以减少Campaign Cloud数据库的整体压力和延迟。

>[!CAUTION]
>
>* 使用这一新机制，现在&#x200B;**异步**&#x200B;实现了渠道输出、订阅、退订或移动注册的数据同步。
>
>* 暂存仅适用于存储在云数据库上的架构。 请勿在复制的架构上启用暂存。 请勿在本地架构上启用暂存。 不要在暂存架构上启用暂存
>


## 实施步骤{#implement-staging}

要在特定表上实施Campaign暂存机制，请执行以下步骤：

1. 在Campaign Cloud数据库上创建一个示例自定义架构。 此步骤未启用暂存。

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

   ??了解有关在[此页面](create-schema.md)中创建自定义模式的更多信息。

1. 保存并更新数据库结构。  [了解详情](update-database-structure.md)

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

1. 保存修改。 提供了新的暂存架构，该架构是初始架构的本地副本。

   ![](assets/staging-mechanism.png)

1. 更新数据库结构。 将在Campaign本地数据库上创建暂存表。
