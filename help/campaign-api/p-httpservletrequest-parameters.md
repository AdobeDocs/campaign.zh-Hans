---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 15%
---
# 参数

返回查询参数。

```text
parameters
```

## 备注

parameters属性返回一个对象，其属性与查询的参数匹配。 示例：

```javascript
var parameters = request.parameters
for(var name in parameters)
{
var value = parameters[name]
document.write(name + " : " + value + "<br>")
}
```

## 功能

**类的属性：** [HttpServletRequest](c-httpservletrequest.md)

**只读：**

是

**可用位置：**

* JSSP
* WebApp
