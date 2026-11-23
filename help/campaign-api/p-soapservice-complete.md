---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# 完成

完成异步查询时要调用的函数。

```text
complete
```

## 备注

函数必须接受四个参数：

* 服务
* 结果
* 上下文：这是传递给[start](m-soapservice-start.md)函数的参数
* 状态

状态可以具有以下值：

* “success”表示已收到结果。
* “错误”可能意味着通信中断、响应结构错误或发生HTTP错误。
* 如果返回SOAP错误，则为“fault”。 在这种情况下，结果包含一个描述错误的对象。
* “超时”表示无法建立连接，或者在配置的截止日期内未收到任何响应。

当结果为“success”时，结果取决于返回的参数数量：

* 如果查询未返回任何值，则无效
* 如果查询返回单个参数的值
* 如果查询返回多个参数的表

当状态为“fault”时，结果会是包含以下属性的对象：

* 消息：错误说明消息。
* 对象：包含错误详细信息的XML对象。

示例：

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
```

## 功能

**类的属性：** [SoapService](c-soapservice.md)

**只读：**

否

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
