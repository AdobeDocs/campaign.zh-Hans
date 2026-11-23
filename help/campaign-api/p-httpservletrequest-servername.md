---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 12%
---
# serverName

返回查询服务器的名称。

```text
serverName
```

## 备注

示例：以下URL的serverName：

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

返回以下字符串：

```javascript
adobe.com
```

## 功能

**类的属性：** [HttpServletRequest](c-httpservletrequest.md)

**只读：**

是

**可用位置：**

* JSSP
* WebApp
