---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 17%
---
# setcontenttype

更改响应的文档类型。

```text
setContentType (name)
```

## 参数

文档的&#x200B;**名称** MIME类型。

## 返回值

无。

## 备注

示例：

```javascript
      response.setContentType("text/html;charset=ISO-8859-1")
```

## 功能

**类的方法：** [HttpServletResponse](c-httpservletresponse.md)

**可用位置：**

* JSSP
* WebApp
