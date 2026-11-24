---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# 标头

按名称分组的HTTP响应的标头列表。

```text
headers
```

## 备注

每个标头属性携带标头的名称和表的值，该表将每个标头与此名称匹配。 此函数不同于[标头](p-httpclientresponse-header.md)，因为它返回一个值表，而不是给定名称的唯一值。 这对于可能出现多次的标头非常有用，例如Accept-Language或Set-Cookie。 如果HTTP响应没有使用此名称的标头，则函数将返回空表。 示例：

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

标头属性不可分项。 属性名称不区分大小写。

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
