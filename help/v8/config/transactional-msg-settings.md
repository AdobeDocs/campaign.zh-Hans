---
title: Campaign事务型消息传递设置
description: Campaign事务型消息传递设置
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 2d10a8f4349b9e2405847fc6a3db1ed568c60387
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 事务性消息设置

事务型消息传递（消息中心）是一个Campaign模块，用于管理触发的消息。 了解有关事务型消息传递的更多信息，请参阅 [此部分](../send/transactional.md).

了解中的事务型消息传递架构 [本页](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) 作为托管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support) ，以在您的环境中安装和配置Campaign事务型消息传递。

## 定义权限

要为托管在Adobe云上的消息中心执行实例创建新用户，您需要联系Adobe客户关怀团队。 消息中心用户是特定的操作员，需要专用权限才能访问“实时事件”(nmsRtEvent)文件夹。

## 模式扩展

对使用的架构进行的所有架构扩展 [消息中心技术工作流](#technical-workflows) 在上，需要在Adobe Campaign事务型消息传递模块使用的其他实例上复制控制实例或执行实例。

## 发送事务推送通知

与 [移动应用程序渠道模块](../send/push.md)，事务型消息可让您在移动设备上通过通知推送事务型消息。

要发送事务推送通知，您需要执行以下配置：

1. 安装 **移动设备应用程序渠道** 包到控件和执行实例上。

   >[!CAUTION]
   >
   >在安装新的Campaign内置包之前，请检查您的许可协议。

1. 复制 **移动应用程序** 服务和执行实例上关联的移动应用程序。

此外，事件必须包含以下元素：

* 移动设备ID: **registrationId** 适用于Android和 **deviceToken** iOS。 此ID表示通知发送到的“地址”。
* 指向移动应用程序或集成密钥的链接(**uid**)，用于检索特定于应用程序的连接信息。
* 将向其发送通知的渠道(**wishedChannel**):iOS为41，安卓为42。
* 任何其他个性化数据。

以下是用于发送事务推送通知的事件配置示例：

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
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

事件清除由 **数据库清理** 技术工作流。 此工作流会清除在执行实例上接收和存储的事件以及在控制实例上存档的事件。

根据需要使用箭头更改 **事件** （在执行实例上）和 **存档事件** （在控制实例上）。


## 技术工作流 {#technical-workflows}

在部署任何事务型消息模板之前，必须确保已启动控制和执行实例上的技术工作流。

然后，可以从 **管理>生产>消息中心** 文件夹。

### 控制实例工作流 {#control-instance-workflows}

在控制实例上，您必须为每个实例创建一个存档工作流 **[!UICONTROL Message Center execution instance]** 外部帐户。 单击 **[!UICONTROL Create the archiving workflow]** 按钮以创建和启动工作流。

### 执行实例工作流 {#execution-instance-workflows}

在执行实例上，必须启动以下技术工作流：

* **[!UICONTROL Processing batch events]** (内部名称： **[!UICONTROL batchEventsProcessing]** ):利用此工作流，可在将批处理事件链接到消息模板之前，先在队列中对它们进行划分。
* **[!UICONTROL Processing real time events]** (内部名称： **[!UICONTROL rtEventsProcessing]** ):利用此工作流，可在将实时事件链接到消息模板之前，先对队列中的实时事件进行划分。
* **[!UICONTROL Update event status]** (内部名称： **[!UICONTROL updateEventStatus]** ):利用此工作流，可将状态归因到事件。

   可能的事件状态包括：

   * **[!UICONTROL Pending]**:事件在队列中。 尚未为其分配消息模板。
   * **[!UICONTROL Pending delivery]**:事件在队列中，已为其分配消息模板且投放正在处理该模板。
   * **[!UICONTROL Sent]**:此状态复制于投放日志。 这意味着投放已发送。
   * **[!UICONTROL Ignored by the delivery]**:此状态复制于投放日志。 这意味着该投放被忽略。
   * **[!UICONTROL Delivery failed]**:此状态复制于投放日志。 这意味着投放失败了。
   * **[!UICONTROL Event not taken into account]**:该事件无法链接到消息模板。 将不会处理该事件。
