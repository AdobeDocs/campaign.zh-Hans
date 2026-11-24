---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%
---
# 正文

HTTP查询的正文。

```text
body
```

## 备注

按如下方式处理分配给查询主体的对象：

* undefined， null， function：不被视为可发送的元素，HTTP查询的正文为空。
* 数字、布尔值、字符串、XML、对象：已更改为基于toString方法的字符字符串，并根据HTTP标头Content-type进行编码。
* [MemoryBuffer](c-memorybuffer.md)：在查询正文中复制了内容，没有进行更改。

示例：

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
```

## 功能

**类的属性：** [HttpClientRequest](c-httpclientrequest.md)

**只读：**

否

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
