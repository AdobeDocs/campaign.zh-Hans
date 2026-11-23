---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 11%
---
# 开始

以异步模式启动查询。

```text
start (context, name, ...)
```

## 参数

**上下文**&#x200B;任何将转发到[完成](p-soapservice-complete.md)函数的用户参数。

**name**&#x200B;调用方法的名称。

**...**&#x200B;函数参数。

## 返回值

创建的查询。 此对象没有属性或函数，它对[wait](m-soapservice-wait.md)函数非常有用，该函数允许您等到操作结束。

## 备注

服务连接必须是异步的。 如果连接阻塞，则会引发异常。 如果连接上当前正在执行另一个查询，则无法运行查询。 在这种情况下，将引发异常。

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
