---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# 等待

等待直到异步查询列表的结尾。

```text
wait (requests,waitAll)
```

## 参数

**请求**&#x200B;查询表。

**waitAll**&#x200B;布尔值（默认为true），等待查询列表中的所有请求完成。 当设置为false时，如果至少完成一个请求，则函数将退出侦听循环。

## 返回值

无。

## 备注

函数不适用于查询，但是HttpClientRequest bin的函数。 示例：

```javascript
var req = new HttpClientRequest("http://www.adobe.com/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

仅当查询是异步的并且[execute](m-httpclientrequest-execute.md)调用未引发异常时，才能将其添加到列表中。 查询完成后，将自动从列表中删除该查询。 这意味着当函数返回控件时，作为参数传递的表将为空。 列表可由[complete](p-httpclientrequest-complete.md)函数修改：例如，可以启动新查询并将其添加到列表。

## 功能

**类的方法：** [HttpClientRequest](c-httpclientrequest.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
