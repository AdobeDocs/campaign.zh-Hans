---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 14%
---
# 处置

从链接到它的所有资源中释放连接。

```text
dispose ()
```

## 参数

无。

## 返回值

无。

## 备注

使用[application.getConnection()](m-application-getconnection.md)方法创建的连接将在脚本结束时自动释放。 调用此方法对于具有较长生命周期的脚本非常有用。

## 功能

**类的方法：** [DBEngine](c-dbengine.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
