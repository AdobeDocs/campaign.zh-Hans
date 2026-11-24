---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# setheader

指定HTTP标头。

```text
setHeader (headerName, headerValue)
```

## 参数

**headerName**&#x200B;字符串，即HTTP标头的名称。

**headerValue**&#x200B;字符串，它是HTTP标头的内容。

## 返回值

无。

## 备注

在SOAP上建有小酒庄。 示例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.setHeader("Authorization","Basic " + memBuf.toBase64());
```

## 功能

**类的方法：** [HttpSoapConnection](c-httpsoapconnection.md)

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
