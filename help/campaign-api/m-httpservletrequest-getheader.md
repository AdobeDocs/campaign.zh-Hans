---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '30'
ht-degree: 16%
---
# getHeader

返回在查询标头中定义的属性。

```text
getHeader (name)
```

## 参数

**name**&#x200B;标头属性的名称。

## 返回值

无。

## 备注

示例：

```javascript
Host: <%= request.getHeader("host") %>
```

## 功能

**类的方法：** [HttpServletRequest](c-httpservletrequest.md)

**可用位置：**

* JSSP
* WebApp
