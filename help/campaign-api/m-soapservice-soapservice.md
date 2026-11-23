---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 26%
---
# SoapService

创建服务以调用Web服务的函数。

```text
SoapService (cnx, namespace)
```

## 参数

**cnx** ([HttpSoapConnection](c-httpsoapconnection.md)) HTTP连接。

**命名空间**&#x200B;服务的命名空间。

## 返回值

无。

## 备注

示例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

## 功能

**类的方法：** [SoapService](c-soapservice.md)

**可用位置：**

* 内容管理
* 投放属性
* 投放消息
* 类型规则
* 导入
* JSSP
* SOAP方法
* WebApp
* 工作流
