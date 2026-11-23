---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 6%
---
# addMethod

在服务上声明函数。

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## 参数

**name**&#x200B;方法的名称。 这是JavaScript中公开的名称，也是SOAP方法的名称。

**action** SOAP-Action参数。

**参数**&#x200B;以表的形式声明参数，该表包含按对分组的字符串列表。 第一个字符串是参数的名称，第二个字符串对应于类型： \[&quot;name1&quot;、&quot;type1&quot;、&quot;name2&quot;、&quot;type2&quot;、...\]

**响应**&#x200B;以表的形式声明返回值，该表包含按对分组的字符串列表：第一个字符串是参数的名称，第二个字符串对应于类型： \[&quot;name1&quot;， &quot;type1&quot;， &quot;name2&quot;， &quot;type2&quot;， ...\]

**requestNodeName**&#x200B;一个字符串，它指定SOAP查询的XML节点名称而不是方法名称。

**responseNodeName**&#x200B;一个字符串，它指定SOAP响应的XML节点名称，而不是方法名称后跟响应。

## 返回值

无。

## 备注

支持以下类型：

* 字符串
* 布尔值
* 长
* 短
* 字节
* float
* double
* 日期
* time
* datetime
* NLDocument
* 勒勒芒
* NLRawxml
* NLCollection

在服务上声明方法时，此方法将成为服务的方法，可以通过其名称调用方法直接调用。 传入参数上使用的NLRawXML类型将复制整个XML节点以替换参数。 用作返回类型，它包含SOAP响应的整个第一个子元素。 它的使用意味着SOAP响应只有一个子元素。 传入参数中使用的NLCollection类型将复制所有子元素以替换参数。 当传入参数是变量参数时，此选项非常有用。 用作返回类型，包含整个SOAP响应，因为这是返回值的根。 如果出现错误，则会引发异常。 如果这是格式正确的SOAP错误，则引发的异常具有soapFault属性，并包含SOAP错误的XML节点。 示例：

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
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
