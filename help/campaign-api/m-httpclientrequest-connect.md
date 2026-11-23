---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# connect

打开HTTP连接并将对象传递到“保持活动状态”模式

```text
connect ( [hasProxy ] [, async ])
```

## 参数

如果需要使用代理HTTP，请将&#x200B;**hasProxy**&#x200B;布尔值设置为true。 默认设置为false。

如果连接预定要执行异步查询，则&#x200B;**async**&#x200B;布尔值设置为true。 默认情况下设置为false。

## 返回值

无。

## 备注

如果HTTP连接失败，则会引发异常。 只有在成功调用execute函数后，响应属性才会生效。 使用完连接后，不要忘记调用disconnect()。 示例：

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
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
