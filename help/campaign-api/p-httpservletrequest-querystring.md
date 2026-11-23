---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 11%
---
# querystring

返回查询URL中与参数匹配的部分。

```text
queryString
```

## 备注

示例：以下URL的查询字符串：

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

返回以下字符串：

```javascript
id=1234&param=dummy
```

## 功能

**类的属性：** [HttpServletRequest](c-httpservletrequest.md)

**只读：**

是

**可用位置：**

* JSSP
* WebApp
