---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 9%
---
# getDBMSType

返回数据库的服务器类型。

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## 参数

**name**&#x200B;数据源的名称。

**checkIfUpdated**&#x200B;检查架构是否已在缓存中更新。 如果架构已在脚本中实例化，则没有影响。

## 返回值

包含数据库服务器类型的文本字符串。

## 备注

如果未指定数据源，则函数默认使用“nms:default”。 数据源必须存在，否则将引发异常。

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
