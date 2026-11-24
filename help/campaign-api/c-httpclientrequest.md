---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 4%
---
# HttpClientRequest（类）

HttpClientRequest对象允许您作为HTTP客户端执行某些操作。

示例：

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## “保持活动状态”

对象可以在两种不同的模式下使用：标准模式或保持活动模式。 标准模式允许您发送单个查询，保持活动模式允许您发送多个查询，同时保持连接打开。 对象的状态取决于方法的使用顺序。 如果调用connect()方法，则对象将切换到“保持活动状态”模式。 示例

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## 异步查询

默认情况下，查询在阻止模式下执行，这意味着

[执行](m-httpclientrequest-execute.md)

函数仅在发送查询并收到响应后返回控制。 也可以以异步模式执行查询。 在本例中，

[执行](m-httpclientrequest-execute.md)

function立即返回控制，并在收到响应后调用函数。 这样即可同时执行多个查询。 以下程序是一个完整示例，它向您展示了如何运行同时打开3个连接的一系列HTTP上载，其中每个上载在最后一个上载完成后开始。

```text
var list = [ "http://www.adobe.com/cn/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## 方法

| 方法 | 描述 |
| --- | --- |
| [HttpClientRequest](m-httpclientrequest-httpclientrequest.md) | 创建新对象以运行HTTP客户端查询。 |
| [连接](m-httpclientrequest-connect.md) | 打开HTTP连接并将对象传递到“保持活动状态”模式 |
| [断开连接](m-httpclientrequest-disconnect.md) | 在“保持活动”模式下关闭对象的HTTP连接。 |
| [执行](m-httpclientrequest-execute.md) | 运行HTTP查询。 |
| [等待](m-httpclientrequest-wait.md) | 等待异步查询列表的结尾。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [正文](p-httpclientrequest-body.md) | HTTP查询的正文。 |
| [完成](p-httpclientrequest-complete.md) | 完成异步查询时要调用的函数。 |
| [标头](p-httpclientrequest-header.md) | 包含标头的HTTP标头的JavaScript对象。 |
| [方法](p-httpclientrequest-method.md) | HTTP方法，以字符串形式表示 |
| [响应](p-httpclientrequest-response.md) | HTTP查询的响应。 这是HttpClientResponse类型对象 |
| [url](p-httpclientrequest-url.md) | 远程服务器的地址。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
