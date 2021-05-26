---
solution: Campaign v8
product: Adobe Campaign
title: Campaign API暂存机制
description: Campaign API暂存机制
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 3%

---

# Campaign API暂存机制

使用Campaign Cloud数据库时，由于性能（延迟和并发），不建议使用爆炸式统一调用。 批处理操作始终为首选。 为了确保API的最佳性能，Campaign会保持在本地数据库级别处理API调用。

促销活动暂存机制可用于内置表和自定义表，并具有以下优势：

* 数据架构结构在本地暂存表中进行复制
* 用于摄取的新API会直接流入暂存表中。 [了解详情](new-apis.md)
* 计划工作流每小时触发一次，并将数据同步回云数据库。 [了解详情](../config/replication.md)。

默认情况下，会暂存一些内置架构，例如nmsSubscriptionRcp、nmsAppSubscriptionRcp、nmsRecipient。

Campaign Classicv7 API仍然可用，但无法从此新的暂存机制中受益：API调用会直接流向云数据库。 Adobe建议尽可能使用新的暂存机制，以减少Campaign Cloud数据库的整体压力和延迟。

>[!CAUTION]
>
>使用这种新机制，订阅、取消订阅或移动注册的数据同步现在为&#x200B;**异步**。


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

   [!DNL :bulb:] 在此页面中了解有关创建自定义模式的 [更多信息](create-schema.md)。

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
