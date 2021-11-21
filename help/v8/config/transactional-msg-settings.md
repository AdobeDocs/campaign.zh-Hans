---
title: Campaign事务型消息传递设置
description: Campaign事务型消息传递设置
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# 事务性消息设置

![](../assets/do-not-localize/speech.png)  作为托管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support) ，以在您的环境中安装和配置Campaign事务型消息传递。

![](../assets/do-not-localize/glass.png) 事务性消息传递功能在 [此部分](../send/transactional.md).

![](../assets/do-not-localize/glass.png) 了解中的事务型消息传递架构 [本页](../dev/architecture.md).

## 定义权限

要为托管在Adobe云上的消息中心执行实例创建新用户，您需要联系Adobe客户关怀团队。 消息中心用户是特定的操作员，需要专用权限才能访问“实时事件”(nmsRtEvent)文件夹。

## 模式扩展

对使用的架构进行的所有架构扩展 **消息中心技术工作流** 在上，需要在Adobe Campaign事务型消息传递模块使用的其他实例上复制控制实例或执行实例。

![](../assets/do-not-localize/book.png) 了解有关消息中心技术工作流的更多信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## 发送事务推送通知

与移动设备应用程序渠道模块结合使用时，事务型消息传递允许您通过移动设备上的通知推送事务型消息。

![](../assets/do-not-localize/book.png) 有关移动设备应用程序渠道的详细信息，请参阅 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

要发送事务推送通知，您需要执行以下配置：

1. 安装 **移动设备应用程序渠道** 包到控件和执行实例上。

   >[!CAUTION]
   >
   >在安装新的Campaign内置包之前，请检查您的许可协议。

1. 复制 **移动应用程序** 服务和执行实例上关联的移动应用程序。

为了使Campaign发送事务推送通知，事件必须包含以下元素：

* 移动设备ID: **registrationId** 适用于Android和 **deviceToken** iOS。 此ID表示通知将发送到的“地址”。
* 指向移动应用程序或集成密钥的链接(**uid**)，用于检索特定于应用程序的连接信息。
* 将向其发送通知的渠道(**wishedChannel**):iOS为41，安卓为42。
* 用于个性化的其他数据。

以下是包含此信息的事件示例：

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
