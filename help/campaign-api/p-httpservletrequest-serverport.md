---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%
---
# 服务器端口

返回用于联系服务器的端口号。

```text
serverPort
```

## 备注

示例：以下URL的serverPort：

```javascript
http://adobe.com/cn:8080/nms/test.jst
```

返回以下字符串：

```javascript
8080
```

以下URL的serverPort：

```javascript
http://adobe.com/nms/test.jst
```

返回以下字符串：

```javascript
80
```

## 功能

**类的属性：** [HttpServletRequest](c-httpservletrequest.md)

**只读：**

是

**可用位置：**

* JSSP
* WebApp
