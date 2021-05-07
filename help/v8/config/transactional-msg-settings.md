---
solution: Campaign
product: Adobe Campaign
title: 活动事务消息设置
description: 活动事务消息设置
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# 交易消息设置

:speech_balloon:作为“托管Cloud Services”用户，[联系Adobe](../start/support.md#support)以在您的环境中安装和配置活动事务消息。

：灯泡：[本节](../send/transactional.md)中详细介绍了事务消息功能。

：灯泡：了解[本页](../dev/architecture.md)中的事务消息架构。

## 定义权限

要为托管在Adobe Cloud上的消息中心执行实例创建新用户，您需要联系Adobe客户关怀。 消息中心用户是需要访问“实时事件”(nmsRtEvent)文件夹的专用权限的特定操作员。

## 模式扩展

在&#x200B;**消息中心技术工作流**&#x200B;在控件或执行实例上使用的模式上执行的所有模式扩展都需要在Adobe Campaign事务消息模块使用的其他实例上进行复制。

:arrow_upper_right:了解有关[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)中消息中心技术工作流的更多信息

## 发送交易推送通知

结合移动应用渠道模块后，交易消息传递使您能够在移动设备上通过通知推送事务性消息。

:arrow_upper_right:移动应用程序渠道详见[Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages)。

要发送事务推送通知，您需要执行以下配置：

1. 将&#x200B;**移动应用程序渠道**&#x200B;包安装到控件和执行实例上。

   >[!CAUTION]
   >
   >安装新的活动内置包前，请检查您的许可协议。

1. 在执行实例上复制&#x200B;**移动应用程序**&#x200B;服务和关联的移动应用程序。

为了使活动发送事务推送通知，事件必须包含以下元素：

* 移动设备ID:**registrationId**（适用于Android）和&#x200B;**deviceToken**（适用于iOS）。 此ID表示通知将发送到的“地址”。
* 指向移动应用程序或集成键(**uuid**)的链接，用于检索特定于应用程序的连接信息。
* 将向其发送通知的渠道(**whistChannel**):41适用于iOS，42适用于Android。
* 可用于个性化的其他数据。

以下是包含此信息的事件的示例：

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

