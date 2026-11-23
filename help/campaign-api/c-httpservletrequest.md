---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# HttpServletRequest（类）

表示转发到servlet的客户端的查询。

此地址只有一个可通过`request`访问的实例。 变量。

## 方法

| 方法 | 描述 |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | 返回在查询标头中定义的属性。 |
| [getParameter](m-httpservletrequest-getparameter.md) | 返回查询参数的值。 |
| [getRemoteAddr](m-httpservletrequest-getremoteaddr.md) | 返回客户端或上次发送请求的代理的IP地址。 |
| [getUTF8参数](m-httpservletrequest-getutf8parameter.md) | 返回查询参数的值（以UTF-8编码）。 |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | 使用查询编码以字符串形式返回查询正文。 |
| [转发](m-httpservletrequest-forward.md) | 无需通过客户端即可将查询重定向到其他页面。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [参数](p-httpservletrequest-parameters.md) | 返回查询参数。 |
| [Cookie](p-httpservletrequest-cookies.md) | 返回查询的Cookie。 |
| [requestURI](p-httpservletrequest-requesturi.md) | 返回查询的URL。 |
| [查询字符串](p-httpservletrequest-querystring.md) | 返回查询URL中与参数匹配的部分。 |
| [方案](p-httpservletrequest-scheme.md) | 返回所用协议的名称（HTTP、HTTPS等） 以访问此页面。 |
| [服务器名称](p-httpservletrequest-servername.md) | 返回查询服务器的名称。 |
| [服务器端口](p-httpservletrequest-serverport.md) | 返回用于联系服务器的端口号。 |
| [serverURL](p-httpservletrequest-serverurl.md) | 返回用于访问服务器的URL。 |
| [servletPath](p-httpservletrequest-servletpath.md) | 返回查询URL中与servlet匹配的部分。 |
| [contextPath](p-httpservletrequest-contextpath.md) | 返回查询URL中与上下文匹配的部分。 |
| [pathInfo](p-httpservletrequest-pathinfo.md) | 返回查询URL的其他信息。 |
| [方法](p-httpservletrequest-method.md) | 返回一个字符串，其中包含用于调用此查询的HTTP方法（GET、HEAD、POST等）。 |

## 功能

**可用位置：**

* JSSP
* WebApp
