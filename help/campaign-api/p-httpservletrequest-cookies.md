---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 13%
---
# Cookie

返回查询的Cookie。

```text
cookies
```

## 备注

Cookie属性返回一个对象，其每个属性都具有匹配的Cookie。 示例：

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
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
