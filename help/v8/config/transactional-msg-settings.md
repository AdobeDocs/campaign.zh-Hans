---
solution: Campaign v8
product: Adobe Campaign
title: Campaign事务型消息传递设置
description: Campaign事务型消息传递设置
feature: 概述
role: Data Engineer
level: Beginner
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---

# 事务型消息传递设置

:speech_balloon:作为受管Cloud Services用户， [联系Adobe](../start/campaign-faq.md#support)以在您的环境中安装和配置Campaign事务型消息传递。

[!DNL :bulb:] 有关事务性消息传递功能的详 [细信息，请参阅此章节](../send/transactional.md)。

[!DNL :bulb:] 了解本页中的事务型消 [息传递架构](../dev/architecture.md)。

## 定义权限

要为托管在Adobe云上的消息中心执行实例创建新用户，您需要联系Adobe客户关怀团队。 消息中心用户是特定的操作员，需要专用权限才能访问“实时事件”(nmsRtEvent)文件夹。

## 模式扩展

对&#x200B;**消息中心技术工作流**&#x200B;在控制实例或执行实例上使用的架构所做的所有架构扩展，都需要复制到Adobe Campaign事务性消息传递模块使用的其他实例上。

[!DNL :arrow_upper_right:] 在Campaign Classicv7文档中了解有关消息中心技术工 [作流的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)

## 发送事务推送通知

与移动设备应用程序渠道模块结合使用时，事务型消息传递允许您通过移动设备上的通知推送事务型消息。

[!DNL :arrow_upper_right:] Campaign Classicv7文档中详细介绍了 [移动应用程序渠道](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages)。

要发送事务推送通知，您需要执行以下配置：

1. 将&#x200B;**移动设备应用程序渠道**&#x200B;包安装到控件和执行实例上。

   >[!CAUTION]
   >
   >在安装新的Campaign内置包之前，请检查您的许可协议。

1. 在执行实例上复制&#x200B;**移动应用程序**&#x200B;服务和关联的移动应用程序。

为了使Campaign发送事务推送通知，事件必须包含以下元素：

* 移动设备ID:适用于Android的&#x200B;**registrationId**&#x200B;和适用于iOS的&#x200B;**deviceToken**。 此ID表示通知将发送到的“地址”。
* 指向移动应用程序或集成密钥(**uuid**)的链接，用于检索特定于应用程序的连接信息。
* 将向其发送通知的渠道(**wishedChannel**):iOS为41,Android为42。
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

