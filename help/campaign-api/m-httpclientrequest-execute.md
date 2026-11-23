---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 6%
---
# 执行

运行HTTP查询。

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## 参数

如果需要使用HTTP代理，**hasProxy** Boolean设置为true。 默认设置为false。

如果查询是异步的，则&#x200B;**async**&#x200B;布尔值设置为true。 默认设置为false。

如果基础套接字应允许重复使用本地地址，则&#x200B;**reuseaddr**&#x200B;布尔值设置为true。 默认设置为false。

**上下文**&#x200B;上下文是任何对象，在异步查询时将转发到[complete](p-httpclientrequest-complete.md)函数的第二个参数。默认设置为null。

**超时**&#x200B;异步查询的最长等待时间（以毫秒为单位）。 如果未定义此参数，则等待时间为5分钟。

## 返回值

无。

## 备注

如果HTTP连接失败，则会引发异常。 [响应](p-httpclientrequest-response.md)属性仅在成功调用execute函数后生效。 示例：

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
```

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
