---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%
---
# getConnection

返回到数据库服务器的新连接。

```text
getConnection ()
```

## 参数

无。

## 返回值

与数据库服务器的[连接](c-dbengine.md)。

## 备注

可以使用[dispose](m-dbengine-dispose.md)方法在脚本执行结束之前释放连接。

## 功能

**类的方法：** [应用程序](c-application.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
