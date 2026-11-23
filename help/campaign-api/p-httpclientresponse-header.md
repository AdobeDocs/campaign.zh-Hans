---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 19%
---
# 标题

包含所有HTTP标头的对象。

```text
header
```

## 备注

属性的名称不区分大小写。 示例：

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

要恢复多个具有相同名称的标头，请使用[标头](p-httpclientresponse-headers.md)属性，而不是标头属性。

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
