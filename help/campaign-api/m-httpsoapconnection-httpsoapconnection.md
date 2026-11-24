---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 9%
---
# HttpSoapConnection

创建到SOAP服务器的HTTP连接。

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## 参数

包含路径的服务器的&#x200B;**url** URL。

**代码页** SOAP调用的序列化编码。 此可选参数允许您指定字符编码。 默认情况下，编码为UTF-8。 示例：

* iso-8859-1
* utf-8
* utf-16

**协议**&#x200B;使用的SOAP协议类型。 此可选参数允许您指定使用的SOAP协议，默认为SOAP\_11。可能值：

* SOAP\_11： SOAP协议1.1。
* SOAP\_12： SOAP协议1.2。
* 0：Adobe Campaign内部的SOAP协议。

如果连接预定要执行异步查询，则&#x200B;**async**&#x200B;布尔值设置为true。 默认情况下设置为false。

## 返回值

无。

## 备注

示例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
```

## 功能

**类的方法：** [HttpSoapConnection](c-httpsoapconnection.md)

**可用位置：**

* 内容管理
* 投放属性
* 投放消息
* 类型规则
* 导入
* JSSP
* SOAP方法
* WebApp
* 工作流
