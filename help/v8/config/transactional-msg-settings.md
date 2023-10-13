---
title: Campaign事务性消息设置
description: Campaign事务性消息设置
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 5%

---

# 事务性消息设置 {#mc-settings}

事务性消息（消息中心）是用于管理触发消息的Campaign模块。 在中了解有关事务型消息传递的更多信息 [本节](../send/transactional.md).

了解中的事务性消息架构 [此页面](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) 作为托管Cloud Service用户， [联系人Adobe](../start/campaign-faq.md#support) 要在环境中安装和配置Campaign事务型消息传递，请执行以下操作：

## 定义权限 {#mc-permissions}

要为托管在Adobe云上的消息中心执行实例创建新用户，您需要联系Adobe客户关怀部门。 消息中心用户是特定的操作员，需要专用权限才能访问“实时事件”(nmsRtEvent)文件夹。

## 架构扩展  {#mc-schema-ext}

在使用的架构上进行的所有架构扩展 [消息中心技术工作流](#technical-workflows) 需要在Adobe Campaign事务性消息传递模块使用的其他实例上复制控制实例或执行实例。

## 发送事务性推送通知 {#mc-transactional-push}

当与 [移动应用程序渠道模块](../send/push.md)、事务型消息传递允许您通过移动设备上的通知推送事务型消息。

要发送事务型推送通知，您需要执行以下配置：

1. 安装 **移动应用程序渠道** 打包到控制实例和执行实例上。

   >[!CAUTION]
   >
   >在安装新的Campaign内置包之前，请检查您的许可协议。

1. 复制 **移动应用程序** 以及执行实例上关联的移动应用程序。

此外，事件必须包含以下元素：

* 移动设备ID： **registrationId** 适用于Android和 **deviceToken** 用于iOS。 此ID表示发送通知的“地址”。
* 指向移动应用程序或集成键的链接(**uuid**)，可检索特定于应用程序的连接信息。
* 通知将发送到的频道(**希望渠道**)：iOS为41，Android为42。
* 任何其他个性化数据。

以下是发送事务推送通知的事件配置示例：

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## 清除事件 {#purge-events}

您可以调整部署向导设置，以配置数据在数据库中存储的时长。

事件清除由自动执行 **数据库清理** 技术工作流。 此工作流会清除在执行实例上接收并存储的事件，以及在控制实例上存档的事件。

使用适当的箭头来更改清除设置 **活动** （在执行实例上）和 **已存档事件** （在控制实例上）。


## 技术工作流 {#technical-workflows}

您必须确保在部署任何事务性消息模板之前已启动控制实例和执行实例上的技术工作流。

然后，可以从访问这些工作流 **管理>生产>消息中心** 文件夹。

### 控制实例工作流 {#control-instance-workflows}

在控制实例上，必须为每个实例创建一个存档工作流 **[!UICONTROL Message Center execution instance]** 外部帐户。 单击 **[!UICONTROL Create the archiving workflow]** 按钮创建和启动工作流。

### 执行实例工作流 {#execution-instance-workflows}

在执行实例上，必须启动以下技术工作流：

* **[!UICONTROL Processing batch events]** (内部名称： **[!UICONTROL batchEventsProcessing]** )：利用此工作流，可在将队列中的批量事件链接到消息模板之前对其进行划分。
* **[!UICONTROL Processing real time events]** (内部名称： **[!UICONTROL rtEventsProcessing]** )：利用此工作流，可在将队列中的实时事件链接到消息模板之前对其进行划分。
* **[!UICONTROL Update event status]** (内部名称： **[!UICONTROL updateEventStatus]** )：利用此工作流，可将状态归因于事件。

  可能的事件状态为：

   * **[!UICONTROL Pending]**：事件在队列中。 尚未为其分配消息模板。
   * **[!UICONTROL Pending delivery]**：事件处于队列中，已为其分配消息模板且投放正在处理该模板。
   * **[!UICONTROL Sent]**：此状态复制于投放日志。 这意味着投放已发送。
   * **[!UICONTROL Ignored by the delivery]**：此状态复制于投放日志。 这意味着该投放被忽略。
   * **[!UICONTROL Delivery failed]**：此状态复制于投放日志。 这意味着投放失败了。
   * **[!UICONTROL Event not taken into account]**：无法将事件链接到消息模板。 将不会处理该事件。
