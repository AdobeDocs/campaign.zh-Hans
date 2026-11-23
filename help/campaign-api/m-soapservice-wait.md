---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%
---
# 等待

等待异步SOAP查询列表的结尾。

```text
wait (requests)
```

## 参数

**请求**&#x200B;查询表。

## 返回值

无。

## 备注

该函数不适用于服务，但是SoapService bin的函数。 示例：

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

查询完成后，将自动从列表中删除该查询。 这意味着当函数返回控件时，作为参数传递的表将为空。 列表可由[complete](p-soapservice-complete.md)函数修改：例如，可以启动新查询并将其添加到列表。

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
