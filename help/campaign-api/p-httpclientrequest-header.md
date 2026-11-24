---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 14%
---
# 标题

包含标头的HTTP标头的JavaScript对象。

```text
header
```

## 备注

标头对象的所有属性在读/写模式下均可访问，并且可枚举。 标头对象的每个所有者都是查询的HTTP标头中的一个条目。 属性名称不区分大小写（对于HTTP标头）。 示例：

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## 功能

**类的属性：** [HttpClientRequest](c-httpclientrequest.md)

**只读：**

是

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
