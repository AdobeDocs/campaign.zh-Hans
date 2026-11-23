---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%
---
# 正文

以MemoryBuffer对象形式表示的HTTP响应主体。

```text
body
```

## 备注

响应正文的编码可通过[codePage](p-httpclientresponse-codepage.md)属性访问。 HTTP响应的正文以[MemoryBuffer](c-memorybuffer.md)对象的形式提供。 因此，所有适用于[MemoryBuffer](c-memorybuffer.md)的方法都适用于HTTP响应的正文。 示例：

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

## 功能

**类的属性：** [HttpClientResponse](c-httpclientresponse.md)

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
