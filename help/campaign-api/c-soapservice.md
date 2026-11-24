---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%
---
# SoapService（类）

允许您在Web服务上执行SOAP调用。

## 阻止调用

以下是典型的用法示例：您必须首先创建一个连接，然后使用此连接的服务，最后为此服务声明SOAP方法。 SOAP方法以服务对象的JavaScript方法的形式公开。

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## 非阻塞调用

可以执行非阻塞（异步）调用，即对服务器运行SOAP查询，并继续执行脚本而不等待结果。 与阻止模式的主要区别如下：

* 必须在异步模式下创建连接

* 请使用

  [开始](m-soapservice-start.md)

  函数。

* 定义

  [完成](p-soapservice-complete.md)

  函数中，将在收到响应时调用。

* 此

  [SoapService.wait](m-soapservice-wait.md)

  函数用于等待一组查询的处理结束。

以下示例脚本通过同时打开3个连接对Adobe Campaign服务器进行一系列“GetOption”SOAP调用。

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## 方法

| 方法 | 描述 |
| --- | --- |
| [SoapService](m-soapservice-soapservice.md) | 创建服务以调用Web服务的函数。 |
| [addMethod](m-soapservice-addmethod.md) | 在服务上声明函数。 |
| [处置](m-soapservice-dispose.md) | 释放对象使用的资源。 |
| [开始](m-soapservice-start.md) | 以异步模式启动查询。 |
| [等待](m-soapservice-wait.md) | 等待异步SOAP查询列表的结尾。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [完成](p-soapservice-complete.md) | 完成异步查询时要调用的函数。 |
| [标头](p-soapservice-header.md) | 在SOAP标头中逐字复制的字符串。 |
| [超时](p-soapservice-timeout.md) | 异步查询的最长等待时间（以毫秒为单位）。 如果未定义此参数，则等待时间为5分钟。 |

## 功能

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
