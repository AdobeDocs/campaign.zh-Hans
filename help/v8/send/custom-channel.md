---
title: 自定义外部渠道入门
description: 了解如何使用Adobe Campaign Web创建和发送自定义外部渠道投放
role: User
level: Beginner, Intermediate
exl-id: d2d92de6-3974-41c5-a0fd-09bbf6cf0020
source-git-commit: f94074d954137c4db39b2ef9f85141b79fe3356b
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# 自定义外部渠道入门 {#gs-custom-channel}

Adobe Campaign允许您创建与第三方集成的自定义外部渠道。 然后，您可以根据这些渠道编排和执行投放。

投放创建和发送可在客户端控制台和Web UI中执行。 但是，自定义外部渠道仅在客户端控制台中执行。

要了解如何基于自定义外部渠道创建和发送投放，请参阅此[页面](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html?lang=zh-Hans)。

以下是在客户端控制台中创建新的外部自定义渠道的步骤：

1. 配置架构，[阅读更多](#configure-schema)
1. 创建新的外部帐户，[了解更多](#create-ext-account)
1. 创建新投放模板，[了解更多](#create-template)

## 配置架构{#configure-schema}

首先，您需要配置架构以将新渠道添加到可用渠道列表。

1. 在Campaign Explorer中，选择&#x200B;**管理** > **配置** > **数据架构**。

1. 创建架构扩展以使用新渠道扩展messageType枚举。

   例如：

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## 创建新的外部帐户{#create-ext-account}

然后，您需要创建新的路由外部帐户。

1. 在Campaign Explorer中，选择&#x200B;**管理** > **平台** > **外部帐户**。

1. 创建新的外部帐户。

1. 选择渠道并将投放模式更改为&#x200B;**外部**。

   ![](assets/cus-ext-account.png){zoomable="yes"}

## 创建新投放模板{#create-template}

现在，让我们创建与新渠道关联的新模板。

1. 在Campaign Explorer中，选择&#x200B;**资源** > **模板** > **投放模板**。

1. 创建新模板。

1. 单击&#x200B;**属性**&#x200B;并选择正确的文件夹和路由。

   ![](assets/cus-template.png){zoomable="yes"}

新渠道现已可用。 您可以基于此渠道创建和执行投放。
