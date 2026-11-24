---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# HttpClientRequest

创建新对象以运行HTTP客户端查询。

```text
HttpClientRequest ( [URL ])
```

## 参数

查询收件人的&#x200B;**URL** URL。

## 返回值

无。

## 备注

如果FTP命令失败，则会引发异常。 示例：

```javascript
var http = new HttpClientRequest("http://www.somewhere.com/login")

var buffer = new MemoryBuffer()
buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"

http.method = "SEARCH"
http.body = "<xml>any content</xml>"

http.execute()
       
```

## 功能

**类的方法：** [HttpClientRequest](c-httpclientrequest.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
