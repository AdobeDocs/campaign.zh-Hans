---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 9%
---
# getSchema

返回到Adobe Campaign架构的映射，如果架构不存在，则返回空值。

```text
getSchema (name [, checkIfUpdated ])
```

## 参数

**名称**&#x200B;完整的架构名称。

**checkIfUpdated**&#x200B;检查架构是否已在缓存中更新。 如果架构已在脚本中实例化，则没有影响。

## 返回值

架构映射（请参阅[架构](c-schema.md)对象）或方法启动异常时，架构与名称不重合。

## 备注

在脚本结束前，脚本中实例化的所有架构都会保留在内存中。 示例：

```javascript
      var schema = application.getSchema("nms:recipient")
```

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
