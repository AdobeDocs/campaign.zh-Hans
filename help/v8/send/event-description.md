---
title: 了解事件描述
description: 了解如何使用SOAP方法在Adobe Campaign Classic中管理事务性消息传递事件
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 2f679d1c-4eb6-4b3c-bdc5-02d3dea6b7d3
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 0%

---

# 了解事件描述 {#about-event-desc}

## 事务性消息传递数据模型 {#about-mc-datamodel}

事务性消息传递依赖于Adobe Campaign数据模型，并使用两个额外的单独表。 这些表格， **NmsRtEvent** 和 **NmsBatchEvent**，包含相同的字段，让您可以一方面管理实时事件，另一方面管理批量事件。

## SOAP方法 {#soap-methods}

本节详细介绍与事务性消息模块模式关联的SOAP方法。

两个 **Pushevent** 或 **PushEvents** SOAP方法链接到这两个 **nms：rtEvent** 和 **nms：BatchEvent** 数据架构。 它是确定事件是“批处理”还是“实时”类型的信息系统。

* **Pushevent** 允许您将单个事件插入到消息中，
* **PushEvents** 允许您将一系列事件插入到消息中。

用于访问这两种方法的WSDL路径为：

* **http://hostname/nl/jsp/schemawsdl.jsp?schema=nms:rtEvent** 以访问实时类型架构。
* **http://hostname/nl/jsp/schemawsdl.jsp?schema=nms:batchEvent** 以访问批处理类型架构。

这两种方法都包含 **`<urn:sessiontoken>`** 用于登录到事务性消息传递模块的元素。 我们建议使用通过受信任的IP地址进行标识的方法。 要检索会话令牌，请执行登录SOAP调用，然后执行get令牌和注销。 对多个RT调用使用相同的令牌。 此部分中包含的示例正在使用会话令牌方法，建议使用此方法。

如果您使用的是负载平衡服务器，则可以使用用户/密码身份验证（在RT消息的级别）。 例如：

```
<PushEvent xmlns="urn:nms:rtEvent">
<sessiontoken>mc/PASSWORD</sessiontoken>
<domEvent>
<rtEvent wishedChannel="41" type="rt_MobileJourney_iOS_Push" registrationToken="c3ddc8aaecc24822df25d0f49865cca61ea3f86c61bfa53ae4d37294e37f4a1c" hashlpId="27EE7571EC14DBA23B9B5CC0EF79BB782DAECF4C03C88E5D92CC9B9DAC4E5DDA" correlationId="415b7593-4f6f-e911-811f-00505691247c" xmlns="">
<mobileApp uuid="236B24DC-C073-412F-8BCB-AC7207096258" _operation="none"/>
<ctx>...</ctx>
</rtEvent>
</domEvent>
</PushEvent>
```

此 **Pushevent** 方法由 **`<urn:domevent>`** 包含事件的参数。

此 **PushEvents** 方法由 **`<urn:domeventcollection>`** 包含事件的参数。

使用PushEvent的示例：

```
<urn:PushEvent>

 <sessiontoken>___921f9b38-72ac-49ad-b481-ab32973efc50</sessiontoken>
 
 <urn:domEvent>
 
   <rtEvent>
   
   ...
   
   </rtEvent>
 
 </urn:domEvent>

</urn:PushEvent>
```

>[!NOTE]
>
>如果调用了 **PushEvents** 方法，需要添加一个符合标准XML的父XML元素。 此XML元素将 **`<rtevent>`** 事件中包含的元素。

使用PushEvents的示例：

```
<urn:PushEvents>

 <sessiontoken>___921f9b38-72ac-49ad-b481-ab32973efc50</sessiontoken>
 
 <urn:domEventCollection>
 
   <Events>
   
     <rtEvent>... </rtEvent>
     
     <rtEvent>... </rtEvent>
     
     ...
   
   </Events>
 
 </urn:domEventCollection>

</urn:PushEvents>
```

此 **`<rtevent>`** 和 **`<batchevent>`** 元素具有一组属性以及一个必需的子元素： **`<ctx>`** 用于集成报文数据。

>[!NOTE]
>
>此 **`<batchevent>`** 元素用于将事件添加到“批处理”队列。 此 **`<rtevent>`** 将事件添加到“实时”队列。

的必需属性 **`<rtevent>`** 和 **`<batchevent>`** 元素为@type和@email。 @type的值必须与配置执行实例时定义的明细列表值相同。 此值允许您定义在投放期间链接到事件内容的模板。

`<rtevent> configuration example:`

```
<rtEvent type="order_confirmation" email="john.doe@domain.com" origin="eCommerce" wishedChannel="0" externalId="1242" mobilePhone="+33620202020"> 
```

在此示例中，提供了两个渠道：电子邮件地址和手机号码。 此 **希望渠道** 允许您选择在将事件转换为消息时要使用的渠道。 “0”值对应于电子邮件渠道，“1”值对应于移动渠道，依此类推。

如果要延迟事件投放，请添加 **[!UICONTROL scheduled]** 字段后跟首选日期。 该事件将在此日期转换为消息。

我们建议使用数值填充@wishedChannel和@emailFormat属性。 在数据架构描述中找到用于链接数值和标签的函数表。

>[!NOTE]
>
>有关所有授权属性及其值的详细说明，请参阅 **nms：rtEvent** 和 **nms：BatchEvent** 数据架构。

此 **`<ctx>`** 元素包含消息数据。 其XML内容是开放的，这意味着可以根据要交付的内容对其进行配置。

>[!NOTE]
>
>优化消息中包含的XML节点的数目和大小很重要，以避免在投放期间使服务器过载。

数据示例：

```
   <ctx>
               <client>
                        <firstname>John</firstname>
                        <lastname>Doe</lastname>
               </client>
               <action>
                         <type>Order confirmation</type>
                          <number>CN23453</number>
               </action>
               <orderdetails>
                          <article num="1">
                                   <name>Generic USB key</name>
                                   <price>20</price>
                           </article>
               </orderdetails>
    </ctx>
```

## SOAP调用返回的信息 {#information-returned-by-the-soap-call}

Adobe Campaign在收到事件时生成一个唯一的返回ID。 这是事件的存档版本的ID。

>[!IMPORTANT]
>
>在接收SOAP调用时，Adobe Campaign会验证电子邮件地址格式。 如果电子邮件地址的格式不正确，则会返回错误。

* 事件处理成功时方法返回的标识符示例：

  ```
  <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="http://xml.apache.org/xml-soap" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
     <SOAP-ENV:Body>
        <urn:PushEventResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns:urn="urn:nms:rtEvent">
           <plId xsi:type="xsd:long">72057594037935966</plId>
        </urn:PushEventResponse>
     </SOAP-ENV:Body>
  </SOAP-ENV:Envelope>
  ```

如果返回标识符的值完全大于零，则表示已在Adobe Campaign中成功存档该事件。

但是，如果无法处理该事件，此方法将返回一条错误消息或一个等于零的值。

* 查询不包含登录名或指定的运算符没有所需权限时失败的事件处理示例：

  ```
  <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
     <SOAP-ENV:Body>
        <SOAP-ENV:Fault>
           <faultcode>SOAP-ENV:Client</faultcode>
           <faultstring xsi:type="xsd:string">Error while reading parameters of method 'PushEvent' of service 'nms:rtEvent'.</faultstring>
           <detail xsi:type="xsd:string">Invalid login or password. Connection denied.</detail>
        </SOAP-ENV:Fault>
     </SOAP-ENV:Body>
  </SOAP-ENV:Envelope>
  ```

* 由于查询中的错误而失败的事件示例（不遵循XML分类）：

  ```
  <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
     <SOAP-ENV:Body>
        <SOAP-ENV:Fault>
           <faultcode>SOAP-ENV:Client</faultcode>
           <faultstring xsi:type="xsd:string">The XML SOAP message is invalid (service 'PushEvent', method 'nms:rtEvent').</faultstring>
           <detail xsi:type="xsd:string"><![CDATA[(16:8) : Expected end of tag 'rtevent'
  Error while parsing XML string '<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
     <soapenv:Header/>
     <soapenv:Body>
        <urn:PushEvent>
           <urn:sessiontoken>mc/</urn:sessiontoken>
           <urn:domEvent>
  <rtevent type="create_account" email="esther.hall@adobe.com" origin="eCommerce" wishedChannel="email" 
        externalId="1596" language="english" country="EN" emailFormat="2"
        mobilePhone="+447700123123">
    <ctx>
     <website name="eCommerce" url="http://www.eCo']]></detail>
        </SOAP-ENV:Fault>
     </SOAP-ENV:Body>
  </SOAP-ENV:Envelope>
  ```

* 失败并返回零标识符（错误的方法名称）的事件示例：

  ```
  <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="http://xml.apache.org/xml-soap" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
     <SOAP-ENV:Body>
        <urn:PushEventResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns:urn="urn:nms:rtEvent">
           <plId xsi:type="xsd:long">0</plId>
        </urn:PushEventResponse>
     </SOAP-ENV:Body>
  </SOAP-ENV:Envelope>
  ```
