---
title: 筛选营销活动架构
description: 了解如何筛选Campaign模式
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---

# 筛选模式{#filter-schemas}

## 系统筛选器 {#system-filters}

您可以筛选对特定用户的架构访问权限，具体取决于其权限。 系统筛选器允许您使用&#x200B;**readAccess**&#x200B;和&#x200B;**writeAccess**&#x200B;参数管理架构中详细描述的实体的读取和写入权限。

>[!NOTE]
>
>此限制仅适用于非技术用户：具有相关权限或使用工作流的技术用户将能够检索和更新数据。

* **readAccess**：提供对架构数据的只读访问权限。

  **警告** — 必须对所有链接表设置相同的限制。 此配置可能会影响性能。

* **writeAccess**：提供对架构数据的写入权限。

这些筛选器是在架构的主&#x200B;**元素**&#x200B;级别输入的，如以下示例所示，可以形成以限制访问。

* 限制写入权限

  此处，过滤器用于禁止没有“管理”权限的操作员在架构上具有“写入”权限。 这意味着只有管理员对此架构描述的实体具有写入权限。

  ```
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* 限制读取和写入权限：

  此处，该过滤器用于禁止所有操作员在架构上同时具有“读取”和“写入”权限。 仅限由表达式“$(loginId)”表示的&#x200B;**internal**&#x200B;帐户！=0”，具有这些权限。

  ```
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  用于定义条件的可用&#x200B;**expr**&#x200B;属性值是TRUE或FALSE。

>[!NOTE]
>
>如果未指定筛选器，则所有操作员都将具有架构的读写权限。

## Protect内置架构

默认情况下，只有具有ADMINISTRATION权限的操作员才可以通过WRITE权限访问内置架构：

* ncm：publishing
* nl：monitoring
* nms：calendar
* xtk：builder
* xtk：连接
* xtk：dbInit
* xtk：entityBackupNew
* xtk：entityBackupOriginal
* xtk：entityOriginal
* xtk：form
* xtk：funcList
* xtk：fusion
* xtk：image
* xtk：javascript
* xtk：jssp
* xtk：jst
* xtk：navtree
* xtk：operatorGroup
* xtk：package
* xtk：queryDef
* xtk：resourceMenu
* xtk：rights
* xtk：schema
* xtk：scriptContext
* xtk：specFile
* xtk：sql
* xtk：sqlSchema
* xtk：srcSchema
* xtk：字符串
* xtk：xslt

>[!CAUTION]
>
>**xtk：sessionInfo**&#x200B;架构的读取和写入权限只能由Adobe Campaign实例的内部帐户访问。

## 修改内置模式的系统筛选器

内置模式受到保护，以避免与旧版本出现兼容性问题。 Adobe建议您不要修改默认架构参数以确保最佳安全性。

但是，在特定上下文中，您可能需要修改内置模式的系统筛选器。 要执行此操作，请按照以下步骤进行：

1. 为内置模式创建扩展或打开现有扩展。
1. 在主元素中添加子元素&#x200B;**`<sysfilter name="<filter name>" _operation="delete"/>`**&#x200B;以忽略内置架构中相同项下的筛选器。
1. 您可以添加新筛选器，如[系统筛选器](#system-filters)部分所述。
