---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# 完成

完成异步查询时要调用的函数。

```text
complete
```

## 备注

函数必须接受三个参数：

* 查询
* 上下文
* 状态：“success”、“error”或“timeout”

“success”状态表示已收到响应，但响应可以包含任何代码（200、404、503等）。 “错误”状态可能意味着结构不佳的响应的通信中断。 “超时”状态表示无法建立连接，或者在配置的截止日期内未收到任何响应。 示例：

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
```

## 功能

**类的属性：** [HttpClientRequest](c-httpclientrequest.md)

**只读：**

否

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
